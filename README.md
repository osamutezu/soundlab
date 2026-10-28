FIELD / SOUND v0.5.0 — CUE system

Based on the actual v0.4.1 ZIP. Main Cue (back cue, pause-set, hold preview), eight Hot Cues, Memory Cues, waveform markers and optional quantization. Existing sequencer and audio import retained.

Hot Cues and Memory Cues are held in session memory in this build; persistent storage and controller MIDI mapping are future work. Main Cue long press starts after 160 ms; touchscreen hold behavior may differ from hardware. Browser runtime testing is not yet completed.


v0.5.1: FIXED PLAYHEAD toggle added to waveform editor. When enabled, waveform scrolls underneath the playhead (when zoom > 1); FOLLOW WAVEFORM is mutually exclusive. At track boundaries the playhead shifts naturally because the waveform is clamped to track bounds.


v0.5.2: FIXED PLAYHEAD is always precisely centered at every zoom, including 1x. Waveform scrolls with blank space at start/end.


## v0.5.3
- Main CUE, Hot CUE A–H, Memory CUE positions are included in SAVE PROJECT and RESTORE.
- Existing saves without CUE data remain supported.
- CUE positions are validated against the decoded audio duration on restore.
- All features from v0.5.2 retained.
