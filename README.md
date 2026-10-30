# FIELD / SOUND v0.6.4

Built from v0.6.3. Adds Sequence → Arrange non-destructive clips.

- In SEQUENCE, press SEND TO ARRANGE, or in ARRANGE choose + SEQUENCE CLIP.
- The clip captures a snapshot of the 16 pad assignments, source ranges, speed, reverse, loop, step grid, step count and swing. Original audio blobs are never modified.
- Drag the clip to reposition it; trim its right edge to set its arrangement length. Longer clips repeat the captured pattern.
- Clips share ARRANGE play/pause/stop, track volume and mute/solo.
- Save/Load and portable .fsproject export/import include sequence clips within the arrangement data.
- Existing audio regions and all earlier views are preserved.

Limitations: clip playback is scheduled at PLAY time; edits during playback require restarting. The clip's step pattern is a snapshot, not linked to later sequencer edits. Tempo changes while playing require restarting. No in-browser audio regression test was performed.


## v0.6.5 — EDIT preview 3-band EQ
- Non-destructive per-audio LOW (100 Hz shelf), MID (1 kHz peaking), HIGH (10 kHz shelf) using Web Audio BiquadFilterNode.
- Rotary drag, keyboard, numerical entry, 0 dB reset, EQ bypass. Range −24 to +12 dB.
- Settings stored in local SAVE/LOAD and portable EXPORT/IMPORT. Existing v0.6.4 features preserved.
- Scope: EDIT source preview playback only. PAD/SEQUENCE/ARRANGE audio routing and noise reduction are NOT yet modified.
- Original audio blobs remain untouched. Loud boosts may clip; reduce MASTER as needed.


## v0.6.6 — Noise Control (EDIT preview)
- Non-destructive **broadband adaptive noise gate** for preview only, not spectral/AI denoising.
- Shift+drag select 0.1–30 s of noise-only audio, LEARN estimates RMS noise reference.
- Enable, reduction (0–100%), sensitivity (0.5–8×), reset. Re-press PLAY after adjusting to hear updates.
- Very quiet desired sounds may also be attenuated; always compare by bypassing. Original Blob and AudioBuffer remain untouched.
- Per-source settings are stored in SAVE/LOAD and portable EXPORT/IMPORT.
- Noise gate is **not** yet applied to PAD or ARRANGE; EQ still behaves as before.


## v0.6.7 — Frequency Target (notch)
- Added an optional frequency-selective notch filter to EDIT preview after the existing broadband noise gate and before 3-band EQ.
- Adjustable center frequency (60–12000 Hz), Q (0.3–20), depth (0–100% wet mix), independent bypass. Adjustments update during playback.
- Intended for narrowband hum/whine; NOT spectral noise-profile subtraction, AI separation, or full-band denoising.
- Per-source non-destructive settings preserved in SAVE/LOAD and EXPORT/IMPORT; previous project defaults remain safe.
- Existing source files, pad playback, sequencer and arrangement are unchanged. Browser audio playback not verified.


## v0.6.8 — PAD PERFORMANCE RECORDING
- PERFORM tab: play 16 pads by touch/mouse/keyboard; RECORD TAKE captures unquantized pad hit times.
- PREVIEW TAKE plays the captured performance; SEND TAKE TO ARRANGE creates a non-destructive region with a snapshot of pad assignments and event timing.
- Performance regions are saved in arrangement through SAVE/LOAD and EXPORT/IMPORT.
- A new take in PERFORM replaces the unsent in-memory take; send it to ARRANGE first to keep it.
- No MIDI velocity or audio recording of the output yet; records pad triggers only.
- Preview and arrangement replay events against current project BPM.
- Fixed pre-existing duplicated project export/import handlers accidentally nested in renderSequencer.


## v0.6.9 — Velocity / Micro Timing
- SEQUENCE: click any step cell to select it, then edit VELOCITY (0–100%) and MICRO TIMING (−60 to +60 ms). A step may be selected even when OFF; settings are retained until activated.
- SEQUENCE playback applies each hit's velocity and time offset; the ARRANGE snapshot stores both and uses them during playback. The original audio is never modified.
- SAVE/LOAD and EXPORT/IMPORT preserve the step settings. Old projects default to 100% velocity and 0 ms offset.
- Swing remains available. This is per-hit groove editing, not an automatic groove-template extractor.
- Browser audio playback is not yet verified; syntax and ZIP integrity are checked.


## v0.7.0 — Sample pitch and envelope
- PAD PITCH ±24 semitones, in addition to SPEED. Uses playbackRate: pitch and duration change together (not independent time stretching).
- ATTACK / DECAY / SUSTAIN / RELEASE controls per pad. ADSR gain is scheduled for one-shot pad playback and arrangement sequence/performance playback.
- Settings are stored on pad objects and inherited by existing snapshot-based project persistence. Old project pads fall back to defaults. Original audio is not modified.
- Note: Looping and gate mode use the original stop behavior; this version does not yet implement a note-off-triggered release. Browser playback needs testing.


## v0.7.1 — Vocal / Field Chopper
- EDIT > VOCAL / FIELD CHOPPER: select a range with Shift+drag, choose Attack/Onset, Silence/Phrase or Equal, count 2–16 and sensitivity. Detect proposed slices.
- Editable start/end boundaries (in seconds) and individual preview. Neighbouring boundaries move together.
- Assign slices to PAD 01–16 starting at any chosen pad. Occupied pads require confirmation before replacement.
- Source audio is never rewritten. Pad source references and their ranges persist through existing SAVE/EXPORT.
- No speech recognition or source separation: detection is based on signal energy. Check and edit the boundaries before assigning.
- Chopper preview boundaries are transient until assigned; saving a project preserves assigned pad ranges, not the temporary detection list.


## v0.7.2 — PAD Effects
Added non-destructive low-pass filter, feedback delay and convolution reverb to each PAD. Each effect has an independent bypass. PAD effects are saved through existing project SAVE/LOAD and EXPORT/IMPORT because parameters live on pad objects. Sequence snapshots and recorded performances also carry pad settings. Delay and reverb are generated locally without external downloads.

Known limitations: effects are not yet applied to EDIT source preview or standalone audio ARRANGE regions; no effect automation. Browser audio playback still needs real-device verification.
