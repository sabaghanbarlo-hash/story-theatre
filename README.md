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

Use `[bg: moonlit forest]` to set a scene. Add another `[bg: sea at dawn]` or `[bg: village]` line when the location changes. Narration action words such as *walked, ran, jumped, fell, laughed, gasped, pointed,* and *wondered* trigger animated movement automatically.

Voices: af_heart, af_bella, af_nicole, af_sarah, bf_emma, am_michael, am_fenrir, am_puck, bm_george, bm_fable.

## Notes

- Voicing runs on your device, so it is slower on phones. The page can freeze briefly while a line is generated.
- Recording happens in real time and needs the tab to stay open and visible.

## Storytime motion cues

Characters no longer need to remain planted in place. The animation reads each narration line for common physical actions and adds free, real-time movement: walking and running travel across the scene, jumps arc upward, falls dip, laughter bounces, and surprise/pointing/thinking add small acting motions. These cues are heuristic, so write clear action verbs in the narration for the best results. No paid API or remote video-generation service is used.

## Automatic scene generation

Story Theater now attempts to infer common settings from ordinary narration (for example school, bedroom, kitchen, office, city street, beach, forest, park, shop, and cafe). Use explicit `[bg: ...]` lines whenever you want to guarantee a location change. Action words such as walked, ran, jumped, fell, laughed, gasped, pointed, and wondered drive movement cues. The generator uses hand-drawn Canvas scenery and local/browser animation; it does not call a paid video-generation API. Scene and action inference is heuristic, so review the preview and add explicit scene cues for unusual settings or subtle transitions.

## Important: script parsing and scene changes

The parser splits scripts into actual lines and recognizes action verbs and explicit `[bg: ...]` markers. Common settings are inferred from ordinary narration, including bedrooms, schools, cafeterias, kitchens, offices, streets, beaches, forests, parks, shops, and cafes. A setting change creates a new visual scene. For predictable scene changes, put a location in the narration (for example, “I ran from my bedroom into the school cafeteria”) or add `[bg: school cafeteria]` on its own line.

This is still a lightweight, heuristic 2D Canvas animator, not a generative model that invents arbitrary new drawings. It uses locally drawn scenery and character rigs, so unusual actions and locations may need explicit cues. No paid API is required.
