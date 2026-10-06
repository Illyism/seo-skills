# SEO Skills for AI Agents

Open-source SEO skills for Claude Code, Cursor, Codex and any agent that reads `SKILL.md` files. Install one and your agent can run daily SEO checks, push a page from page 2 to page 1, track AI answers, and write the copy that ranks.

Browse them at [il.ly/skills](https://il.ly/skills).

## Install

```bash
# Install the SEO autopilot skill
npx skills add Illyism/seo-skills --skill seo-autopilot

# Install all skills
npx skills add Illyism/seo-skills

# List available skills
npx skills add Illyism/seo-skills --list
```

## SEO skills

| Skill | What it does |
| ----- | ------------ |
| [seo-autopilot](seo/seo-autopilot/SKILL.md) | Daily agent that runs SEO end to end: site health checks, fixes, keyword map, articles, comparison pages, free tools, link drafts and AI answer tracking |
| [blitz-seo](seo/blitz-seo/SKILL.md) | A 30-day sprint to rank one high-value page for one money keyword |

## Copywriting skills

| Skill | What it does |
| ----- | ------------ |
| [blitz-copy](copywriting/blitz-copy/SKILL.md) | Landing pages, headlines, SEO titles, cold emails and posts using Hook → Spike → Payoff |
| [understand-customers](copywriting/understand-customers/SKILL.md) | Research customer pains and language before writing copy |

## Other skills

| Skill | Category | What it does |
| ----- | -------- | ------------ |
| [eval](code/eval/SKILL.md) | Code | Minimal 1-file AI evals for prompts, models and production functions |
| [extension-store-assets](product/extension-store-assets/SKILL.md) | Product | Chrome extension icons, store promo tiles, benefit slides and listing copy |

## Structure

Each skill is a folder with a `SKILL.md` that follows the [Agent Skills spec](https://agentskills.io):

```
<category>/<skill-name>/SKILL.md
```

## License

MIT, by [Ilias Ism](https://il.ly)
