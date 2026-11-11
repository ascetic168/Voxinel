[📖 Contents](index.md)

# 08 Settings Reference

Open via: system tray menu → 設置 (Settings). Changes take effect only after clicking **Save Settings**; Cancel reverts unsaved changes. Closing the window with X only hides it to the tray.


## Speech Recognition (語音辨識來源)

| Field | Description | Default |
|---|---|---|
| Source list | Enabled recognition sources; the number is the priority. Click an item to expand its details | Local Offline (SenseVoice) |
| ▲ / ▼ / ✕ | Reorder / remove sources | — |
| Provider / Model | Choose the source and model (available models per source: see [engines](07-engines.md)) | — |
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
| Conference Mode: Hide overlay windows (recording only) | Conference mode runs without overlay windows, recognizing and saving in the background | ✅ On |

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
| Enable AI meeting summary | Auto-generates a structured summary when the conference transcript is saved; uses the **same LLM settings** as proofreading | ❌ Off |## About (關於)

Shows the version, author (朱國棟 / Charlie Chu), contact email, and license.

---

[← 07 Speech Recognition Sources](07-engines.md) | [Contents](index.md) | [09 AI Features & LLM Setup →](09-ai-features.md)
