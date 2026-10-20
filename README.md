# Story Theatre

Paste a story, press one button, and a free AI narrator reads it while a stickman hero walks, runs, climbs and explores a side-scrolling world that changes with the story. Then download the finished video.

Runs entirely in your browser (phone or laptop). No server, no account, no GPU, no paid services.

**Open it:** https://sabaghanbarlo-hash.github.io/story-theatre/

## How it works

- **Voice:** [Kokoro](https://github.com/hexgrad/kokoro) (82M-parameter open-weight TTS, Apache-2.0) via `kokoro-js`, running locally in the browser. The model (about 80 MB) downloads once and is cached by your browser.
- **Auto-director:** each sentence is read for action words (walked, ran, climbed, jumped, waved, laughed, looked up, gasped, fell asleep), places (forest, village, sea, mountain, snow, desert, castle, night/day) and objects (tree, house, boat, chest, fire, lantern, flowers, birds). The hero acts it out, the world scrolls and changes, and props appear along the path.
- **Stickmen:** procedural walk cycle, eased head and arm motion, blinking, mouth driven by the loudness of the real audio.
- **Video file:** the page records its own canvas and audio (MediaRecorder) and gives you an MP4 or WebM to download.

## Script format

Plain text works: one stickman reads and acts out everything. For a narrator and characters:

```
@character Kaito | color=#1b1b1f, hat=cap, voice=am_michael
@character Mia | color=#d64545, hat=crown, voice=af_bella
[bg: a quiet forest at night]
[action: climb]
[prop: tree, lantern]
Once upon a time...            <- unnamed lines are read by the off-screen Narrator
Mia: "You can't catch the moon!"
```

The first `@character` is the hero. `hat` can be cap, top or crown. `[action: ...]` (walk, run, jump, climb, wave, laugh, point, lookup, surprise, sleep) and `[prop: ...]` apply to the next line; `[bg: ...]` sets the world.

Voices: af_heart, af_bella, af_nicole, af_sarah, bf_emma, am_michael, am_fenrir, am_puck, bm_george, bm_fable.

## Notes

- Voicing runs on your device, so it is slower on phones. The page can freeze briefly while a line is generated.
- Recording happens in real time and needs the tab to stay open and visible.
