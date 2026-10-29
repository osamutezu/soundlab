# FIELD / SOUND v0.6.4

Built from v0.6.3. Adds Sequence → Arrange non-destructive clips.

- In SEQUENCE, press SEND TO ARRANGE, or in ARRANGE choose + SEQUENCE CLIP.
- The clip captures a snapshot of the 16 pad assignments, source ranges, speed, reverse, loop, step grid, step count and swing. Original audio blobs are never modified.
- Drag the clip to reposition it; trim its right edge to set its arrangement length. Longer clips repeat the captured pattern.
- Clips share ARRANGE play/pause/stop, track volume and mute/solo.
- Save/Load and portable .fsproject export/import include sequence clips within the arrangement data.
- Existing audio regions and all earlier views are preserved.

Limitations: clip playback is scheduled at PLAY time; edits during playback require restarting. The clip's step pattern is a snapshot, not linked to later sequencer edits. Tempo changes while playing require restarting. No in-browser audio regression test was performed.
