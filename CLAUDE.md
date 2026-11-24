# Flipbook Recaps: notes for Claude

This is a public repo. Never commit personal info, subtitle files, narration audio or rendered video.

## Image generation
- Generate panels by driving the **ChatGPT desktop app** with computer use. This is the owner's choice: no OpenAI API key.
- Use one ChatGPT conversation per episode. Re-attach the style anchors and the relevant character sheets at the start, then go scene by scene.
- Check every image against the character sheets. Regenerate anything that drifts (wrong hair, costume or props, or the style sliding toward anime or photo).
- Before downloading, get the owner's approval for the episode's whole batch and its destination folder (`shows/<show>/episodes/<ep>/panels/`).

## Scripts
- Write from the episode's subtitle file, not from memory. Shows past the model's knowledge cutoff are the norm.
- Save the draft as `script.draft.md`. The owner rewrites it into `script.md`. Afterwards, update `style/voice.md` with what changed.
- Flag purely visual plot beats the subtitles can't show, so the owner can fill them in.

## Assembly
- ffmpeg on macOS (`/opt/homebrew/bin/ffmpeg`).
- Time panels from the recorded narration (word-level transcript), not from the script.
