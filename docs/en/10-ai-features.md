[📖 Contents](index.md)

# 10 AI Features & LLM Setup

Voxinel's three AI features share one **OpenAI-compatible LLM endpoint** configuration (Base URL + model name + API Key):

| Feature | When it runs | What it does |
|---|---|---|
| AI Proofreading | Before saving a Live Caption／Conference transcript | Fixes typos and punctuation, merges sentences broken across lines; timestamps preserved |
| AI Meeting Summary | When the conference transcript is saved | Produces a Markdown summary with sections for summary, attendees, topics, decisions, action items |
| AI Assistant | Wake word／`Ctrl+Shift+L` conversation | Voice Q&A with multi-turn context and Markdown／KaTeX／Mermaid replies |

## Option A: Local Ollama (default — free, fully offline)

1. Install [Ollama](https://ollama.com) and make sure the service is running
2. Pull a model, e.g. `ollama pull gemma4` (the Settings default is `gemma4:latest` — use the exact name you pulled)
3. In Settings keep Base URL `http://localhost:11434`, enter Ollama's model id as the model name, leave API Key empty
4. Check the AI features you want and save

## Option B: OpenAI or Compatible Cloud Services

| Service | Base URL | Example model name |
|---|---|---|
| OpenAI | `https://api.openai.com` (`/v1` may be omitted) | `gpt-4o-mini` etc. |
| OpenRouter | `https://openrouter.ai/api/v1` | per platform docs |
| Other OpenAI-compatible endpoints | per provider docs (mind the path rule below) | per provider docs |

Fill in the API Key and save.

> **Base URL path rule**: for Ollama and OpenAI the root URL is enough (the app appends the API path); **for other services enter the complete path** including the version segment (`/v1`, …). A wrong path typically shows up as connection failures or 404s.

## Verifying It Works

- **AI Assistant**: press `Ctrl+Shift+L` and ask something — you should get a reply
- **Proofreading／Summary**: run Conference Mode, say one sentence, close it, and check whether the saved transcript was corrected and whether a summary file appeared
- The endpoint is health-checked at app startup; if Ollama wasn't running yet, start it and **restart Voxinel**

## Troubleshooting Table

| Symptom | Likely cause |
|---|---|
| Proofreading／summary does nothing | Feature not checked; LLM endpoint unavailable (startup health check failed) |
| Assistant stuck on 思考中 (thinking) | Wrong endpoint or model name; invalid API Key |
| 404 / model not found | Model name doesn't match the service; Base URL path incomplete |
| Slow responses | Cloud network latency; local model too large — try a smaller one |

---

[← 09 Settings Reference](09-settings.md) | [Contents](index.md) | [11 Files & Data Locations →](11-data-and-files.md)
