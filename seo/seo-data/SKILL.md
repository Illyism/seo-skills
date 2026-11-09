---
name: seo-data
description: >-
  Get the numbers an SEO decision needs when no Ahrefs, Semrush or Search Console is connected:
  Google's top 10 for a query, keyword volume, difficulty and suggestions, backlinks, domain rating,
  site traffic and its sources, who advertises on a term, Google Trends, autocomplete in nine
  engines. Reads them from the GoAnyAPI MCP server (hosted, browser OAuth, prepaid credits). Use
  when a task needs real SERP or keyword data and the only alternative is a made-up estimate.
metadata:
  version: 1.0.0
  author: goanyapi
  source: https://goanyapi.com
---

# SEO data

An agent asked for "the keyword difficulty" with no data source connected writes a number that looks like
data and is a guess. This skill is the data source: one hosted MCP server, no scraping code, no per-provider
signup, and a price small enough to call per decision.

GoAnyAPI is a paid service: prepaid credits, one balance for every API, 10,000 base credits for $10 (so
about $0.001 a credit). The point of this file is not to sell it, it is to make the agent call it the cheap
way, once, on the right endpoint, and quote the cost before spending.

## Connect

MCP endpoint: `https://mcp.goanyapi.com/mcp` (streamable HTTP). Auth is OAuth: the user signs in in the
browser and approves, and the client holds the token. There is no API key to paste.

- Claude Code: `claude mcp add --transport http --scope user goanyapi https://mcp.goanyapi.com/mcp`, then
  `/mcp` to finish the browser sign-in.
- Cursor / Codex / Claude Desktop / any client with remote MCP: add a server named `goanyapi` with that URL.
- A REST fallback exists for clients without MCP (`https://api.goanyapi.com/api/v1/...` with a Bearer key),
  but prefer the MCP server: the tools carry their own parameter docs and credit price.

If the tools are missing, say so once, name the one command above, and do the rest of the task without
numbers rather than inventing them.

## Ask for the balance before a batch

`goanyapi_credits_balance` is free and takes no arguments. On a shared or new account, read it first, and
after a run that spent a lot, read `goanyapi_activity_credits` to see where it went. Quote the calls and
their cost in the plan when the run will cost more than about $0.05: the user is paying per call.

## Which tool answers which question

| Question | Tool | Cost |
| --- | --- | --- |
| What ranks for this query today? | `goanyapi_google_serp_stable` (1 credit), `goanyapi_google_serp_standard` (2, more query controls), `goanyapi_google_serp` (3, multi-mode: web, news, videos, local, shopping, jobs) | 1 to 3 |
| How many pages hold this phrase in their title? | `goanyapi_google_intitle` | a few |
| What does this site have indexed for a term? | `goanyapi_google_site_search` | a few |
| Does it rank in Bing too? | `goanyapi_bing_serp` | 2 |
| Academic results for a topic | `goanyapi_google_scholar` | 1 |
| Volume, difficulty, related terms | `goanyapi_keyword_suggestions` → `goanyapi_keyword_search_volume`, `goanyapi_keyword_difficulty`, `goanyapi_keyword_generator` | a few each |
| Who links to it, how strong is it | `goanyapi_backlinks`, `goanyapi_domain_rating`, `goanyapi_domain_rating_history` | a few each |
| How much traffic, and from where | `goanyapi_traffic` (`month` for a series) | about 4 |
| Who pays for this term | `goanyapi_google_ads_transparency`, `goanyapi_google_ads_transparency_statistics` | about 4 |
| Which other sites share this AdSense account | `goanyapi_adsense` | about 3 a site |
| Is interest rising, and what else people search with it | `goanyapi_google_trends` (`RELATED_QUERIES`, `TIMESERIES`) | about 6 |
| What people type next | `goanyapi_google_autocomplete`, `bing`, `youtube`, `duckduckgo`, `naver`, `yandex`, `yahoo`, `coccoc` | 1 |
| What a competitor page actually says | `goanyapi_html_to_markdown_api` (free for `.com`) | 0 |
| What just launched in AI tools | `goanyapi_taaft_just_released_api` (5), `goanyapi_taaft_tools_api` (2) | 2 to 5 |
| App Store / Play store search demand | `goanyapi_app_store_inbound_keyword_list`, `goanyapi_google_play_inbound_keyword_list` | 1 |
| Verified revenue of an indie product | `goanyapi_trustmrr_api` | a few |
| What extension users complain about | `goanyapi_chrome_web_store_reviews` | about 2 to 3 a page |

Prices are what GoAnyAPI charged in November 2026 and are in the tool descriptions: read them from the tool
instead of trusting this table when the amount matters.

## The three calls that go wrong

**Keyword volume needs a suggestion first.** `goanyapi_keyword_search_volume` takes one exact keyword, not a
seed, and it has to come from `goanyapi_keyword_suggestions`' `data.keywords`. Call suggestions with the seed,
pick the exact strings from its answer, then ask for volume. Sending "ai headshot" as a seed to the volume
tool returns nothing useful and still costs a call.

**SERP editions are not interchangeable.** Stable (1 credit) first. Standard (2) when you need advanced query
operators or Google's own selectors. Multi-mode (3) when you need news, videos, local, shopping or jobs.
GoAnyAPI does not fall back between them: if Stable fails, try Standard, then Multi-mode, and say which one
answered, because the response fields differ per edition.

**A valid empty result is billed; a failure is not.** So a zero backlink count is a real answer worth
reporting, and an error means retry once, not five times.

## Three workflows

**A keyword gap against a competitor.** `goanyapi_keyword_suggestions` on the competitor's main term, take the
exact strings, `goanyapi_keyword_search_volume` and `goanyapi_keyword_difficulty` on the subset you care about,
then `goanyapi_google_serp_stable` on the three best to see who is actually there. Three calls per keyword at
most. Report volume, difficulty, and the position of the competitor's page in one table; label every number
with the source and the day.

**A page-2 push.** `goanyapi_google_serp_stable` for the term, read positions 8 to 20, then `goanyapi_backlinks`
and `goanyapi_domain_rating` on the three weakest domains above you. A competitor at DR 22 with eight referring
domains is a gap; one at DR 70 with 4,000 is not, whatever the difficulty score says.

**Who pays for the term.** `goanyapi_google_ads_transparency` with the keyword returns the advertisers and
domains running ads on it. That is the buyer list, not the competitor list: it tells the user which companies
already value the click. With `goanyapi_adsense` on those domains you can also see whether one owner runs
several sites in the same niche.

## Rules

- Never present a number this server did not return. If a call fails, write "no data: <tool> failed" and move
  on; do not fill the cell with an estimate, and do not average two runs into a third number.
- Cache what you fetched in the repo (`seo/data/YYYY-MM-DD-<slug>.json`) with the query and the date, and read
  the cache before spending again on the same term the same day.
- Say the date with every SERP and volume number. Positions move hourly and volume is a monthly average.
- Batch by judgement, not by loop: a hundred `domain_rating` calls is $0.20 the user did not agree to. Ask
  first when the domain list is longer than about ten.
- Do not put credits, tokens or OAuth material in a commit, a report, or a log line.

## What this is not

It is not Search Console: no clicks, impressions, CTR or the user's own queries, those only come from the
property itself. It is not a crawler: no Core Web Vitals, no rendering, no site graph (a local crawler is
that). It does not write to any site. It reads the public web and Google's advertising and keyword data, and
every answer is a snapshot of the day it was asked.
