---
name: hillclimb
description: Improve a prompt, skill file, tool description, or model and effort choice against an existing eval without overfitting. Runs a train/test loop with one patch per round, keeps or reverts each patch, diagnoses stalls, and reports the final gain with confidence intervals. Use when the user says hillclimb, asks to tune or optimize a prompt against an eval, raise an eval score, cut model cost or latency at the same quality, or iterate on eval failures. Works on eval.ts files from the eval skill.
metadata:
  version: 1.0.0
  author: illyism
  source: https://il.ly/skills/hillclimb
---

# Hillclimb

Hillclimbing is a loop: read failures, apply one patch, rerun, then keep or revert. This skill runs that loop against an existing `eval.ts` (see the `eval` skill) and stops it from overfitting to the eval's cases.

---

## Preflight: is the eval ready?

Hillclimbing on a bad eval optimizes the bad eval. Check each item before the first patch and fix failures first.

1. **An eval exists.** No `eval.ts` for the feature → build one with the `eval` skill.
2. **Cases mirror production.** They come from production inputs, bug reports, and support tickets first, with hand-written and synthetic cases filling gaps. Hard cases were chosen by judgment with a stated reason, not because the current model fails them. Selecting on current failures measures one model's blind spots.
3. **The score comes from an independent grader.** Use a programmatic check (exact match, fixed label set, schema, tests) or a separate judge model that checks yes/no claims per case. **Never** the generating model's own score, and never a 1–10 scale.
4. **The grader is validated.** Show the user 5–10 graded outputs next to their verdicts and fix disagreements. Judge identical outputs twice and rewrite any claim whose verdict flips.
5. **Infra failures are excluded.** Timeouts, rate limits (429), 5xx errors, and truncated output (`finishReason === 'length'`) are counted separately and rerun, not scored as failures.
6. **Headroom matches the goal.** A baseline of 95% or higher can't show quality gains. Offer a cost or latency goal instead.
7. **The runner supports `--reps=N` and `--split=train|test`.** If not, add them with the snippet below.
8. **The case list is frozen.** Adding cases reshuffles the split. Add cases before the baseline, never mid-climb.

### Add `--reps` and `--split` to an eval.ts

```typescript
import { createHash } from 'node:crypto'

// --reps=N repeats each case; --split=train|test runs one half
const flag = (name: string) => process.argv.find(a => a.startsWith(`--${name}=`))?.split('=')[1]
const REPS = Number(flag('reps') ?? 1)
const SPLIT = flag('split')

// Deterministic split: sort names by hash, first third is test. Adding cases reshuffles it: re-baseline.
const hash = (name: string) => createHash('sha1').update(name).digest('hex')
const byHash = TEST_CASES.map(c => c.name).toSorted((a, b) => hash(a).localeCompare(hash(b)))
const TEST_NAMES = new Set(byHash.slice(0, Math.ceil(byHash.length / 3)))
const CASES = SPLIT ? TEST_CASES.filter(c => TEST_NAMES.has(c.name) === (SPLIT === 'test')) : TEST_CASES
if (CASES.length === 0) throw new Error(`No cases in the ${SPLIT} split`)

const avg = (xs: number[]) => xs.reduce((a, b) => a + b, 0) / xs.length

// Mean ± 95% CI (normal approximation) over per-case mean scores
function meanCI(caseMeans: number[]) {
  const mean = avg(caseMeans)
  const sd = Math.sqrt(caseMeans.reduce((a, x) => a + (x - mean) ** 2, 0) / Math.max(caseMeans.length - 1, 1))
  return { mean, ci: caseMeans.length > 1 ? (1.96 * sd) / Math.sqrt(caseMeans.length) : 0 }
}
```

Then iterate `CASES` instead of `TEST_CASES`, wrap each case in `for (let rep = 1; rep <= REPS; rep++)`, record a 0–1 `score` per run, average each case's reps, and print `mean ± ci` per model in the `eval.md` summary. Flag cases whose score varies across reps as flaky.

---

## Pick the target

- **Cheap to change:** prompt text, skill or instruction files, tool descriptions, model, effort or reasoning level, API parameters. Prefer these over harness rewrites.
- **Attributable:** the metric moves because of the surface you change. Skill trigger rate responds to the skill description; answer accuracy responds to the prompt.
- **One scoped goal:** ask the user to choose "raise the score" (needs headroom) or "cut cost or latency at the same score" (works on saturated evals too).

---

## Set up

1. Commit the current state so every patch is a clean diff you can revert.
2. Run the baseline with `--reps=3` on both splits: `bun <module>/eval.ts --split=train --reps=3`, then `--split=test`.
3. Measure the noise floor: the CI half-width from those runs. If it is larger than the smallest gain worth shipping, add reps or cases before patching.
4. Create `hillclimb.md` next to `eval.md` and record the baseline row.

Read train outputs only. **Never** use test outputs to write a patch.

---

## Each round

1. Read the failing train outputs in `eval.md` and name the root cause.
2. Apply **one** patch aimed at that cause: rewrite the section that produced it, or add the missing rule. Skip cosmetic rewording.
3. Rerun train and test with the same reps.
4. Decide:
   - Train up and test up beyond noise → **keep** and commit.
   - Train up, test flat → **overfit**. Revert.
   - Either split down → **regression**. Revert.
5. Append the round to `hillclimb.md`:

```markdown
| Round | Patch | Train | Test | Cost / case | Decision |
| :--- | :--- | ---: | ---: | ---: | :--- |
| 0 | baseline | <mean> ±<ci> | <mean> ±<ci> | $<cost> | baseline |
| 1 | <one-line patch summary> | <mean> ±<ci> | <mean> ±<ci> | $<cost> | keep / revert (overfit) / revert (regression) |
```

---

## Overfitting guardrails

- **NEVER** paste failing case inputs, outputs, or expected answers into the prompt.
- **NEVER** add a tool or rule that only helps eval cases, such as an OCR tool because one case has an image, or a rule that repeats a case's wording.
- **NEVER** let the system under test reach expected answers. Keep them out of prompts, tool results, and any file the agent can open.
- **ALWAYS** write each patch as a general rule that an unseen production case would also need.

---

## When progress stalls

After 2–3 flat rounds, or sooner if no single fix could beat the noise floor, stop patching and diagnose:

1. Group the remaining train failures by root cause.
2. Remove illegitimate failures first: grader bugs, ambiguous cases, cases that contradict the live API or product, infra errors, and flaky cases. Fixing a grader or case changes the eval, so re-run the baseline on both splits afterward.
3. Look for model priors that override instructions. If the model keeps producing an old form that the prompt already replaces, add an explicit old → new mapping instead of more documentation.
4. If noise is the blocker, add reps or cases instead of more patches.

---

## Cost hillclimb order

When the goal is lower cost at the same score, try these in order and check the test split after each step:

1. Trim the prompt: mandatory tool-call rituals, scratchpad steps, contradictory rules.
2. Lower the effort or reasoning level.
3. Move to a cheaper model tier.
4. Add targeted rules for any new failures.

---

## Finish

- Keep the version with the best **test** score, which is not always the last round.
- Report baseline vs final on the test split with 95% CI, plus cost per case.
- If the gain sits inside the noise, say so and recommend not shipping the change.
- Leave `hillclimb.md` in the repo. It records which patches were tried and why each was kept or reverted.
