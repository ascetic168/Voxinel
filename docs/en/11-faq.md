[📖 Contents](index.md)

# 11 FAQ & Troubleshooting

## Voice Input

### I held Ctrl, spoke, released — but no text appeared?

Check in order:

1. **Was the utterance too short?** — recordings under 0.8 s are auto-discarded (misfire protection)
2. **Is a recognition source configured?** — Settings → "Speech Recognition" needs at least one; if all sources fail, no text is produced
3. **Are the models downloaded?** — reopen the settings window; if models are missing the download dialog appears automatically
4. **Did you press another key while recording?** — any other keypress cancels the recording immediately

### Text was pasted into the wrong window?

The paste target is locked the moment you press the hotkey, and focus is returned to that window before pasting. A few special apps (fullscreen games, windows running with administrator privileges) may refuse simulated pastes.

### Ctrl conflicts with IME switching or other shortcuts?

Pressing any other key during a recording cancels it immediately, handing Ctrl back to the original shortcut; pressing Ctrl while Shift／Alt is held never triggers a recording. Still annoying? Switch the hotkey to `Ctrl + Win` or another combo in Settings.

### Stray characters occasionally appear on my keyboard?

Fixed in v0.5.10 (empty recognition results no longer send simulated paste keystrokes). Please update to the latest version.

## Modes

### Listening Mode pastes into the wrong window?

The paste target is locked **when the mode is activated**. To switch: double-tap right Ctrl to stop, focus the target window, then start it again.

### Live Caption／Conference Mode shows no captions? (Windows)

1. Make sure the audible device is the Windows **default playback device** — the capture taps the default device's mix
2. Audio through non-default devices (e.g. Bluetooth headphones) won't be captured; switch the default device first
3. macOS / Linux do not support system-audio capture

### Conference Mode labels everyone "unknown"?

- Clips under 0.5 s are always unknown; speak at a normal pace
- Voiceprints improve with exposure — the more a person speaks, the more accurate
- Open "Speaker Management" and rename `Speaker_N` to the person's real name; future transcripts will show it
## AI Features

### Proofreading／summary does nothing?

1. Make sure the feature is checked in Settings
2. Make sure the LLM endpoint works (see [AI Features & LLM Setup](09-ai-features.md)): is local Ollama running? is the model name correct?
3. The endpoint is health-checked at startup — if Ollama wasn't running then, start it and restart Voxinel
## Engines & Models

### Model download fails or is slow?

- Simplified-Chinese systems automatically use a mirror site; if you're on a mainland-China network but your system isn't Simplified Chinese, temporarily set the interface language to 简体中文 before downloading
- Make sure at least 600MB of disk space is free
- If the download is interrupted, reopening the settings window triggers it again

### Can I use only cloud engines?

Yes. Rank a cloud source first — PTT works the same, just without the as-you-speak live display (see [engines](07-engines.md)).

## Platforms & Misc

### How well does macOS / Linux work?

Installable, basic voice input works, and launch-at-startup is supported; but Live Caption／Conference Mode (system-audio capture) and automatic pasting are currently Windows-only.

### How do I diagnose a problem?

Launch with the `--debug` argument to open a console with detailed messages. Voxinel normally writes no log files.

### How do I report an issue?

Email: charliechu1688@gmail.com

---

[← 10 Files & Data Locations](10-data-and-files.md) | [Contents](index.md)
