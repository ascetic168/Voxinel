[正體中文](../zh-TW/index.md) | [简体中文](../zh-CN/index.md)

# Voxinel User Manual

> Hold Ctrl, speak, and your words are typed for you — fully local speech recognition. No GPU, no cloud, no API keys.

**Applies to: v0.5.10**

> Note: some in-app text — the tray menu and the "AI 助手模式" / "TTS 語音回覆" settings sections — currently displays in Traditional Chinese regardless of the interface language.

## Contents

| Chapter | What it covers |
|---|---|
| [01 Getting Started](01-getting-started.md) | System requirements, installation, first launch & model download, system tray |
| [02 Hotkeys & Misfire Protection](02-hotkeys.md) | Every hotkey at a glance, how accidental triggers are prevented |
| [03 Push-to-Talk (PTT)](03-mode-ptt.md) | The default mode: hold to speak, release to paste |
| [04 Listening Mode](04-mode-listening.md) | Continuous dictation, pasted sentence by sentence |
| [05 Live Caption Mode](05-mode-caption.md) | Turn system audio into live captions and a transcript |
| [06 Conference Mode & Speakers](06-mode-conference.md) | Mic + system audio dual recording, speaker labels, AI summary |
| [07 AI Assistant Mode](07-mode-assistant.md) | Wake word, voice Q&A, TTS spoken replies |
| [08 Speech Recognition Sources](08-engines.md) | Local dual engine, Tencent Cloud, Gemini, priority & fallback |
| [09 Settings Reference](09-settings.md) | Every settings field explained, with defaults |
| [10 AI Features & LLM Setup](10-ai-features.md) | Proofreading, meeting summary, and the assistant's LLM endpoint |
| [11 Files & Data Locations](11-data-and-files.md) | Where models, config, and transcripts live |
| [12 FAQ & Troubleshooting](12-faq.md) | No text pasted, connection failures, platform limits, and more |

## Five Modes at a Glance

| Mode | How to start | Audio source | Where results go | Best for |
|---|---|---|---|---|
| **Push-to-Talk** (default) | Hold `Ctrl` | Microphone | Whole utterance recognized and pasted on release | Replacing typing |
| **Listening Mode** | Double-tap **right** `Ctrl` | Microphone | Recognized and pasted sentence by sentence | Long dictation, thinking out loud |
| **Live Caption Mode** 🧪 | System tray menu | System playback | On-screen captions; transcript saved on close | Captions for videos, talks, calls |
| **Conference Mode** 🧪 | System tray menu | Microphone + system audio | Dual captions + merged transcript + AI summary | Meeting minutes with speaker labels |
| **AI Assistant Mode** | Say the wake word, or press `Ctrl+Shift+L` | Microphone + text input | AI chat window with TTS voice replies | Asking questions without typing |

> 🧪 = experimental feature; behavior and UI are still being refined.

## Key Concept: Modes Are Mutually Exclusive

Only **one mode runs at a time**. Starting any mode automatically stops the others. Additionally:

- While Listening Mode is active, Push-to-Talk is temporarily disabled so both cannot record at once
- While the AI Assistant window is open, PTT is likewise disabled to keep conversation from leaking into your apps
- Background wake-word listening only happens when every other mode is idle

## Quick Navigation

- First time here → Start with [Getting Started](01-getting-started.md), then try [Push-to-Talk](03-mode-ptt.md)
- Want every hotkey → [Hotkeys & Misfire Protection](02-hotkeys.md)
- Taking meeting minutes → [Conference Mode](06-mode-conference.md)
- Bringing your own LLM → [AI Features & LLM Setup](10-ai-features.md)
- Something's wrong → [FAQ & Troubleshooting](12-faq.md)
