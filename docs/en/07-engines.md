[📖 Contents](index.md)

# 07 Speech Recognition Sources (ASR Engines)

Voxinel supports three recognition sources. You can enable several at once and rank them by **priority**: recognition tries the first one and falls back to the next on failure (Fallback).

## Local Dual Engine (default, no keys required)

| Engine | Role | Description |
|---|---|---|
| Streaming Zipformer | Real-time | Bilingual Chinese-English streaming model; shows text as you speak. Powers PTT live display, plus listening／caption／conference modes |
| SenseVoice-Small (INT8) | Offline correction | High-accuracy offline recognition; Chinese, English, Japanese, Korean, Cantonese; automatic punctuation |

- Runs entirely on your local CPU; audio never leaves the machine
- Models auto-download on first launch (~600MB total); Simplified-Chinese systems automatically use a download mirror
- Model location: see [Files & Data Locations](10-data-and-files.md)

## Tencent Cloud ASR

- Service: SentenceRecognition (single-utterance synchronous recognition)
- Requires **Secret ID** and **Secret Key** from the Tencent Cloud console
- Available engine models:

| Model | Language |
|---|---|
| `16k_zh` | Mandarin |
| `16k_zh_video` | Mandarin (video scenarios) |
| `16k_en` | English |
| `16k_yue` | Cantonese |
| `16k_ca` | Sichuan dialect |

## Google Gemini

- Cloud AI speech recognition; requires an **API Key** (from Google AI Studio)
- Available models: `gemini-3.5-transcribe` (default), `gemini-3.5-flash`, `gemini-3.5-flash-lite`, `gemini-3.8-flash`
- Automatic punctuation and filler-word removal; output language follows the interface language (Traditional/Simplified Chinese, Japanese, Korean, English — otherwise the language actually spoken)
- Note: Gemini results **skip the Simplified/Traditional conversion** — output follows the language you configured directly

## Priority & Automatic Fallback

In the Settings "Speech Recognition" section:

- **Add a source**: entering any provider's credentials enables it and appends it to the list
- **▲／▼**: change priority (lower number is tried first)
- **✕**: remove a source
- **Test Connection**: verify the currently selected source

Recognition flow: try the first source → if it fails (missing keys, network error, quota) → automatically try the next → if all fail, no text is produced for that utterance.

> **Live display depends on first place only**: streaming as-you-speak feedback requires the **local engine to be ranked first**. With a cloud engine first, the flow becomes release → whole clip to the cloud → paste, with no live preview.

## Environment Variables (advanced)

Credentials can also come from environment variables (used as fallback when the Settings fields are empty):

| Variable | Purpose |
|---|---|
| `TENCENTCLOUD_SECRET_ID` / `TENCENTCLOUD_SECRET_KEY` | Tencent Cloud credentials |
| `GEMINI_API_KEY` | Gemini key |

---

[← 06 Conference Mode & Speakers](06-mode-conference.md) | [Contents](index.md) | [08 Settings Reference →](08-settings.md)
