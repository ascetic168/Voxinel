[📖 Contents](index.md)

# 05 Live Caption Mode 🧪

Turn **whatever your computer is playing** into live captions: videos, online courses, talks, or the far side of a call are captioned in real time at the bottom of your screen; closing the mode saves a timestamped transcript.

> ⚠️ Requires system-audio loopback capture — **Windows only** for now. 🧪 marks an experimental feature.

## Toggle On / Off

1. System tray menu → "Live Caption Mode"
2. A caption window with a **purple pulsing border** appears at the bottom of the screen
3. Click the tray item again (it reads 關閉即時字幕 while active) to stop and save automatically

## The Caption Window

- Shows up to **5 lines** of captions by default (configurable 3–15 in Settings), auto-scrolled to the latest
- Within a line: **blue** is confirmed text, **amber** is live prediction
- Experimental "mid-segment correction": while a sentence is still in progress, SenseVoice pre-recognizes the earlier part of the audio and promotes it to blue, with the not-yet-corrected remainder continuing in amber — so long sentences show high-quality text before they're fully spoken

## The Transcript

When you close the mode, a transcript is saved to `Documents\Voxinel\caption_YYYYMMDD_HHMMSS.txt`:

```
# Live Caption Record — 2026-10-31 14:05:00
# Duration: 123.4 s
[14:05:02] First caption line
[14:05:09] Second caption line
```

(The on-disk file header is written in Chinese.) If "AI Proofreading" is enabled, the lines are corrected by an LLM before saving — see [AI Features & LLM Setup](09-ai-features.md). The tray item "Open transcript folder" opens the folder directly.

## Common Questions

- **Nothing shows up?** This mode captures the mix of the Windows **default playback device**. If audio is playing through a non-default device (e.g. Bluetooth headphones), set that device as the default in Windows sound settings first
- Environments with no audible system audio (e.g. some remote desktops) can't be captured
- For meetings, use the fuller-featured [Conference Mode](06-mode-conference.md) (adds your microphone and speaker labels)

---

[← 04 Listening Mode](04-mode-listening.md) | [Contents](index.md) | [06 Conference Mode & Speakers →](06-mode-conference.md)
