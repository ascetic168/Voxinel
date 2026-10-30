[📖 Contents](index.md)

# 07 AI Assistant Mode

A background voice Q&A assistant: it quietly listens to your microphone and starts a conversation when it hears the wake word. Ask by voice; the AI answers in rich text with a spoken voice summary on top.

## Ways to Start

| Method | Description |
|---|---|
| Wake word | Default 小花同學 ("Xiaohua"), editable in Settings. On hearing it, the assistant replies 我在。 ("I'm here.") and starts listening to your question |
| `Ctrl+Shift+L` | Skips the wake word and opens the conversation window immediately — the most reliable way |

- This mode is **enabled by default**: as long as the streaming model is downloaded, it stands by in the background as soon as the app starts
- Background listening only happens when every other mode is idle (modes are mutually exclusive)

## The Conversation Window

- Takes about 80% of the screen, always on top; **clicking anywhere else in the window closes it** (ending the conversation and stopping speech) — clicks in the bottom input bar don't close it
- A status badge shows: 聆聽中 (listening for you) → 思考中 (AI thinking) → the reply
- Your lines are blue, AI replies are purple; the last 15 lines of the conversation are kept on screen
- **Text input bar**: when speaking is impractical, type your message and press Enter
- Replies render **Markdown**, tables, code, **KaTeX math** (`$...$` inline, `$$...$$` display), **Mermaid diagrams**, and SVG graphics
- The conversation is multi-turn — just follow up

## Voice Replies (TTS)

- **On by default**: replies are also spoken aloud as a short conversational version (2–4 sentences), while the full text stays on screen
- Settings offers **103 voices** (Chinese female / Chinese male / English female), speech rate 0.5x–2.0x, and a 🔊 preview button
- While speech is playing, the microphone is temporarily ignored so the assistant doesn't hear its own voice

## When It Won't Respond

- The wake word must be **spoken completely** and recognized; short or mumbled syllables are treated as noise and ignored
- Background listening pauses while other modes (listening／caption／conference) are running
- PTT is disabled while the assistant window is open — a deliberate misfire protection (since v0.5.9) so conversation content can't be pasted into other apps

## The Assistant's Brain: LLM Configuration

The assistant uses an OpenAI-compatible LLM endpoint, defaulting to local Ollama (`http://localhost:11434`, model `gemma4:latest`). You can point it at OpenAI, OpenRouter, or any compatible service — see [AI Features & LLM Setup](10-ai-features.md). An optional "extra prompt" in Settings customizes the assistant's persona and answer style.

---

[← 06 Conference Mode & Speakers](06-mode-conference.md) | [Contents](index.md) | [08 Speech Recognition Sources →](08-engines.md)
