# fit.gif

Compress animated GIFs to fit social network upload limits — right in your browser. No uploads, no watermark, no server.

Built for **X/Twitter**, **Farcaster**, and **Discord**, and tuned for 2D illustration and pixel art loops.

## Why

Social platforms cap GIF uploads (X at 15 MB, Farcaster at 10 MB, Discord at 10 MB on the free tier), and a short high-frame-rate loop can blow past those in seconds. Most compressors fix this by uploading your file to their servers. fit.gif does everything locally — your GIF never leaves your device.

## Features

- **Platform targets** — pick X, Farcaster, or Discord and see the exact cap you're fitting under, with a built-in safety buffer so uploads aren't rejected at the edge.
- **Auto-fit** — one click finds a setting combination that lands under the selected cap.
- **Three compression levers** — palette reduction (8–256 colors), frame-dropping (keep-all through 1-in-4), and resize (20–100%).
- **Tuned for flat art** — cuts colors and drops frames before resizing, so illustration and pixel-art loops keep their dimensions as long as possible.
- **Art-type detection** — automatically recognizes pixel art vs. illustration on upload (via pixel-grid, palette, and dithering analysis) and tailors the on-screen guidance to match.
- **Pixel-art mode** — crisp nearest-neighbor resizing that keeps pixels sharp; illustration mode uses smooth downscaling. Neither dithers, keeping flat color areas clean.
- **Pass/fail verdict** — shows whether the result fits, a size-vs-cap bar, and a before/after preview.
- **Light / dark / system themes** — monochrome, follows your OS by default.

## How it works

Everything runs client-side in vanilla JavaScript:

1. Decodes the GIF (GIF87a/89a, LZW, handling interlacing and frame disposal).
2. Resizes and requantizes each frame to a shared color palette (median-cut).
3. Re-encodes to a valid looping GIF.

No dependencies, no build step, no network calls.

## Usage

Open the hosted page, drop in a GIF, pick a target, and either adjust the sliders or hit **Auto-fit**. Download the result when it fits.

Or run it locally — download `index.html` and open it in any browser. It's a single self-contained file.

## Privacy

Your GIF is never uploaded. All processing happens in your browser's memory. The only thing the host serves is the page itself.

## Limitations

- Uses a from-scratch decoder/encoder, so very large or high-frame-rate GIFs (e.g. 1080p at 100+ frames) can take 20–40 seconds and use significant memory.
- GIF's 256-color palette is inherently less efficient than video. If your destination accepts MP4 (X and Farcaster do), an MP4 export of the same clip will usually be smaller at the same quality.

## License

MIT
