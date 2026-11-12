<h1 align="center">SEO Skills for Claude Code, Cursor &amp; AI Agents</h1>

<p align="center">
  <strong>30 open-source <code>SKILL.md</code> workflows that ship real SEO outputs — not 50-page audit PDFs nobody reads.</strong><br />
  Run daily repo SEO on autopilot, pull live Ahrefs &amp; DataForSEO SERP gaps, build a First-Hand Proof KB, ship honest <code>/vs/</code> pages, de-slop MDX for AI search, track ChatGPT &amp; Perplexity citations (GEO), and build DR 30–60+ backlinks.
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
  <a href="#all-30-seo-skills">All 30 Skills</a> ·
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
# Install all 30 SEO, GEO, Ahrefs/DataForSEO research, proof KB, link building & copywriting skills
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

- **Codebase diffs you can merge:** Rewritten `<title>` tags, `<h1>` alignment, MDX blog refreshes grounded in SERP gap analysis, `robots.txt` / bot-firewall middleware, verified `301` redirect maps, and new `/vs/` comparison routes.
- **First-hand proof over AI commodity fluff:** `proof-kb`, `seo-blog-images`, and `unslop-seo` replace generic filler with atomic product benchmarks, real screenshots/SVG charts, and answer-engine HTML structure.
- **Focused 30-day execution:** Instead of spreading effort across 200 low-intent keywords, `blitz-seo` concentrates technical fixes, internal links, SERP proof, and authority links onto **one money page** until it reaches Page 1.
- **Google + AI Search (GEO / AEO) together:** Map the exact prompts buyers ask ChatGPT, Perplexity, Gemini, and Google AI Overviews, measure live citation share, and ship pages and third-party placements that close missing prompt clusters.

![SEO Skills for AI Coding Agents — ship technical fixes, SERP-backed content refreshes, authority backlinks, and Google #1 rankings](assets/seo-skills-output-engine.webp)

---

## All 30 SEO Skills

### 1. Technical, Research & On-Page SEO Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`seo-autopilot`**](seo/seo-autopilot/SKILL.md) | Daily end-to-end repo SEO agent with persistent state in `seo/`: site health checks, commit fact-checking, Page-2-to-Page-1 pushes, competitor sitemap diffs, monthly keyword map, comparison pages, free tools & link drafts | *"Run `seo-autopilot` on this repo and open a PR with today's highest-leverage fix"* |
| [**`seo-roast`**](seo/seo-roast/SKILL.md) | Brutal revenue-first SEO teardown that fixes fatal crawl, `robots.txt`, programmatic, above-the-fold layout, and AI-visibility blockers in code, plus a revenue-ordered `seo/roast-roadmap.md` | *"Run `seo-roast` on our repo, fix fatal blockers in a PR, and write `seo/roast-roadmap.md`"* |
| [**`blitz-seo`**](seo/blitz-seo/SKILL.md) | Aggressive 30-day sprint to rank **one high-value page** for one money keyword using search-intent lock-in, internal link concentration, proof upgrades, and targeted authority | *"Run a 30-day `blitz-seo` sprint to push `/pricing` from #14 to Top 3"* |
| [**`ahrefs-research`**](seo/ahrefs-research/SKILL.md) | Ahrefs MCP + API v3 workflows: competitor `top-pages` gap Kanban (`seo/competitor-gaps.md`) + scaffolded routes, fake-DR filter (`seo/link-targets.csv`), subreddit pain mining, and link-insertion page matcher | *"Use `ahrefs-research` to diff our top pages against our top 5 competitors and scaffold the #1 gap"* |
| [**`dataforseo-serp`**](seo/dataforseo-serp/SKILL.md) | Live DataForSEO SERP URL-overlap keyword clustering (`seo/keyword-clusters.json`), `CPC x Volume` free-tool filter + route scaffold, AI Overview citation extraction, and pre-write SERP intent locks | *"Use `dataforseo-serp` to cluster these 40 keywords by live Top-10 URL overlap so we don't cannibalize"* |
| [**`proof-kb`**](seo/proof-kb/SKILL.md) | Atomic First-Hand Proof Knowledge Base (`seo/kb/`): `brand-ssot.md`, verifiable benchmark/customer proof cards, `[CONSENSUS] + [PROOF]` draft architecture, and `route-fact` multi-page propagation | *"Run `proof-kb` init and upgrade `content/blog/postgres-branching.mdx` with real benchmark receipts"* |
| [**`vs-and-alternatives`**](seo/vs-and-alternatives/SKILL.md) | High-converting `/vs/[competitor]`, `/[competitor]-alternative`, and micro-persona `Best [Category] for [Persona]` routes built on verified public switching triggers, 1/5/25-seat pricing math, and 10-minute switch steps | *"Use `vs-and-alternatives` to mine switching triggers and ship `/vs/billstack` wired into the footer"* |
| [**`internal-linking`**](seo/internal-linking/SKILL.md) | Reverse internal linking ("traffic-to-money routing"): audits the repo link graph (`scripts/internal-link-graph.mjs`) and injects upper-40% contextual anchors + prefilled tool callouts from top blog posts into `/pricing`, `/vs/*`, and `/tools/*` | *"Run `internal-linking` to eliminate orphan money pages and route blog equity to `/pricing`"* |
| [**`domain-migration`**](seo/domain-migration/SKILL.md) | Zero-traffic-loss domain rebrand, subdomain-to-subfolder merge, or URL consolidation: full URL + backlink union, 1-hop `301` config, `scripts/verify-redirects.sh`, schema `alternateName`, and `seo/backlink-transfer-emails.md` | *"Run `domain-migration` to move `blog.acme.com` into `acme.com/blog` with verified 1-to-1 redirects"* |
| [**`seo-title-optimization`**](seo/seo-title-optimization/SKILL.md) | Bulk title tag, MDX frontmatter `title`, and `<h1>` rewrites calibrated against live SERP winners, pixel/character truncation limits, and click-through rate (CTR) | *"Audit every page title in `app/` and `content/blog/` for CTR and SERP truncation"* |
| [**`blog-refresher`**](seo/blog-refresher/SKILL.md) | 6-phase content refresh and SERP gap analysis that compares a slipping post against current Top-10 pages and rewrites weak sections while preserving your voice | *"Use `blog-refresher` on `content/blog/best-crm.mdx` so it outranks the Top 3"* |
| [**`block-ai-scrapers`**](seo/block-ai-scrapers/SKILL.md) | Multi-layer bot firewall that blocks AI coding agents, `WebFetch`, `curl`, and headless scrapers from burning API/DB credits while keeping verified `Googlebot` indexing intact and turning blocked scrapes into product links | *"Add `block-ai-scrapers` to protect our `/directory` dataset routes without hurting Googlebot"* |

### 2. AI Search & GEO (Generative Engine Optimization) Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`customer-journey`**](marketing/customer-journey/SKILL.md) | 5-stage buyer awareness map pairing traditional Google keywords with the conversational prompts buyers type into ChatGPT, Claude, and Perplexity at each stage | *"Map the 5-stage `customer-journey` and AI search prompts for our B2B analytics SaaS"* |
| [**`aiseotracker`**](seo/aiseotracker/SKILL.md) | One-time OAuth MCP setup (`https://aiseotracker.com/api/agent/mcp`) and project wiring for [AI SEO Tracker](https://aiseotracker.com) to track brand mentions, citations, and competitors across ChatGPT, Perplexity, Gemini, Copilot & Google AI Overviews | *"Connect `aiseotracker` and check how ChatGPT and Perplexity rank our domain"* |
| [**`ai-seo-report`**](seo/ai-seo-report/SKILL.md) | Executive AI visibility brief synthesized from live prompt scans, cited competitor URLs, and share-of-voice shifts — zero raw JSON dumps | *"Give me this week's `ai-seo-report` brief and tell me why competitors beat us in ChatGPT"* |
| [**`content-coverage`**](seo/content-coverage/SKILL.md) | Evidence-backed content plan and article drafts targeting the exact AI search prompt clusters where competitors get cited and your site is missing | *"Run `content-coverage` to plan and draft pages for our missing Perplexity & ChatGPT prompts"* |
| [**`reddit-serp`**](seo/reddit-serp/SKILL.md) | Finds unlocked Reddit threads that already rank Page 1 on Google or get cited by AI Overviews and ChatGPT, checks subreddit rules via JSON, and writes `seo/reddit-serp-queue.md` with practitioner replies that survive moderation | *"Run `reddit-serp` to find unlocked Page-1 Reddit threads for our category and draft replies"* |

### 3. Off-Page SEO, Link Building & Directory Submissions

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`directory-submissions`**](seo/directory-submissions/SKILL.md) | Autonomous startup, AI tool, MCP registry & GitHub Awesome directory submission workflow: builds `submission-manifest.json`, cascades 1 repo across 15+ MCP/agent registries, and works through 50 high-DR launchpads ([850+ directory database](https://linkdr.com/resources/directories)) | *"Run `directory-submissions` to generate our manifest and submit across Wave 1–3 directories"* |
| [**`linkdr`**](seo/linkdr/SKILL.md) | Managed authority link-building planner for [LinkDR](https://linkdr.com): calculates a DR 30+ to DR 60+ backlink, niche-edit, or listicle mix for your budget and returns a single approval-gated checkout link | *"Plan a $1,000 DR 40–50+ backlink campaign for our SaaS homepage using `linkdr`"* |
| [**`honest-link-outreach`**](seo/honest-link-outreach/SKILL.md) | Vetted backlink outreach batch (`seo/outreach-batch-YYYY-MM-DD.md`) with a `SEND / CUT` table targeting ranking `/blog`, `/guides`, and `/docs` URLs, Ask-First structure, and a 7-axis Anti-Template Variety Matrix | *"Run `honest-link-outreach` on these 8 partner and blog domains and write the batch file"* |
| [**`awesome-tools`**](seo/awesome-tools/SKILL.md) | Agent submission workflow for [Awesome Tools](https://awesome.tools) via Streamable HTTP MCP (`https://awesome.tools/mcp`), JSON API, or WebMCP to earn a verified `dofollow` SaaS directory backlink | *"Submit our app to `awesome-tools` and check eligibility for the free dofollow listing"* |

### 4. Content & Shipped-Code Distribution Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`unslop-seo`**](content/unslop-seo/SKILL.md) | 3-phase in-place editorial de-slopping and Answer-Engine (GEO) HTML pass: grounds vague claims in `seo/kb/brand-ssot.md`, enforces a 40-word direct opening answer and question `<h2>` tags, and strips 20 AI slop patterns | *"Run `unslop-seo` on `content/blog/ci-guide.mdx` and verify the slop check exits 0"* |
| [**`seo-blog-images`**](content/seo-blog-images/SKILL.md) | Plans, generates, compresses (`scripts/seo-image.mjs`), visually verifies, and wires high-CTR cover images, Playwright screenshots, and deterministic SVG charts into posts with strict filename, size (`<= 220 KB`), and `80–160` char `alt` checks | *"Use `seo-blog-images` to add a cover image and benchmark chart to `content/blog/benchmark.mdx`"* |
| [**`youtube-seo`**](content/youtube-seo/SKILL.md) | Turns a demo, tutorial, or `.srt` transcript into 2 YouTube title options (with char counts), a Google Key-Moments `00:00` description (`>= 10s` chapters), X/LinkedIn launch posts, and a `VideoObject` JSON-LD blog embed | *"Run `youtube-seo` on `demo.srt` and embed the `VideoObject` schema into our matching blog post"* |
| [**`parasite-and-pr`**](marketing/parasite-and-pr/SKILL.md) | Ready-to-publish third-party syndication bundle (`marketing/distribution/<slug>/`): privacy-audited wire press release (zero personal/LLC leaks across 500+ scrapers), canonicalized Dev.to draft, LinkedIn/parasite article, and verification checklist | *"Run `parasite-and-pr` for our 2026 latency benchmark so ChatGPT and Google triangulate it fast"* |
| [**`intro`**](content/intro/SKILL.md) | High-retention blog introductions with a proof hook and journey teaser tailored to listicle, how-to, comparison, or definition search intent (includes [real examples](content/intro/examples.md)) | *"Rewrite the opening 80 words of this post using the `intro` skill for listicle intent"* |
| [**`scribiz`**](content/scribiz/SKILL.md) | Video, YouTube, podcast, and screen-recording transcription with speaker labels, on-screen OCR text, chapters, and video-to-SEO-blog conversion via [Scribiz](https://scribiz.com) (`https://scribiz.com/mcp`) | *"Transcribe this YouTube demo with `scribiz` and turn it into a step-by-step tutorial post"* |
| [**`diff-marketing`**](marketing/diff-marketing/SKILL.md) | Reads recent `git log` commits and merged PRs to ship customer-facing changelog entries, SEO feature articles, launch tweets, and release emails based on what actually shipped | *"Read the last 2 weeks of git commits with `diff-marketing` and draft 3 blog/launch angles"* |

### 5. Conversion Copywriting Skills

| Skill | What it ships | Example prompt |
| --- | --- | --- |
| [**`understand-customers`**](copywriting/understand-customers/SKILL.md) | Deep buyer-psychology brief uncovering customer pains, switching triggers, objections, and exact verbatim phrasing before writing a word of copy | *"Run `understand-customers` for indie Next.js founders tired of slow CI builds"* |
| [**`blitz-copy`**](copywriting/blitz-copy/SKILL.md) | High-converting landing pages, hero headlines, cold outreach emails, social hooks, and SERP titles built on the **Hook → Spike → Payoff** dopamine copywriting system | *"Rewrite our hero section and pricing CTAs using `blitz-copy`"* |

> Looking for engineering skills like AI evals and Chrome Web Store release pipelines? Check out **[Illyism/dev-skills](https://github.com/Illyism/dev-skills)**.

---

## End-to-End SEO Workflows

Skills compose naturally inside Claude Code, Cursor, and Codex. Six battle-tested chains:

1. **Ship a Proof-Backed Post That Ranks Top 3 & Earns AI Citations**
   `dataforseo-serp` *(cluster keywords by live URL overlap & lock SERP intent)* → `proof-kb` *(inject atomic first-hand benchmarks & write the receipt intro last)* → `seo-blog-images` *(add real screenshots, deterministic SVG charts & cover WebP)* → `unslop-seo` *(strip AI tells & enforce answer-engine HTML)* → `internal-linking` *(route upper-40% anchors to money pages)* → `parasite-and-pr` *(syndicate across wires, Dev.to & LinkedIn for 48h triangulation)*.
2. **Capture High-Intent Competitor Switchers Across Google, Reddit & LLMs**
   `ahrefs-research` *(diff competitor `top-pages` & filter real backlinks)* → `vs-and-alternatives` *(mine verified switching triggers, 1/5/25-seat pricing math & ship `/vs/[competitor]` + persona listicles)* → `reddit-serp` *(find unlocked Page-1 Reddit threads & draft practitioner replies)* → `honest-link-outreach` *(pitch varied, ask-first emails to ranking partner & editorial guides)*.
3. **Push a Page-2 URL into the Google Top 3**
   `seo-title-optimization` *(fix CTR & SERP intent)* → `blog-refresher` *(close Top-10 entity & proof gaps)* → `intro` *(cut pogo-sticking in the first 80 words)* → `linkdr` *(point 2–4 DR 40+ contextual links at the refreshed URL)*.
4. **Win Citations in ChatGPT, Perplexity & Google AI Overviews (GEO)**
   `customer-journey` *(map buyer prompts across 5 stages)* → `aiseotracker` *(scan live AI answers)* → `ai-seo-report` *(spot third-party listicles & missing topics)* → `content-coverage` *(ship pages covering unowned prompt clusters)*.
5. **Launch a New Product from DR 0**
   `understand-customers` *(extract buyer language)* → `blitz-copy` *(write the landing page)* → `directory-submissions` & `awesome-tools` *(cascade across 15+ MCP registries & 50+ high-DR directories)* → `blitz-seo` *(run a focused 30-day sprint on your #1 commercial keyword)*.
6. **Autonomous Daily Repo SEO**
   Drop `seo-autopilot` on a daily schedule so your coding agent checks site health, verifies product claims against recent commits, refreshes decaying posts, and opens reviewable PRs — paired with `diff-marketing` every Friday to turn shipped code into distribution.

---

## Live SEO Data via MCP Servers

A `SKILL.md` gives your agent the **methodology**. Pairing it with a [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server (preconfigured in [`.mcp.json`](.mcp.json)) gives your agent **live search, citation, directory, and transcript data**:

| Server / Integration | Endpoint / Repo | Live capabilities |
| --- | --- | --- |
| **[AI SEO Tracker MCP](https://aiseotracker.com)** | `https://aiseotracker.com/api/agent/mcp` ([`Illyism/aiseotracker-mcp`](https://github.com/Illyism/aiseotracker-mcp)) | Live prompt rankings, cited source URLs, competitor share of voice & weekly scan diffs across ChatGPT, Perplexity, Gemini, Copilot & Google AIO |
| **[Scribiz MCP](https://scribiz.com)** | `https://scribiz.com/mcp` | Transcribe YouTube videos, podcasts, and recordings with speaker diarization, screen OCR, summaries & `00:00` chapters |
| **[Awesome Tools MCP](https://awesome.tools)** | `https://awesome.tools/mcp` ([`Illyism/awesome-tools-mcp`](https://github.com/Illyism/awesome-tools-mcp)) | Search curated SaaS & AI tools, submit products for `dofollow` directory listings, and verify badge backlinks |
| **[LinkDR Agent Skill](https://linkdr.com)** | [`https://linkdr.com/SKILL.md`](https://linkdr.com/SKILL.md) | Plan vetted DR 30–60+ contextual backlinks, link insertions, and SaaS listicle placements with a single approval-gated `/agent/checkout` link |
| **[GenPPT MCP](https://genppt.com)** | [`Illyism/genppt-mcp`](https://github.com/Illyism/genppt-mcp) | Turn SEO audits, `seo-roast` roadmaps, and competitor gap analyses into designed PowerPoint (`.pptx`) & PDF slide decks from your IDE |

---

## Repository Structure

Every skill lives in `<category>/<skill-name>/SKILL.md` with clean YAML frontmatter (`name`, `description`, `metadata`) and zero build step:

```text
seo-skills/
├── seo/
│   ├── ahrefs-research/SKILL.md
│   ├── ai-seo-report/SKILL.md
│   ├── aiseotracker/SKILL.md
│   ├── awesome-tools/SKILL.md
│   ├── blitz-seo/SKILL.md
│   ├── block-ai-scrapers/SKILL.md
│   ├── blog-refresher/SKILL.md
│   ├── content-coverage/SKILL.md
│   ├── dataforseo-serp/SKILL.md
│   ├── directory-submissions/SKILL.md
│   ├── domain-migration/SKILL.md
│   ├── honest-link-outreach/SKILL.md
│   ├── internal-linking/SKILL.md
│   ├── linkdr/SKILL.md
│   ├── proof-kb/SKILL.md
│   ├── reddit-serp/SKILL.md
│   ├── seo-autopilot/SKILL.md
│   ├── seo-roast/SKILL.md
│   ├── seo-title-optimization/SKILL.md
│   └── vs-and-alternatives/SKILL.md
├── content/
│   ├── intro/SKILL.md
│   ├── scribiz/SKILL.md
│   ├── seo-blog-images/SKILL.md
│   ├── unslop-seo/SKILL.md
│   └── youtube-seo/SKILL.md
├── marketing/
│   ├── customer-journey/SKILL.md
│   ├── diff-marketing/SKILL.md
│   └── parasite-and-pr/SKILL.md
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
1. **SERP Clustering, Competitor Research & Title Engineering** (`dataforseo-serp`, `ahrefs-research`, `seo-title-optimization`, `customer-journey`)
2. **First-Hand Proof Content, Visuals & De-Slopping** (`proof-kb`, `seo-blog-images`, `unslop-seo`, `blog-refresher`, `intro`, `scribiz`, `youtube-seo`)
3. **Technical Crawlability, Internal Routing & Migrations** (`seo-autopilot`, `seo-roast`, `internal-linking`, `domain-migration`, `block-ai-scrapers`)
4. **Authority Backlinks, Outreach & Syndication** (`directory-submissions`, `linkdr`, `honest-link-outreach`, `parasite-and-pr`, `awesome-tools`)
5. **Generative Engine Optimization (GEO / AEO) & Comparison Pages** (`aiseotracker`, `ai-seo-report`, `content-coverage`, `vs-and-alternatives`, `reddit-serp`)

---

## License

MIT © [Ilias Ism](https://il.ly)
