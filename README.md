# FIELD / SOUND v0.2

Extends v0.1 using the actual previous files. Includes recording, imports, waveform editor, 16 pads, IndexedDB save/load, and new BPM estimate, beat-grid overlay, transient overlay, slice preview and batch pad assignment.

## How to use
1. Open index.html in Chrome or Safari. For microphone recording publish via HTTPS (e.g. GitHub Pages).
2. Import audio and open EDIT.
3. Click ANALYZE BPM. BPM is an approximate estimate, not guaranteed, particularly on short or non-rhythmic material. Adjust the BPM input manually.
4. Choose TRANSIENT / EQUAL / BEAT slicing, set number of slices, click PREVIEW SLICES.
5. Click ASSIGN TO PADS 01–16. Existing assignments on those pads are replaced.
6. SAVE persists files, pad assignments and BPM locally; LOAD restores them.

## Notes
- Transient and tempo estimation are lightweight offline heuristics; results depend on audio content.
- Beat grid starts at time zero and does not estimate downbeat offset.
- No cloud upload; IndexedDB can be cleared by browser storage management.
- Mac/iPhone/iPad have not been physically tested in this environment.
