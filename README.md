# FIELD / SOUND — v0.1

Browser-based local-first sampler prototype. No external libraries or accounts.

## Start

- Open `index.html` directly for importing and playback. For microphone recording, use an HTTPS origin (such as GitHub Pages) or `http://localhost`.
- GitHub Pages: create a public repository, upload `index.html`, `style.css`, `app.js` to the repository root, then enable Pages → Deploy from a branch → main / root.
- On Mac, you can also run `python3 -m http.server 8000` in this directory and open `http://localhost:8000`.

## Features

- Microphone capture via MediaRecorder, import audio supported by the browser
- Waveform rendering, non-destructive region selection, preview, export region as new library clip
- 16 pads, adjustable gain/speed, reverse, loop, gate, keyboard triggers
- Tap tempo and manual BPM (no beat detection or tempo-sync in v0.1)
- Project save/load in browser IndexedDB (audio blobs included)

## Limitations

- Browser storage is device- and origin-specific. Save does not synchronize devices or create a downloadable backup. Do not treat browser storage as the only copy of irreplaceable recordings.
- Microphone recording formats and decoding differ across browsers. Some recordings may not be decodable on all devices.
- Keyboard playback timing depends on the browser/device. No sample-accurate sequencer yet.
- Reverse playback creates a temporary reversed buffer and may use additional memory for long files.
- No recording monitoring, BPM detection, multi-track, effects or VJ link yet.
- Recording may stop when the phone sleeps or browser tab is suspended.
