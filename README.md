# Story Theatre

Paste a story, press one button, and a free AI narrator reads it while characters act it out: mouths move with the real voice, they blink, sway, nod and gesture. Then download the finished video.

Runs entirely in your browser (phone or laptop). No server, no account, no GPU, no paid services.

**Open it:** https://sabaghanbarlo-hash.github.io/story-theatre/

## How it works

- **Voice:** [Kokoro](https://github.com/hexgrad/kokoro) (82M-parameter open-weight TTS, Apache-2.0) via `kokoro-js`, running locally in the browser. The model (about 80 MB) downloads once and is cached by your browser.
- **Lip-sync:** the mouth follows the loudness of the actual generated audio.
- **Motion:** eased head sway, random blinks, nods and hand gestures on emphasis.
- **Video file:** the page records its own canvas and audio (MediaRecorder) and gives you an MP4 or WebM to download.

## Script format

Plain text works: one character reads everything. For a narrator and characters:

```
@character Kaito | hair=#2a2030, shirt=#2a9d8f, style=short, voice=am_michael
@character Mia | hair=#6b3a2a, shirt=#e76f51, style=long, voice=af_bella
[bg: moonlit forest]
Once upon a time...            <- unnamed lines are read by the off-screen Narrator
Mia: "You can't catch the moon!"
```

Words like night, forest, sea, village or dawn in a `[bg: ...]` line change the setting.

Voices: af_heart, af_bella, af_nicole, af_sarah, bf_emma, am_michael, am_fenrir, am_puck, bm_george, bm_fable.

## Notes

- Voicing runs on your device, so it is slower on phones. The page can freeze briefly while a line is generated.
- Recording happens in real time and needs the tab to stay open and visible.
