[📖 Contents](index.md)

# 03 Push-to-Talk (PTT)

The default voice-input mode: hold the hotkey and speak, and the recognized text is pasted automatically when you release. The closest thing to typing with your voice.

## Basic Flow

1. Hold `Ctrl` (or your chosen combo) and start speaking
2. While you talk, the overlay window near the bottom of the screen shows the streaming recognition result **as you speak**
3. Release the hotkey — the offline engine (SenseVoice) re-recognizes the full audio with higher accuracy and punctuation
4. The corrected text is automatically **pasted** into the window that was focused when you pressed the hotkey
5. Your previous clipboard content is restored

## Reading the Overlay

The overlay appears bottom-center on your main monitor and never steals focus (clicks and typing keep going to your work window):

| Color | Meaning |
|---|---|
| Light blue text | Confirmed recognition result |
| Amber text | Live streaming prediction, still pending correction |

When you release the hotkey, the amber portion is replaced by the high-accuracy SenseVoice result (with punctuation), then pasted and the overlay hides.

## How the Dual Engines Cooperate

- **Streaming engine (Zipformer)**: starts recognizing the instant you press the hotkey, giving real-time feedback so you can verify as you speak
- **Offline engine (SenseVoice)**: re-recognizes the complete audio after you release, for final quality; supports Chinese, English, Japanese, Korean, and Cantonese, with automatic punctuation

## When Recording Cancels or Nothing Is Pasted

- Held less than 0.5 s, or audio shorter than 0.8 s → auto-cancelled / discarded
- Any other key pressed during recording → instant cancel (bail out by pressing any key before releasing)
- Empty recognition result → nothing pasted
- Full details in [Hotkeys & Misfire Protection](02-hotkeys.md)

## Using Cloud Engines

With [Tencent Cloud or Gemini ranked first](07-engines.md), PTT works the same — hold, speak, release, paste — but there is **no live streaming display**: after you release, the whole clip (silence-stripped by VAD) is sent to the cloud, then pasted. Keep the local engine in first place if you want the live feedback.

## Tips

- No result from a very short utterance (<0.8 s) is normal misfire protection, not a bug
- If the offline correction hasn't returned within 5 seconds of releasing, the app pastes the streaming result directly rather than leaving you stuck
- Switching windows mid-recognition is fine — the paste target was locked when you pressed the hotkey, and focus is restored automatically

---

[← 02 Hotkeys & Misfire Protection](02-hotkeys.md) | [Contents](index.md) | [04 Listening Mode →](04-mode-listening.md)
