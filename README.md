# Flipbook Recaps

Cartoon flipbook recaps of TV shows. Hand-drawn-style panels, slow pan and zoom, and a real human narrator. Long-form season and episode recaps, cut down into Shorts.

Built in the open with Claude Code. This repo is the production pipeline, plus the scripts and style guides for each show.

## How an episode gets made

1. **Source:** the episode's subtitle file gives the actual dialogue, so the recap is accurate (not from memory).
2. **Script:** Claude drafts it, the narrator rewrites it in their own voice, and the differences feed back into [`style/voice.md`](style/voice.md) so later drafts get closer.
3. **Narration:** recorded on a real mic. No AI voice.
4. **Panels:** generated in ChatGPT from a fixed art style ([`style/art-style.md`](style/art-style.md)) plus per-show character sheets, one panel per beat of the script.
5. **Timing:** the recorded narration is transcribed with word-level timestamps, and each panel is placed where its line is spoken.
6. **Assembly:** ffmpeg adds the pan and zoom, title cards and captions, then renders a 16:9 long-form cut and 9:16 Shorts.

## Layout

```
style/                 channel-wide art style + narrator voice guide
shows/<show>/
  show.md              cast, look of each character, season notes
  characters/          approved character reference sheets
  episodes/<sXXeYY>/
    script.md          draft -> narrator's final
    panels.md          one prompt per panel, tied to script lines
    panels/            generated images
    audio/             narration (not committed)
    out/               rendered video (not committed)
tools/                 pipeline scripts
```

Subtitle files, narration audio and rendered video are kept out of git.
