[📖 Contents](index.md)

# 04 Listening Mode

Continuous dictation: once enabled, Voxinel keeps listening to your microphone and **pastes each finished sentence automatically**, until you turn it off. Ideal for long passages and thinking out loud.

## Toggle On / Off

- **Double-tap the right `Ctrl` key** (two presses within 1 second) — repeat to turn it off
- Or toggle "Listening Mode" from the system tray menu

## Key Points

- **The paste target is locked when you activate the mode** — every sentence goes to that window. To switch windows: turn the mode off, focus the new window, then turn it on again
- Every sentence goes through the SenseVoice offline correction and gets automatic punctuation
- The overlay shows a "🎙️ Mic 傾聽" label with a **pulsing green border** so you can tell at a glance that it's on
- On shutdown, sentences already recorded but not yet finalized are pasted before the mode fully stops (drain behavior) — nothing is lost
- **This mode produces no transcript file** — its only output is pasted text. Use [Live Caption](05-mode-caption.md) or [Conference Mode](06-mode-conference.md) if you need a saved record

## Typical Flow

1. Place your cursor where the text should go (e.g. your editor)
2. Double-tap right Ctrl to start Listening Mode
3. Speak — each finished sentence appears at the cursor position
4. Double-tap right Ctrl again to stop

## Relationship with Other Modes

- Starting Listening Mode automatically stops the other modes (caption／conference／assistant) — modes are mutually exclusive
- While Listening Mode is active, Push-to-Talk is temporarily disabled so the two can't record at once

---

[← 03 Push-to-Talk (PTT)](03-mode-ptt.md) | [Contents](index.md) | [05 Live Caption Mode →](05-mode-caption.md)
