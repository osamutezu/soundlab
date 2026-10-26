FIELD / SOUND v0.3

Based on v0.2.1. Adds full overview, zoomable detailed waveform, BLUE/RGB/3Band-inspired colors, beat grid with bar numbers, BPM analysis ranges, half/double BPM, grid offset and downbeat alignment, alternative candidates and heuristic confidence.

BPM analysis remains an experimental heuristic, not the proprietary rekordbox engine. The 3Band rendering is an approximate frequency visualization, not identical to rekordbox. Confidence is a relative candidate score, not a calibrated accuracy probability.

Open index.html in a modern browser. Microphone recording requires HTTPS or localhost. Local project saves do not include analysis metadata yet.


## v0.3.1
- BPM worker searches 0.1 BPM increments with interpolated lag. Decimal display in analysis result and BPM input. This is an estimate, not guaranteed 0.1 BPM accuracy.
- Playback position overlays in overview and detailed waveform, dimming the played section to the left and emphasizing upcoming audio to the right. Uses AudioContext time; applies to file preview and Play Selection.
