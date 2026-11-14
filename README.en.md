# Voxinel

**[正體中文](README.md)** | **[简体中文](README.zh-CN.md)** | **[English](README.en.md)**

![Version](https://img.shields.io/badge/version-0.6.1-2563eb) ![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-64748b) ![Privacy](https://img.shields.io/badge/audio-100%25%20local-16a34a) ![GPU](https://img.shields.io/badge/GPU-not%20required-16a34a) ![License](https://img.shields.io/badge/license-freeware-f59e0b)

> **Hold Ctrl, speak, and your words are typed for you.**
> A fully local voice-input tool — streaming recognition shows text as you speak, SenseVoice polishes it after you release. Runs smoothly on CPU alone: no GPU, no cloud, no API keys.

📖 **Full user manual**: [正體中文](docs/zh-TW/index.md) · [简体中文](docs/zh-CN/index.md) · [English](docs/en/index.md)

## Up and Running in 30 Seconds

| What you want | How |
|---|---|
| Type by speaking | Hold `Ctrl`, talk, release — recognized and pasted automatically |
| Dictate long passages | Double-tap **right** `Ctrl` for Listening Mode; sentences paste themselves |
| Caption a video or call | System tray menu → Live Caption Mode |
| Meeting minutes + AI summary | System tray menu → Conference Mode |

First time: [download the installer](https://github.com/ascetic168/Voxinel/releases) → models download automatically on launch (~600MB, one time only) → start talking.

## Why Voxinel

### 1. Audio Never Leaves Your Machine — and It Runs Fine without a GPU
All recognition happens locally; audio is never uploaded to any server — ideal for enterprises and classified environments. The dual-engine architecture (streaming Zipformer + offline SenseVoice) **runs smoothly on CPU alone**: no dedicated GPU, no CUDA, no internet, no API keys.

### 2. Text as You Speak, Polished When You're Done
A unique streaming-offline collaboration: the streaming engine (Zipformer) starts recognizing the instant you press the hotkey and displays live results; when you release, the offline engine (SenseVoice) re-recognizes the full audio with higher accuracy and automatic punctuation. Real-time feedback and final quality — you get both.

### 3. A Single Ctrl Key, without Disturbing How You Already Type
Hold Ctrl to record; the app detects your intent the whole time: chords with other modifiers never start a recording, any keypress during recording cancels it instantly, too-short clips are discarded, and empty results paste nothing. Ctrl+C, Ctrl+V, and IME switching keep working untouched — and your clipboard content is restored after every paste.

## How It Compares to Cloud-Only Voice Input

| | Voxinel | Cloud-only tools |
|---|---|---|
| Where audio goes | Stays on your machine | Uploaded to third-party servers |
| Offline use | ✅ Fully offline once models are installed | ❌ Requires internet |
| Hardware | CPU only, no GPU | Not needed (but compute happens in the cloud) |
| Live feedback | ✅ Text appears as you speak | Depends on the service |
| Classified environments | ✅ Fits enterprise / government intranets | Usually prohibited |
| Cost | Free; keys only if you opt into cloud engines | Subscription or metered billing |

## Five Modes, Each with a Job

| Mode | How to start | Audio source | Best for |
|---|---|---|---|
| **Push-to-Talk** (default) | Hold `Ctrl` | Microphone | Replacing typing |
| **Listening Mode** | Double-tap right `Ctrl` | Microphone | Long dictation, sentence-by-sentence pasting |
| **Live Caption Mode** 🧪 | System tray menu | System playback | Captions for videos／talks／calls |
| **Conference Mode** 🧪 | System tray menu | Microphone + system audio | Meeting transcripts, speaker labels, AI summary |

Modes run exclusively and switch automatically; details in the [user manual](docs/en/index.md).

## Features

**Core input**
- Fully local dual engine — streaming Zipformer live feedback + SenseVoice offline correction; zero privacy concerns
- CPU-only performance — no GPU or CUDA needed on any modern laptop or desktop
- Automatic punctuation — ，。？ output directly, no extra model
- Voice activity detection — Ten-VAD filters silence and pauses, eliminating garbage characters (adjustable sensitivity)
- Simplified/Traditional conversion — automatic based on system locale, for streaming and final results alike

**Advanced modes**
- Live Caption Mode 🧪 — real-time captions of system audio, transcript saved on close
- Conference Mode 🧪 — local + remote dual-track recording, echo suppression, automatic speaker voiceprint labels

**AI-powered (via local Ollama or any OpenAI-compatible LLM)**
- AI proofreading — transcripts auto-corrected when closing caption／conference mode
- AI meeting summary — structured summary generated automatically when a conference ends

**Conveniences**
- Multi-engine ASR — local (default), Tencent Cloud ASR, Google Gemini; custom priority with automatic fallback
- System tray resident, launch at startup, one-click transcript folder, clipboard protection
- Multi-language UI — 繁體中文／简体中文／English
- China Mainland download acceleration — automatic mirror site on Simplified Chinese systems

## Supported ASR Engines

| Engine | Type | Description |
|---|---|---|
| Local dual engine (default) | Offline | Streaming Zipformer (zh-en) + SenseVoice-Small (zh/en/ja/ko/yue, automatic punctuation); no keys; models auto-download on first launch |
| Tencent Cloud ASR | Cloud | SentenceRecognition API; Mandarin／video／English／Cantonese／Sichuan dialect; needs Secret ID + Secret Key |
| Google Gemini | Cloud | gemini-3.5-transcribe (default) and related models; automatic punctuation, filler-word removal; needs an API Key |

Model storage location: `C:\ProgramData\Voxinel\models\` (Windows).

## Installation & Quick Start

1. Download the installer from the [Releases page](https://github.com/ascetic168/Voxinel/releases)
2. First launch opens the settings window and auto-downloads all models (streaming, offline, VAD, speaker — ~**460MB** total)
3. Once downloaded you're ready to go — no API keys to configure, fully offline from then on

## Screenshots

<!-- TODO: after adding real screenshots, uncomment the table below (images go in docs/images/)
| Settings | Push-to-Talk overlay | Conference dual captions |
|---|---|---|
| ![Settings](docs/images/settings.png) | ![Push-to-Talk](docs/images/overlay-ptt.png) | ![Conference](docs/images/conference.png) |
-->

*Screenshots coming soon.*

## Latest Release

✅ **Released v0.6.1** — Segmentation overhaul: conference and caption modes drop fixed mid-speech force cuts; line breaks now come from confirmed silence and voiceprint speaker-change detection. Fixes speaker labels vanishing on long segments, surfaces unknown speakers in the transcript, suppresses phantom near-end lines, and adds a conference mic mute button plus caption-mode toasts.

<details><summary>v0.5.10</summary>v0.5.10 — Hardened PTT against accidental triggers: chords with other modifiers no longer start a recording, any keypress now cancels it immediately, and empty recognition results no longer inject simulated paste keystrokes — fixing stray characters appearing during keyboard typing.</details>

<details><summary>v0.5.9</summary>v0.5.9 — Assistant TTS voice is now selectable with preview in Settings (defaults to a Mandarin voice), and the PTT hotkey no longer mis-fires while the assistant window is open.</details>

<details><summary>v0.5.8</summary>v0.5.8 — Fixed recognized text not pasting into the target window when listening mode was started from the tray menu.</details>

## License

Closed-source software, free to use. Developed by Charlie Chu (朱國棟).
