[📖 Contents](index.md)

# 06 Conference Mode & Speakers 🧪

Captures your **microphone (local: what you say)** and **system audio (remote: the other side or the meeting playback)** at the same time, showing both as live captions; on close, everything merges into a timestamped transcript with speaker labels, and an AI meeting summary can be generated automatically.

> ⚠️ Remote-audio loopback capture is **Windows only** for now. 🧪 marks an experimental feature.

## Toggle On / Off

1. System tray menu → "Conference Mode" (requires the streaming model to be downloaded)
2. A purple "🔊 遠端" (remote) caption window appears at the **top** of the screen, a green "🎤 近端" (local) window at the **bottom**
3. Click the tray item again (it reads 關閉會議模式 while active) to finish and save

## Echo Suppression

When the remote side talks, their voice played through your speakers also reaches your microphone — the same sentence would be recorded twice. Conference Mode includes heuristic echo suppression: while remote speech is detected, microphone audio is ignored; about 0.5 s after the remote side stops, your mic comes back. **Works best with headphones.**

## Speaker Voiceprint Labels

- Built-in speaker recognition: every new voice is automatically registered as `Speaker_1`, `Speaker_2`, … — no manual enrollment needed
- When the same person is heard again, captions and the transcript show `[Speaker_1]`; the more a person speaks, the more reliable the matching becomes
- Clips shorter than 0.5 s are always labeled unknown

### Speaker Management

System tray menu → "Speaker Management" (聲紋辨識管理) opens the management window:

| Action | What it does |
|---|---|
| Rename | Change `Speaker_1` to a real name; future transcripts and captions will show it |
| Delete | Remove a speaker's voiceprint data |
| Merge | Renaming to an existing name offers to merge the two voiceprints into one person |

Voiceprint data is stored in the model directory as `speaker\speakers.db` (SQLite) and **never leaves your machine**.

## Transcript & AI Summary

When you close the mode:

1. Local and remote text merge in timestamp order and save to `Documents\Voxinel\conference_YYYYMMDD_HHMMSS.txt`. Consecutive lines from the same speaker are grouped into one block — the timestamp and speaker appear only on the block's first line:

```
# 會議記錄 (Meeting Record) — 2026-10-31 14:00:00
# 時長 (Duration): 1830.0 s | 遠端 (Remote): 42 segments | 近端 (Local): 18 segments

[14:00:12] 遠端 [Speaker_1]：
大家早安，我們開始今天的會議
今天主要討論三件事

[14:00:25] 近端：
好的，我先報告上週進度
```

2. If "AI Proofreading" is enabled → lines are corrected by the LLM before saving
3. If "AI Meeting Summary" is enabled → an additional `conference_summary_YYYYMMDD_HHMMSS.md` is generated with sections for summary, attendees, topics, decisions, and action items (see [AI Features & LLM Setup](09-ai-features.md))

## Record Without Captions

Settings → "System Settings" → check "Conference Mode: Hide overlay windows (recording only)": no overlay windows appear during the meeting; recognition and saving run quietly in the background — useful in formal settings where on-screen captions would be distracting.

## Tips

- Wear headphones for the best echo suppression
- Audio from meeting apps (Google Meet, Teams, etc.) is captured through system audio — no extra configuration needed
- If the remote side produces no captions, check that the meeting playback device is the Windows default playback device

---

[← 05 Live Caption Mode](05-mode-caption.md) | [Contents](index.md) | [07 Speech Recognition Sources →](07-engines.md)
