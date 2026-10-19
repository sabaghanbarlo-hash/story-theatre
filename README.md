# Story Theatre

Paste a story, press one button, and a character tells it out loud: the mouth moves with the words, the character blinks, sways, nods and gestures.

Runs entirely in the browser (phone or laptop). No install, no server, no GPU, no paid services.

**Open it:** https://sabaghanbarlo-hash.github.io/story-theatre/

## Script format

Plain text works: one character reads everything. For more:

```
@character Kaito | hair=#2a2030, shirt=#2a9d8f, style=short
@character Mia | hair=#6b3a2a, shirt=#e76f51, style=long
[bg: moonlit forest]
Once upon a time...
Mia: "You can't catch the moon!"
```

The first `@character` is the storyteller. A `[bg: ...]` line starts a new scene; words like night, forest, sea, village or dawn change the setting.

## Notes

- The voice comes from your device's built-in text-to-speech, so voices differ between phones and computers.
- Browsers cannot record their own speech, so to save a video, screen-record the page with sound.
