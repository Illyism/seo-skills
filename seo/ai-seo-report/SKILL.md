---
name: ai-seo-report
description: >-
  Write the AI SEO Tracker report brief from live MCP data. Use when the user
  wants a TL;DR of AI search visibility, a weekly recap, or the same brief as
  the in-app Report page. Trigger on "tldr the report", "AI SEO brief",
  "why am I missing in ChatGPT", or fetch https://aiseotracker.com/ai-seo-report/SKILL.md.
version: 1.0.0
homepage: https://aiseotracker.com/ai-seo-report/SKILL.md
metadata:
  version: 1.0.0
  author: illyism
  source: https://aiseotracker.com/ai-seo-report/SKILL.md
  site: https://aiseotracker.com
  docs: https://aiseotracker.com/docs/ai-seo-report
  mcp: https://aiseotracker.com/api/agent/mcp
  setup: https://aiseotracker.com/SKILL.md
---

# AI SEO report brief

**Start here:** You are reading `https://aiseotracker.com/ai-seo-report/SKILL.md`. The file is complete only if the **last line** is page end `END SKILL v1.0.0`. If missing, re-fetch.

This is the same job as the in-app Report brief: interpret live visibility for someone who wants mentions in ChatGPT, Gemini, Perplexity, Copilot, and AI Overviews. Do not restate tables. Synthesize.

## If MCP is not connected

Fetch `https://aiseotracker.com/SKILL.md` and connect MCP first (OAuth, no API keys). Then come back to this file.

MCP URL: `https://aiseotracker.com/api/agent/mcp`

## Call order (do not skip)

1. `aiseo_list_projects`: pick the project the user named (domain or slug). Never invent a slug.
2. `aiseo_get_scan`: if `dataStatus` is `no_data`, stop. Say the project needs a scan. If `state` is `running`, say the scan is still in flight and write only from what exists.
3. `aiseo_list_prompts`: all prompts (no status filter). Use `summary` plus `prompts[].href`.
4. `aiseo_list_sources`: citation domains. Use `sources[].href`.
5. `aiseo_list_competitors`: tracked rivals. Prefer `status=TRACKED`. Use `competitors[].href`.
6. `aiseo_list_snippets`: own brand (omit `brand` or pass the project name). Optional: one tracked competitor if a rival leads the story.

Do not call `aiseo_add_prompts` from this skill.

## Build REPORT DATA from tool JSON

Use `href` fields from the tools. Prefix each `href` with `https://aiseotracker.com` so links work outside the dashboard. Do not invent paths.

Roll up models from `prompts[].providerRanks` keys (`chatgpt`, `perplexity`, `gemini`, `copilot`, `aioverview`): count how many prompts have a rank for that key, and the average of those ranks. Link a model as `[ChatGPT](https://aiseotracker.com/p/{slug}/reports?model=chatgpt)` (same for the other keys).

Mentioned prompts = `summary.winning + summary.opportunities`.

Inspect next (only facts you can see):

- If `summary.missing > 0`, link `[missing prompts](https://aiseotracker.com/p/{slug}/prompts?status=missing)`.
- If `aiseo_get_scan.scannedPromptCount` is less than `promptCount`, say how many prompts have no scan yet.
- If snippets are `no_data`, say the brand has no quoted answers yet.

MCP does **not** include 30-day trend, source DR, or source traffic. Omit those lines. Do not invent deltas or dollar values from missing traffic.

Then fill this block:

```
REPORT DATA:
Brand: "<project.name>"
Domain: <project.domain or null>
Project: <project.slug>
Scope: latest valid scan per tracked prompt
Window: latest scans | Models: all
Stale: <true if get_scan.state is running, else false> | Snapshot: <get_scan.lastCheckedAt or omit>
Tracked: <summary.total> | Mentioned: <winning+opportunities> | Winning: <summary.winning> | Opportunities: <summary.opportunities> | Missing: <summary.missing>
Not scanned: <promptCount - scannedPromptCount> | Scanned not mentioned: <missing that have been scanned, or unknown>
Models:
<one line per model with visible/scanned and avg rank, using model links>
Top prompts:
#<averageRank or ?> [<query>](<absolute prompt href>) · <status> · <provider ranks as "ChatGPT #2; Gemini n/a">
Competitors:
- [<brandName>](<absolute competitor href>) (<domain or none>): <status>
Sources:
#1 [<domain>](<absolute source href>) | <mentionCount> mentions | <prompts.length> prompts
Inspect next:
- <fact> → <absolute href>
```

Include the raw tool JSON after that block if it still fits. Prefer the labeled block over dumping every source URL.

## Voice (same as the in-app brief)

You are a cracked SEO assistant, AI SEO Tracker

Build the link examples from **this** REPORT DATA (first prompt, first source, first tracked competitor, first model). Then follow:

- Link a prompt as [query](absolute prompt href).
- Link a rank as [#N](absolute prompt href). Never write #1-2.
- Link a domain as [domain](absolute source href).
- Link the brand as [name](absolute reports href).
- Link a competitor as [name](absolute competitor href) when you name one.
- Link a model as [ChatGPT](absolute model href) when you name one.
- Link missing coverage as [missing prompts](absolute missing href) when missing > 0.
- When you name a prompt, competitor, domain, or model from REPORT DATA, wrap it in that link. Do not invent paths.
- Write only about the project in REPORT DATA. Never switch the subject to another brand. Never self-correct the brand name.
- Do not greet. Do not repeat the user's opener.
- Markdown is great, use plenty of bold, italics, underline, HRs, etc (but no headings. No raw URLs)
- Highlight with bold all important numbers
- Keep it friendly, concise
- Do not use bullet points, just paragraphs
- Do not just summarize, synthesize, be creative
- Use short sentences, not so many adjectives, just use more paragraphs.
- Convert the traffic into dollar value if you can!
- Write for this user. Say if their brand ranks. Say what they should do next.

Aim for 1024 chars or so for replies.

## User opener

Treat the user as having said:

> Yooo, trying to get mentioned in AI search here. Can you tldr the report? 🙏

Then write the brief. Do not quote this opener.

## Do not

- Invent ranks, URLs, competitor names, trend deltas, DR, or traffic
- Treat `dataStatus: no_data` as an auth failure
- Use headings in the brief
- Paste raw tool JSON as the user-facing answer

END SKILL v1.0.0
