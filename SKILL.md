---
name: fetch-youtube
description: Fetch YouTube video transcripts with robust InnerTube fallback. Use when extracting captions/transcripts from a YouTube URL, channel, or batch config, especially when ordinary transcript libraries fail or return no transcript.
---

Fetch transcripts from YouTube videos. Prefer this skill when the goal is to obtain transcript text, not to summarize.

Run `./fetch-youtube --url <youtube-url>` for a single video.
Run `./fetch-youtube --channel <channel-id-or-handle> --hours <n>` for recent channel videos.
Run `./fetch-youtube --config config/channels.example.json --daily` for batch mode.

The main script is `scripts/fetch_youtube.py`.
It uses watch-page scraping plus InnerTube player API fallback with multiple client profiles (`ANDROID`, `WEB`, `TVHTML5_SIMPLY_EMBEDDED_PLAYER`, `IOS`) to recover caption tracks that simpler methods miss.

Return the transcript text from the generated JSON output. Do not rely on any summary fields.
