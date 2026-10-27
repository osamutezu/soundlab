FIELD / SOUND v0.4.0

Built from the latest actual v0.3.6 files.

New: 16-track step sequencer, 16/32 steps, swing, start/stop, example pattern, local project persistence. BPM follows top transport. Uses Web Audio clock with 120ms lookahead and 25ms scheduling loop.

How to use: IMPORT AUDIO, assign sounds to PAD 1-3 in SAMPLE, open SEQUENCE, GENERATE EXAMPLE, PLAY PATTERN.

Limitations: no pattern export yet, one pattern only, and scheduled sample start timing has not been browser-tested.


v0.4.1 hotfix
- Initialize activeAnalysis before file imports can call selectEdit.
- Differentiate decoder errors from app errors.
- Preserve all v0.4.0 sequencer functionality.
