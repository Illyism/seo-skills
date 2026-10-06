---
name: scribiz
description: Get the transcript, on-screen text, summary, and chapters of any video or audio with Scribiz. Use when the user wants to transcribe a YouTube, TikTok, Instagram, podcast, or local media file, generate SRT or VTT subtitles, summarize a video, ask questions about a video, or turn a video into a blog post, show notes, or social posts.
metadata:
  version: 1.0.0
  author: illyism
  source: https://il.ly/skills/scribiz
---

# Scribiz

[Scribiz](https://scribiz.com) turns a video or audio link, or a local file, into a transcript with speakers and timestamps, the text shown on screen, a summary, and chapters. It works when a video has no captions.

Docs: [scribiz.com/docs](https://scribiz.com/docs). Every docs page is also Markdown: add `.md` to the path.

## Pick a way in

```
What does the agent have?
├── An MCP client (Claude Code, Cursor, Codex) and a link
│   └── Use the MCP server. Best for questions, summaries and search.
├── A shell and a link or local file
│   └── Use the CLI. Best for subtitles, files on disk and batch jobs.
└── Neither
    └── Send the user to scribiz.com to paste the link.
```

## MCP server

Hosted at `https://scribiz.com/mcp` (Streamable HTTP). No key needed to start.

```bash
# Claude Code
claude mcp add --transport http scribiz https://scribiz.com/mcp
```

Cursor, in `~/.cursor/mcp.json`:

```json
{ "mcpServers": { "scribiz": { "url": "https://scribiz.com/mcp" } } }
```

```toml
# Codex: ~/.codex/config.toml
[mcp_servers.scribiz]
url = "https://scribiz.com/mcp"
```

Tools:

- `get_video_context`: summary, chapters and key moments in under 2,000 tokens. Start here.
- `search_video`: find where a phrase is said and read only those minutes.
- `ask_video`: an answer with 3–5 cited moments, each a timestamp link.
- `get_transcript`: the full transcript, when you really need all of it.
- `get_job`: check a running job.

Without a key the server reads captions, videos already processed and, within a small daily allowance, the link itself. It never looks at the picture. With an API key (`Authorization: Bearer $SCRIBIZ_API_KEY`) it uses the account's minutes and can read the screen. Other clients: [MCP install](https://scribiz.com/docs/mcp/install.md).

Prefer `get_video_context` then `search_video` over pulling the whole transcript. A two-hour talk is more than 25,000 tokens.

## CLI

```bash
npm install -g scribiz     # or: npx scribiz --help
scribiz login              # free account, 30 minutes a month
scribiz setup              # or: your own Gemini API key
scribiz doctor             # checks the credential, ffmpeg, ffprobe, yt-dlp
```

Needs Node.js 24+, `ffmpeg`, and `yt-dlp` for most links (`brew install ffmpeg yt-dlp`). Tested on macOS.

```bash
scribiz "https://www.youtube.com/watch?v=VIDEO_ID" -o talk.srt        # subtitles
scribiz talk.mp4 -f txt -o talk.txt                                    # plain text
scribiz talk.mp4 -f md -o talk.md                                      # Markdown with speakers
scribiz context talk.mp4 --visual -f context                           # transcript + on-screen notes + summary + chapters, for an LLM
scribiz talk.mp4 --json --out-file talk.json                           # save the full result once
scribiz format talk.json -f vtt                                        # render another format without paying again
scribiz ask talk.json "What did they decide about pricing?"
```

Put links that contain `?` in quotes. A folder input writes one `.srt` next to each file.

### Options

- **Format:** `-f srt|vtt|txt|md|context|json` (default `srt`)
- **Mode:** `-m auto|captions|audio|visual|full` (aliases `listen`, `watch`, `both`). Auto uses good captions and listens when there are none.
- **Speakers:** `--speakers` for interviews and podcasts, `--no-speakers` for on-screen captions
- **Proofread:** `--proofread`, plus `--vocabulary "Brand,Name"` for names speech-to-text mishears
- **Language hint:** `-l en`
- **Cost guard:** `--max-cost 0.50`, `--max-duration 02:00:00`
- **Scripts:** `--no-input` never prompts. Exit codes: 0 ok, 2 usage, 3 sign-in or quota, 4 source, 5 provider, 6 missing tool.

Do not split or rechunk SRT cues after the fact. Re-run Scribiz instead.

## Content workflows

- **Video to blog post:** run `get_video_context` (or `scribiz context`), outline from the chapters, quote the transcript for key claims, and link timestamps as sources.
- **Podcast show notes:** `-f md --speakers`, then write a summary, chapter list with timestamps, and pull quotes.
- **Social clips:** use `search_video` to find the strongest moments, then write posts that cite the exact second.
- **Competitor research:** summarize a competitor's demo or webinar and list the claims and features they show on screen (`--visual`).
- **Subtitles for upload:** `--proofread --no-speakers -o video.srt`.

## Limits

- YouTube, podcast feeds, direct media links and files work best. TikTok, X and Vimeo are best effort. Instagram usually needs `--cookies-from-browser chrome` on the CLI.
- Not for live streams, DRM services (Spotify, Netflix), editing, or generating video.
- Spot-check names and brands in the output before publishing.
