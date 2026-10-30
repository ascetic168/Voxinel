[📖 Contents](index.md)

# 02 Hotkeys & Misfire Protection

## Hotkey Cheat Sheet

| Function | How | Customizable |
|---|---|---|
| Push-to-Talk (PTT) | Hold `Ctrl` and speak; release to recognize and paste | ✅ Choose from five combos |
| Toggle Listening Mode | Double-tap **right** `Ctrl` (within 1 second) | ❌ Fixed |
| Open the AI Assistant instantly | `Ctrl+Shift+L` | ❌ Fixed |
| Wake the AI Assistant | Say the wake word (default: 小花同學) | ✅ Wake word is editable |

## PTT Hotkey Combos

Settings → "Recognition Settings" → "Hotkey" offers five combos; changes take effect immediately:

| Option | Best for |
|---|---|
| `Ctrl` (single key, default) | Smoothest to use; full misfire protection (below) |
| `Ctrl + Win` | Users who want zero interaction with everyday Ctrl shortcuts |
| `Ctrl + Shift` | — |
| `Ctrl + Alt` | — |
| `Shift + Alt` | — |

## How Single-Key Ctrl Avoids Misfires

A single-key Ctrl shares the same physical key as everyday Ctrl+C / Ctrl+V, so Voxinel ships with a full intent-detection layer — normal keyboard use is never disturbed:

| Rule | Behavior |
|---|---|
| Won't start while other modifiers are held | Pressing Ctrl while Shift／Alt／Win is held never starts a recording (IME switches and other chords won't misfire) |
| Held less than 0.5 s | Auto-cancelled; a quick Ctrl tap never records |
| Any other key pressed during recording | **Instantly cancelled** — e.g. you press Ctrl, then change your mind and press Ctrl+C: the recording cancels at once and the copy proceeds normally |
| Recording shorter than 0.8 s | Auto-discarded; no garbage text |
| Empty recognition result | No paste keystrokes are sent at all — no stray characters on your keyboard |
| Within 0.2 s after auto-paste | The simulated Ctrl used for pasting is never mistaken for a new recording |

## Pasting & the Clipboard

- After recognition, the text is pasted with a simulated `Ctrl+V`, and **your original clipboard content is restored** afterwards (text portion)
- The paste target is locked to the foreground window **at the moment you press the hotkey**; when recognition finishes, focus is brought back to that window before pasting so text never lands in the wrong place
- Voxinel's own windows, the taskbar, and the Start menu are never paste targets

## Global Rules

- PTT is temporarily disabled while **Listening Mode is active** or **the AI Assistant window is open**
- Hotkey changes take effect immediately — no restart needed

---

[← 01 Getting Started](01-getting-started.md) | [Contents](index.md) | [03 Push-to-Talk (PTT) →](03-mode-ptt.md)
