<h1 align="center">SEO Skills for Claude Code, Cursor &amp; AI Agents</h1>

<p align="center">
  <strong>17 open-source <code>SKILL.md</code> workflows that ship real SEO outputs — not 50-page audit PDFs nobody reads.</strong><br />
  Run daily repo SEO on autopilot, rewrite title tags from live SERPs, refresh slipping blog posts, track ChatGPT &amp; Perplexity citations (GEO), block AI scrapers, repurpose videos into posts, and build DR 30–60+ backlinks.
</p>

<p align="center">
  <a href="https://github.com/Illyism/seo-skills/stargazers"><img src="https://img.shields.io/github/stars/Illyism/seo-skills?style=flat-square&logo=github&color=eab308" alt="GitHub Stars" /></a>
  <a href="https://agentskills.io"><img src="https://img.shields.io/badge/spec-SKILL.md%20(Agent%20Skills)-2563eb?style=flat-square" alt="Agent Skills Specification" /></a>
  <a href="https://il.ly/skills"><img src="https://img.shields.io/badge/browse-il.ly%2Fskills-10b981?style=flat-square" alt="Browse SEO Skills at il.ly/skills" /></a>
  <a href="https://github.com/Illyism/seo-skills/blob/main/README.md#license"><img src="https://img.shields.io/badge/license-MIT-zinc?style=flat-square" alt="MIT License" /></a>
</p>

<p align="center">
  <a href="https://il.ly/skills">Browse Web Catalog</a> ·
  <a href="#install">Quick Install</a> ·
  <a href="#all-17-seo-skills">All 17 Skills</a> ·
  <a href="#end-to-end-seo-workflows">Workflows</a> ·
  <a href="#live-seo-data-via-mcp-servers">MCP Servers</a> ·
  <a href="#sponsors--seo-growth-stack">Sponsors</a> ·
  <a href="#faq">FAQ</a>
</p>

![SEO Skills for Claude Code, Cursor, and OpenAI Codex — installable SKILL.md workflows that turn AI coding agents into Google #1 rankings](assets/seo-skills-hero.jpg)

---

## Install

Install every skill in one command using the [`skills`](https://www.npmjs.com/package/skills) CLI, or install individual skills on demand:

```bash
# Install all 17 SEO, GEO, directory submission, link building & copywriting skills
npx skills add Illyism/seo-skills

# Install a single skill (for example, daily autonomous repo SEO)
npx skills add Illyism/seo-skills --skill seo-autopilot

# List every available skill in this repository
npx skills add Illyism/seo-skills --list
```

### Works Across Every Coding Agent & AI Chat App

Each skill is a self-contained folder with a plain Markdown `SKILL.md` following the open [Agent Skills specification](https://agentskills.io). Your agent loads only the short `name` and `description` at startup and opens the full instructions when your prompt matches — keeping your context window fast and clean.

| Environment | Where `SKILL.md` lives | How to install |
| --- | --- | --- |
| **Claude Code** | `.claude/skills/` or `~/.claude/skills/` | `npx skills add Illyism/seo-skills -a claude-code` |
| **Cursor** | `.cursor/skills/` or `.agents/skills/` | `npx skills add Illyism/seo-skills -a cursor` |
| **OpenAI Codex / OpenCode** | `.agents/skills/` | `npx skills add Illyism/seo-skills` |
| **Windsurf / Cline / Roo Code** | `.agents/skills/` | `npx skills add Illyism/seo-skills` |
| **ChatGPT, Claude.ai, Perplexity, Grok** | Paste or attach raw Markdown | Copy any skill directly at **[il.ly/skills](https://il.ly/skills)** |

---

## Why Output-First SEO Skills?

Most "AI SEO prompt packs" generate giant checklists and health scores that sit in a folder forever.

Every skill in `Illyism/seo-skills` is built to **end in a concrete, shippable output** inside your repository or marketing workflow:

- **Codebase diffs you can merge:** Rewritten `<title>` tags, `<h1>` alignment, MDX blog refreshes grounded in SERP gap analysis, `robots.txt` / bot-firewall middleware, and new comparison pages.
- **Focused 30-day execution:** Instead of spreading effort across 200 low-intent keywords, `blitz-seo` concentrates technical fixes, internal links, SERP proof, and authority links onto **one money page** until it reaches Page 1.
- **Google + AI Search (GEO / AEO) together:** Map the exact prompts buyers ask ChatGPT, Perplexity, Gemini, and Google AI Overviews, measure live citation share, and ship pages that close missing prompt clusters.

![SEO Skills for AI Coding Agents — ship technical fixes, SERP-backed content refreshes, authority backlinks, and Google #1 rankings](assets/seo-skills-output-engine.webp)

---

## All 17 SEO Skills

### 1. Technical & On-Page SEO Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`seo-autopilot`**](seo/seo-autopilot/SKILL.md) | Daily end-to-end repo SEO agent with persistent state in `seo/`: site health checks, commit fact-checking, Page-2-to-Page-1 pushes, competitor sitemap diffs, monthly keyword map, comparison pages, free tools & link drafts | *"Run `seo-autopilot` on this repo and open a PR with today's highest-leverage fix"* |
| [**`blitz-seo`**](seo/blitz-seo/SKILL.md) | Aggressive 30-day sprint to rank **one high-value page** for one money keyword using search-intent lock-in, internal link concentration, proof upgrades, and targeted authority | *"Run a 30-day `blitz-seo` sprint to push `/pricing` from #14 to Top 3"* |
| [**`seo-title-optimization`**](seo/seo-title-optimization/SKILL.md) | Bulk title tag, MDX frontmatter `title`, and `<h1>` rewrites calibrated against live SERP winners, pixel/character truncation limits, and click-through rate (CTR) | *"Audit every page title in `app/` and `content/blog/` for CTR and SERP truncation"* |
| [**`blog-refresher`**](seo/blog-refresher/SKILL.md) | 6-phase content refresh and SERP gap analysis that compares a slipping post against current Top-10 pages and rewrites weak sections while preserving your voice | *"Use `blog-refresher` on `content/blog/best-crm.mdx` so it outranks the Top 3"* |
| [**`block-ai-scrapers`**](seo/block-ai-scrapers/SKILL.md) | Multi-layer bot firewall that blocks AI coding agents, `WebFetch`, `curl`, and headless scrapers from burning API/DB credits while keeping verified `Googlebot` indexing intact and turning blocked scrapes into product links | *"Add `block-ai-scrapers` to protect our `/directory` dataset routes without hurting Googlebot"* |

### 2. AI Search & GEO (Generative Engine Optimization) Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`customer-journey`**](marketing/customer-journey/SKILL.md) | 5-stage buyer awareness map pairing traditional Google keywords with the conversational prompts buyers type into ChatGPT, Claude, and Perplexity at each stage | *"Map the 5-stage `customer-journey` and AI search prompts for our B2B analytics SaaS"* |
| [**`aiseotracker`**](seo/aiseotracker/SKILL.md) | One-time OAuth MCP setup and project wiring for [AI SEO Tracker](https://aiseotracker.com) to track brand mentions, citations, and competitors across ChatGPT, Perplexity, Gemini, Copilot & Google AI Overviews | *"Connect `aiseotracker` and check how ChatGPT and Perplexity rank our domain"* |
| [**`ai-seo-report`**](seo/ai-seo-report/SKILL.md) | Executive AI visibility brief synthesized from live prompt scans, cited competitor URLs, and share-of-voice shifts — zero raw JSON dumps | *"Give me this week's `ai-seo-report` brief and tell me why competitors beat us in ChatGPT"* |
| [**`content-coverage`**](seo/content-coverage/SKILL.md) | Evidence-backed content plan and article drafts targeting the exact AI search prompt clusters where competitors get cited and your site is missing | *"Run `content-coverage` to plan and draft pages for our missing Perplexity & ChatGPT prompts"* |

### 3. Off-Page SEO, Link Building & Directory Submissions

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`directory-submissions`**](seo/directory-submissions/SKILL.md) | Autonomous startup, AI tool, MCP registry & GitHub Awesome directory submission workflow: builds `submission-manifest.json`, cascades 1 repo across 15+ MCP/agent registries, and works through 50 high-DR launchpads ([850+ directory database](https://linkdr.com/resources/directories)) | *"Run `directory-submissions` to generate our manifest and submit across Wave 1–3 directories"* |
| [**`linkdr`**](seo/linkdr/SKILL.md) | Managed authority link-building planner for [LinkDR](https://linkdr.com): calculates a DR 30+ to DR 60+ backlink, niche-edit, or listicle mix for your budget and returns a single approval-gated checkout link | *"Plan a $1,000 DR 40–50+ backlink campaign for our SaaS homepage using `linkdr`"* |
| [**`awesome-tools`**](seo/awesome-tools/SKILL.md) | Agent submission workflow for [Awesome Tools](https://awesome.tools) via JSON API or WebMCP to earn a verified `dofollow` SaaS directory backlink (free reciprocal path or instant Featured Launch) | *"Submit our app to `awesome-tools` and check eligibility for the free dofollow listing"* |

### 4. Content & Shipped-Code Distribution Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`intro`**](content/intro/SKILL.md) | High-retention blog introductions with a proof hook and journey teaser tailored to listicle, how-to, comparison, or definition search intent (includes [real examples](content/intro/examples.md)) | *"Rewrite the opening 80 words of this post using the `intro` skill for listicle intent"* |
| [**`scribiz`**](content/scribiz/SKILL.md) | Video, YouTube, podcast, and screen-recording transcription with speaker labels, on-screen OCR text, chapters, and video-to-SEO-blog conversion via [Scribiz](https://scribiz.com) | *"Transcribe this YouTube demo with `scribiz` and turn it into a step-by-step tutorial post"* |
| [**`diff-marketing`**](marketing/diff-marketing/SKILL.md) | Reads recent `git log` commits and merged PRs to ship customer-facing changelog entries, SEO feature articles, launch tweets, and release emails based on what actually shipped | *"Read the last 2 weeks of git commits with `diff-marketing` and draft 3 blog/launch angles"* |

### 5. Conversion Copywriting Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`understand-customers`**](copywriting/understand-customers/SKILL.md) | Deep buyer-psychology brief uncovering customer pains, switching triggers, objections, and exact verbatim phrasing before writing a word of copy | *"Run `understand-customers` for indie Next.js founders tired of slow CI builds"* |
| [**`blitz-copy`**](copywriting/blitz-copy/SKILL.md) | High-converting landing pages, hero headlines, cold outreach emails, social hooks, and SERP titles built on the **Hook → Spike → Payoff** dopamine copywriting system | *"Rewrite our hero section and pricing CTAs using `blitz-copy`"* |

> Looking for engineering skills like AI evals and Chrome Web Store release pipelines? Check out **[Illyism/dev-skills](https://github.com/Illyism/dev-skills)**.

---

## End-to-End SEO Workflows

Skills compose naturally inside Claude Code, Cursor, and Codex. Four battle-tested chains:

1. **Push a Page-2 URL into the Google Top 3**
   `seo-title-optimization` *(fix CTR & SERP intent)* → `blog-refresher` *(close Top-10 entity & proof gaps)* → `intro` *(cut pogo-sticking in the first 80 words)* → `linkdr` *(point 2–4 DR 40+ contextual links at the refreshed URL)*.
2. **Win Citations in ChatGPT, Perplexity & Google AI Overviews (GEO)**
   `customer-journey` *(map buyer prompts across 5 stages)* → `aiseotracker` *(scan live AI answers)* → `ai-seo-report` *(spot third-party listicles & missing topics)* → `content-coverage` *(ship pages covering unowned prompt clusters)*.
3. **Launch a New Product from DR 0**
   `understand-customers` *(extract buyer language)* → `blitz-copy` *(write the landing page)* → `directory-submissions` & `awesome-tools` *(cascade across 15+ MCP registries & 50+ high-DR directories)* → `blitz-seo` *(run a focused 30-day sprint on your #1 commercial keyword)*.
4. **Autonomous Daily Repo SEO**
   Drop `seo-autopilot` on a daily schedule so your coding agent checks site health, verifies product claims against recent commits, refreshes decaying posts, and opens reviewable PRs — paired with `diff-marketing` every Friday to turn shipped code into distribution.

---

## Live SEO Data via MCP Servers

A `SKILL.md` gives your agent the **methodology**. Pairing it with a [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server gives your agent **live search, backlink, citation, and transcript data**:

| MCP Server | Live capabilities | Setup repo |
| --- | --- | --- |
| **[LinkDR MCP](https://linkdr.com)** | Domain Rating & backlink research, live Google SERP snapshots, keyword discovery, AI visibility checks & approval-gated link orders | [`Illyism/linkdr-mcp`](https://github.com/Illyism/linkdr-mcp) |
| **[AI SEO Tracker MCP](https://aiseotracker.com)** | Live prompt rankings, cited source URLs, competitor share of voice & weekly scan diffs across ChatGPT, Perplexity, Gemini, Copilot & Google AIO | [`Illyism/aiseotracker-mcp`](https://github.com/Illyism/aiseotracker-mcp) |
| **[Awesome Tools MCP](https://awesome.tools)** | Search curated SaaS & AI tools, submit products for `dofollow` directory listings, and verify badge backlinks | [`Illyism/awesome-tools-mcp`](https://github.com/Illyism/awesome-tools-mcp) |
| **[Scribiz MCP](https://scribiz.com)** | Transcribe YouTube videos, podcasts, and recordings with speaker diarization, screen OCR, summaries & chapters | [`scribiz.com/mcp`](https://scribiz.com) |
| **[GenPPT MCP](https://genppt.com)** | Turn SEO audits, strategy docs, and PDFs into designed PowerPoint (`.pptx`) & PDF slide decks from your IDE | [`Illyism/genppt-mcp`](https://github.com/Illyism/genppt-mcp) |

---

## Repository Structure

Every skill lives in `<category>/<skill-name>/SKILL.md` with clean YAML frontmatter (`name`, `description`, `metadata`) and zero build step:

```text
seo-skills/
├── seo/
│   ├── seo-autopilot/SKILL.md
│   ├── blitz-seo/SKILL.md
│   ├── seo-title-optimization/SKILL.md
│   ├── blog-refresher/SKILL.md
│   ├── block-ai-scrapers/SKILL.md
│   ├── aiseotracker/SKILL.md
│   ├── ai-seo-report/SKILL.md
│   ├── content-coverage/SKILL.md
│   ├── directory-submissions/SKILL.md
│   ├── linkdr/SKILL.md
│   └── awesome-tools/SKILL.md
├── content/
│   ├── intro/SKILL.md
│   └── scribiz/SKILL.md
├── marketing/
│   ├── customer-journey/SKILL.md
│   └── diff-marketing/SKILL.md
└── copywriting/
    ├── blitz-copy/SKILL.md
    └── understand-customers/SKILL.md
```

---

## Free 71-Point SEO Checklist & 850+ Startup Directories

Launching a new product or pushing a domain past DR 30? Pair these skills with two companion playbooks:

- **[71-Point SEO Launch Checklist & Growth Playbook (`il.ly/growth`)](https://il.ly/growth)** — Free **71 pass/fail checks** (each with an exact test command), `seo-autopilot` repo setup, and the **50-directory 5-wave launch tracker** (`il.ly/growth/directories`).
- **[850+ Startup, AI Tool & MCP Directories (`linkdr.com/resources/directories`)](https://linkdr.com/resources/directories)** — Filter **856+ verified launchpads, software review sites, MCP registries, and GitHub Awesome lists** across 14 categories by Domain Rating (DR), monthly traffic, free vs. paid pricing, and `dofollow`/`nofollow` link type — complete with direct submit URLs and a copy-paste Claude Code / Cursor submission prompt.

---

## Sponsors & SEO Growth Stack

`Illyism/seo-skills` is MIT-licensed and maintained by **[Ilias Ism](https://il.ly)**, supported by the SEO & creator products below:

| Product | What it does |
| --- | --- |
| <img src="https://www.google.com/s2/favicons?domain=linkdr.com&sz=32" width="16" height="16" alt="LinkDR" /> **[LinkDR](https://linkdr.com)** | **AI Link Building & Authority Backlinks** — Order vetted DR 30–60+ contextual backlinks, link insertions, and SaaS listicle placements. Approve every publisher site before placement (`15% off` monthly plans). |
| <img src="https://www.google.com/s2/favicons?domain=aiseotracker.com&sz=32" width="16" height="16" alt="AI SEO Tracker" /> **[AI SEO Tracker](https://aiseotracker.com)** | **AI Search & GEO Visibility Tracking** — Track whether ChatGPT, Perplexity, Gemini, Copilot, and Google AI Overviews cite your brand, which competitor pages win citations, and which prompts to target next. |
| <img src="https://www.google.com/s2/favicons?domain=genppt.com&sz=32" width="16" height="16" alt="GenPPT" /> **[GenPPT](https://genppt.com)** | **AI Presentation & Pitch Deck Maker** — Turn messy notes, client SEO reports, and financial PDFs into clean, editable PowerPoint (`.pptx`) and Google Slides decks in minutes. |
| <img src="https://www.google.com/s2/favicons?domain=scribiz.com&sz=32" width="16" height="16" alt="Scribiz" /> **[Scribiz](https://scribiz.com)** | **Video & Audio Transcription + Screen OCR** — Turn YouTube videos, calls, and demos into speaker-labeled transcripts, on-screen code/slide OCR, chapters, and SEO blog drafts (`Web`, `macOS`, `Android`, `CLI`). |
| <img src="https://www.google.com/s2/favicons?domain=awesome.tools&sz=32" width="16" height="16" alt="Awesome Tools" /> **[Awesome Tools](https://awesome.tools)** | **Curated SaaS & Developer Tools Directory** — Discover hand-picked software tools or submit your own product to earn a verified `dofollow` backlink. |
| <img src="https://www.google.com/s2/favicons?domain=seoroast.com&sz=32" width="16" height="16" alt="SEO Roast" /> **[SEO Roast](https://seoroast.com)** | **20-Minute Video SEO Teardown** — Get a blunt, recorded screen-share audit of your site's rankings, SERP title leaks, backlink gaps, and 90-day growth plan. |
| <img src="https://www.google.com/s2/favicons?domain=xoutlier.com&sz=32" width="16" height="16" alt="XOutlier" /> **[XOutlier](https://xoutlier.com)** | **Viral X Outlier Finder (Free Chrome Extension)** — Spot outlier posts and proven hooks across `390,000+` creators right inside X to distribute what you ship. |

---

## FAQ

### What are SEO skills for AI agents?
An **SEO skill** is a portable folder containing a `SKILL.md` file with structured instructions, quality gates, and output templates that teach coding and research agents (Claude Code, Cursor, OpenAI Codex, OpenCode, Windsurf) how to execute specialized search engine optimization workflows — from technical audits and title tag rewrites to content refreshes, GEO citation tracking, and backlink planning.

### How do I use these SEO skills in Claude Code or Cursor?
Run `npx skills add Illyism/seo-skills` in your project root (or globally). Claude Code and Cursor automatically index each skill's `name` and `description` and load the full `SKILL.md` whenever you ask for an SEO sprint, title audit, blog refresh, scraper block, or backlink plan. You can also invoke any skill explicitly by name (for example, *"Use `blog-refresher` on `content/blog/post.mdx`"*).

### Can I use these skills in ChatGPT, Claude.ai, or Perplexity without a terminal?
Yes. Open **[il.ly/skills](https://il.ly/skills)**, click any skill, and hit **Copy prompt** (or open its raw `SKILL.md`) to paste directly into ChatGPT, Claude Desktop, Perplexity, or Grok.

### What is the difference between an SEO skill (`SKILL.md`) and an SEO MCP server?
A **skill (`SKILL.md`)** teaches the agent *how to do the job* (the step-by-step methodology, SERP rules, formatting, and approval gates). An **MCP server** connects the agent to *live external data and actions* (Google Search Console metrics, live SERPs, AI citation scans, video transcripts, or backlink checkouts). Using both together gives your agent live search data plus senior-level SEO judgment.

### Which core SEO skills matter most for ranking in 2026?
Modern search visibility across Google and AI answer engines comes down to five compounding skills — all covered in this repo:
1. **Search Intent & SERP Title Engineering** (`seo-title-optimization`, `customer-journey`)
2. **First-Hand Proof Content & Decay Refreshes** (`blog-refresher`, `intro`, `scribiz`)
3. **Technical Crawlability & Bot Hygiene** (`seo-autopilot`, `block-ai-scrapers`)
4. **Authority Off-Page Backlinks & Directory Distribution** (`directory-submissions`, `linkdr`, `awesome-tools`)
5. **Generative Engine Optimization (GEO / AEO)** (`aiseotracker`, `ai-seo-report`, `content-coverage`)

---

## License

MIT © [Ilias Ism](https://il.ly)
