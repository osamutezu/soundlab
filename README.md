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

## v0.5.4 — Waveform drag scrubbing
- Drag waveform horizontally to move the track position by the same proportional distance (left drag advances, right drag rewinds).
- Works in FIXED PLAYHEAD at 1× zoom and at higher zoom. The playhead stays centered.
- Single click seeks; Shift+drag still selects a range.
- When dragging during playback, playback temporarily stops and resumes from the scrubbed position on release.


## v0.6.0 — ARRANGE
- Logic Pro-inspired multi-track timeline, beat/bar ruler, playhead, transport.
- Import audio via RECORD, select source in ARRANGE, add audio region.
- Drag region to move, drag right edge to trim, double-click to edit source.
- Track Mute, Solo, Volume, region duplication and deletion.
- Non-destructive source offsets, scheduled multitrack playback.
- Arrangement data saved in existing local IndexedDB project.
- Known limits: no region splitting, MIDI, mixer, or automatic waveform-to-grid time stretching yet.
