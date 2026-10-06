# SEO Skills for AI Agents

Open-source SEO skills for Claude Code, Cursor, Codex and any agent that reads `SKILL.md` files. Install one and your agent can run daily SEO checks, fix title tags, refresh posts that slipped, buy backlinks, map search intent, and write the copy that ranks.

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
| [seo-title-optimization](seo/seo-title-optimization/SKILL.md) | Rewrite and audit title tags, H1s and meta titles for rankings and click-through rate |
| [blog-refresher](seo/blog-refresher/SKILL.md) | Refresh an existing post with a SERP gap analysis so it outranks the pages above it |
| [linkdr](seo/linkdr/SKILL.md) | Buy managed backlinks from [LinkDR](https://linkdr.com): plan a DR-tier mix for a budget and send one checkout link |

## Content skills

| Skill | What it does |
| ----- | ------------ |
| [intro](content/intro/SKILL.md) | Short blog intros with a journey teaser, matched to listicle, how-to or definition intent |
| [scribiz](content/scribiz/SKILL.md) | Transcripts, subtitles, summaries and chapters for any video with [Scribiz](https://scribiz.com), and video-to-blog workflows |

## Marketing skills

| Skill | What it does |
| ----- | ------------ |
| [customer-journey](marketing/customer-journey/SKILL.md) | Map the 5-stage awareness journey with the prompts people type into Google and ChatGPT at each stage |
| [diff-marketing](marketing/diff-marketing/SKILL.md) | Turn recent commits and merged PRs into blog posts, launch posts, changelogs and emails |

## Copywriting skills

| Skill | What it does |
| ----- | ------------ |
| [blitz-copy](copywriting/blitz-copy/SKILL.md) | Landing pages, headlines, SEO titles, cold emails and posts using Hook → Spike → Payoff |
| [understand-customers](copywriting/understand-customers/SKILL.md) | Research customer pains and language before writing copy |

Looking for developer skills like AI evals? See [Illyism/dev-skills](https://github.com/Illyism/dev-skills).

## Structure

Each skill is a folder with a `SKILL.md` that follows the [Agent Skills spec](https://agentskills.io):

```
<category>/<skill-name>/SKILL.md
```

## Free SEO checklist

Want to check a site by hand first? Get the [SEO launch checklist](https://il.ly/growth): 71 checks, each with a test you can run and a pass condition, covering crawling, page basics, speed, content, links and AI answers. Signing up also adds you to my newsletter, where I share what I learn building LinkDR, GenPPT and AI SEO Tracker. Unsubscribe anytime.

## License

MIT, by [Ilias Ism](https://il.ly)
