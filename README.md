# ffmpeg Command Builder

Task-first ffmpeg helper. Instead of digging through documentation, pick what you want to do (compress a video, make a GIF, trim a clip, extract the audio) and get the exact command, with every flag explained in plain language and honest warnings where they matter.

One HTML file, no external dependencies, works offline.

**Live demo:** https://0xelitesystem.github.io/ffmpeg-command-builder/

## Use

1. Search for a goal or click a category filter (compress, audio, trim, GIF, subtitles, info).
2. Pick a task to see its ffmpeg command.
3. Fill in your file name, times, or quality slider; the command updates as you type.
4. Read the flag explanations and warnings, then click copy and run the command in your terminal.

## Why this exists

ffmpeg can do almost anything, but the right flags are buried in long documentation. This tool turns everyday goals into the exact command with every flag explained. It is one HTML file with inline CSS and JavaScript: no account, no tracking, no analytics, no external scripts or fonts, and it works offline. MIT licensed, so you can fork it, self-host it, or read every line.

## Features

- 32 everyday ffmpeg tasks phrased as goals, grouped into six categories: compress and convert, audio, trim and cut, GIF and images, subtitles, info and misc
- Search box plus category filters to find the right task fast
- Live-substituting inputs: type your file name, drag the CRF quality slider, set trim times, and the command updates as you type
- Every flag in every command explained in plain language
- Honest warnings where they matter: keyframe snapping on stream-copy trims, re-encode quality loss, GIF file sizes, the -y overwrite flag
- Copy button on every command
- The copy-trim task computes the -to duration from your start and end times automatically
- The speed task builds the atempo filter chain automatically for extreme values
- Dark mode toggle, keyboard-friendly UI

Scope, honestly stated: this covers everyday tasks, it is not an ffmpeg reference. Commands target recent ffmpeg versions (5.x and newer).

## How it works

Every task is a small data object: a goal-phrased title, a description, optional input fields, a command template, per-flag explanations, and warnings. Selecting a task renders the command from the template, substituting your input values where you have provided them and clearly marked placeholders (like `<input.mp4>`) where you have not. There is no server and no build step; open `index.html` in any modern browser and it works, including with no network connection.

## Privacy

Everything runs client-side in your browser. File names and values you type never leave the page. No analytics, no tracking, no network requests of any kind. The only thing written to storage is your light or dark theme choice, saved in localStorage under the key `theme`.

## Run locally

```bash
git clone https://github.com/0xelitesystem/ffmpeg-command-builder
cd ffmpeg-command-builder
```

Then open `index.html` in any modern browser. Or serve the folder with `python -m http.server 8000` and visit http://localhost:8000.

## Build

No build step. The whole tool is one `index.html` with no dependencies, so there is nothing to install or compile.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT. Copyright 0xelitesystem 2026.
