# fetch-youtube

OpenClaw skill and CLI for robust YouTube transcript extraction.

## What it does

It fetches captions from YouTube videos using a resilient fallback path:
watch page scrape -> INNERTUBE_API_KEY extraction -> InnerTube player API via multiple clients -> caption XML download -> transcript text extraction.

## Usage

```bash
./fetch-youtube --url "https://www.youtube.com/watch?v=VIDEO_ID"
./fetch-youtube --channel "@channel_handle" --hours 24
./fetch-youtube --config config/channels.example.json --daily
```

The output is JSON and includes `transcript` when extraction succeeds.
