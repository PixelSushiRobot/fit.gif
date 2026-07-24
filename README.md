# fit.gif

**Shrink animated GIFs to fit social upload caps — right in your browser.**

fit.gif compresses GIF loops down to the size limits of X/Twitter (15MB), Farcaster (10MB), and Discord (10MB), so your art posts as a real GIF instead of a video. It's tuned for illustration and pixel art loops, and it runs entirely on your device.

**→ [Try it live](https://pixelsushirobot.github.io/fit.gif/)** — no install, nothing to upload.

## Why

Posting GIF art often means converting it to MP4 just to clear an upload limit — losing the true-loop, autoplay, hotlinkable qualities that make a GIF a GIF. fit.gif keeps it a GIF and gets it under the cap.

## Features

- **One-click auto-fit** — pick a platform and it finds the largest settings that stay under the limit.
- **Art-type detection** — recognizes pixel art vs. illustration and adjusts its strategy (no dithering, palette-preserving resizes for pixel art).
- **Full manual control** — scale, color count, and frame step if you want to dial it in yourself.
- **Runs locally** — pure client-side JavaScript, no dependencies, no build step, no server.

## How it works

1. Decodes the GIF in-browser (frames, palette, timing, transparency).
2. Applies your chosen transforms — resize, palette quantization, frame reduction.
3. Re-encodes a valid, looping GIF you can download.

Auto-fit walks a ladder of settings from least to most destructive, stopping at the first result that fits — resizing before dropping colors, and dropping frames only as a last resort.

## Usage

1. Drop in a GIF.
2. Choose a target platform, or set scale / colors / frames manually.
3. Download the compressed result.

## Privacy

> [!NOTE]
> Your GIF never leaves your device. All processing happens in the browser — nothing is uploaded to any server. You can also download `index.html` and run it fully offline.

## Limitations

- Very large or long GIFs may need heavy compression to fit — quality trade-offs are unavoidable at extreme sizes.
- Optimized for illustration and pixel art loops; photographic GIFs will work but aren't the focus.

## License

MIT
