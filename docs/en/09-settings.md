[📖 Contents](index.md)

# 09 Settings Reference

Open via: system tray menu → 設置 (Settings). Changes take effect only after clicking **Save Settings**; Cancel reverts unsaved changes. Closing the window with X only hides it to the tray.

> The "AI 助手模式" and "TTS 語音回覆" sections currently display in Traditional Chinese regardless of the interface language.

## Speech Recognition (語音辨識來源)

| Field | Description | Default |
|---|---|---|
| Source list | Enabled recognition sources; the number is the priority. Click an item to expand its details | Local Offline (SenseVoice) |
| ▲ / ▼ / ✕ | Reorder / remove sources | — |
| Provider / Model | Choose the source and model (available models per source: see [engines](08-engines.md)) | — |
| Credential fields | Depends on the source: Secret ID／Secret Key (Tencent Cloud), API Key (Gemini), Model Directory (local — usually leave as is) | empty |
| Test Connection | Check the currently selected source | — |

> With no source configured, the page shows a warning: "Please configure at least one speech recognition provider".

## Recognition Settings (識別設置)

| Field | Description | Default |
|---|---|---|
| Hotkey | The push-to-talk key combo (five options, see [Hotkeys](02-hotkeys.md)) | `Ctrl` (single key) |
| Simplified/Traditional | Auto (by system locale)／Traditional Chinese／No conversion; applies to streaming and final results | Auto |

## Language (語言)

| Field | Description | Default |
|---|---|---|
| Interface Language | Auto (detect system language)／繁體中文／简体中文／English | Auto |

## Voice Activity Detection (語音活動偵測)

| Field | Description | Default |
|---|---|---|
| Filter silent segments | Skips silence and pauses so background noise isn't recognized as garbage characters | ✅ On |
| Sensitivity | 0.1–0.9. **Lower = more sensitive** (more audio passes), higher = stricter filtering | 0.50 |

## System Settings (系統設置)

| Field | Description | Default |
|---|---|---|
| Launch at system startup | Start Voxinel automatically at login | ❌ Off |
| Conference Mode: Hide overlay windows (recording only) | Conference mode runs without overlay windows, recognizing and saving in the background | ❌ Off |

## AI Proofreading (AI 輔助校稿)

| Field | Description | Default |
|---|---|---|
| Enable AI proofreading | When closing caption／conference mode, an LLM corrects the transcript (typos, punctuation, merged broken sentences) before saving | ❌ Off |
| Base URL | OpenAI-compatible API address; for Ollama or OpenAI the root URL is enough, others need the full path | `http://localhost:11434` |
| Model | LLM model id | `gemma4:latest` |
| API Key | Leave empty for no authentication (e.g. local Ollama) | empty |

## AI Meeting Summary (AI 會議摘要)

| Field | Description | Default |
|---|---|---|
| Enable AI meeting summary | Auto-generates a structured summary when the conference transcript is saved; uses the **same LLM settings** as proofreading | ❌ Off |

## AI Assistant Mode (AI 助手模式)

| Field | Description | Default |
|---|---|---|
| Enable AI assistant mode | Background wake-word listening when other modes are idle | ✅ On |
| Wake word | Hearing it starts a conversation with the reply 我在。 | 小花同學 |
| Extra prompt | Appended after the built-in system prompt to customize the assistant's persona and style | empty |

## TTS Voice Replies (TTS 語音回覆)

| Field | Description | Default |
|---|---|---|
| Enable voice replies | AI assistant replies are also spoken as a short conversational version | ✅ On |
| Speech rate | 0.5x (slow) – 2.0x (fast) | 1.0x |
| Voice | 103 voices: English female, Chinese female, Chinese male | Chinese female zf_001 |
| 🔊 Preview | Preview the selected voice at the current rate | — |

## About (關於)

Shows the version, author (朱國棟 / Charlie Chu), contact email, and license.

---

[← 08 Speech Recognition Sources](08-engines.md) | [Contents](index.md) | [10 AI Features & LLM Setup →](10-ai-features.md)
