[📖 Contents](index.md)

# 01 Getting Started

## System Requirements

| Item | Requirement |
|---|---|
| OS | Windows 10 / 11 (full functionality); macOS and Linux installable with limitations (see note below) |
| Microphone | Required for voice input, listening, conference, and assistant modes |
| Disk space | About **600MB** for the first model download |
| Network | Only needed to download models once; afterwards **completely offline** |
| GPU | **Not required.** Runs smoothly on CPU alone |

> **macOS / Linux note**: Settings, basic voice input, and launch-at-startup all work; but the system-audio capture (loopback) behind Live Caption and Conference Mode, and automatic pasting of results, are currently implemented on Windows only. See the [FAQ](12-faq.md).

## Installation

1. Download the latest installer from the [GitHub Releases](https://github.com/ascetic168/Voxinel/releases) page
2. Run the installer — Voxinel then lives in the system tray (the 🎤 icon near the clock)
3. Voxinel is a single-instance app: launching it twice won't open a second copy

## First Launch & Model Download

1. On first launch the settings window opens automatically, along with a "Downloading Speech Recognition Model..." dialog that starts downloading right away
2. Download order: offline recognition (SenseVoice) → streaming recognition (Zipformer) → VAD → speaker recognition → TTS
3. The progress bar shows the current item and "downloaded / total"; when everything is done you'll see "Model download complete" and the dialog closes itself
4. Once downloaded you're ready to go — **no API keys needed**

The models total roughly 600MB and are stored in the system model directory (see [Files & Data Locations](11-data-and-files.md)). If a download fails, reopening the settings window triggers it again.

> **China Mainland acceleration**: when the system language is Simplified Chinese, model downloads automatically switch to a mirror site (hf-mirror.com) — no configuration needed.

## System Tray

Voxinel normally lives in the system tray. **Left-click the icon** to open the menu:

| Menu item | Action |
|---|---|
| 傾聽模式 (Listening Mode) | Toggle [Listening Mode](04-mode-listening.md) (reads 關閉傾聽模式 while active) |
| 即時字幕模式 (Live Caption Mode) | Toggle [Live Caption Mode](05-mode-caption.md) |
| 會議模式 (Conference Mode) | Toggle [Conference Mode](06-mode-conference.md) |
| AI 助手模式 (AI Assistant Mode) | Toggle [AI Assistant Mode](07-mode-assistant.md) |
| 聲紋辨識管理 (Speaker Management) | Open the [speaker voiceprint manager](06-mode-conference.md#speaker-management) |
| 設置 (Settings) | Open the [settings window](09-settings.md) |
| 打開記錄檔目錄 (Open transcript folder) | Open the transcript folder (`Documents\Voxinel`) in Explorer |
| 結束 (Quit) | Fully exit Voxinel |

Closing the settings window with X only hides it back to the tray — the app keeps running; use 結束 (Quit) in the tray menu to exit fully.

> Tray menu labels are currently shown in Traditional Chinese regardless of the UI language.

## Launch at Startup

Settings window → "System Settings" → check "Launch at system startup". Supported on all three platforms (Windows / macOS / Linux).

## Updating

Voxinel **does not auto-update**. When a new version ships, download the new installer from [Releases](https://github.com/ascetic168/Voxinel/releases) and install it directly — your settings and models are preserved.

---

[← Contents](index.md) | [02 Hotkeys & Misfire Protection →](02-hotkeys.md)
