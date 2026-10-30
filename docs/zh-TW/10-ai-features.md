[📖 目錄](index.md)

# 10 AI 功能與 LLM 設定

Voxinel 的三個 AI 功能共用同一組 **OpenAI 相容 LLM 端點**設定（Base URL + 模型名稱 + API Key）：

| 功能 | 觸發時機 | 作用 |
|---|---|---|
| AI 輔助校稿 | 關閉即時字幕／會議模式存檔前 | 修正錯字與標點、合併被切斷的句子，保留時間戳 |
| AI 會議摘要 | 會議模式關閉存檔時 | 產生含摘要、與會者、討論主題、重要決議、行動項目的 Markdown 摘要 |
| AI 助手 | 喚醒詞／`Ctrl+Shift+L` 對話 | 語音問答，多輪上下文，Markdown／KaTeX／Mermaid 回覆 |

## 方案 A：本機 Ollama（預設，零成本、完全離線）

1. 安裝 [Ollama](https://ollama.com) 並確認服務在背景運行
2. 拉取模型，例如：`ollama pull gemma4`（設定頁預設模型名 `gemma4:latest`，請以實際拉取的名稱為準）
3. 設定頁保持 Base URL `http://localhost:11434`，模型名稱填 Ollama 的模型 id，API Key 留空
4. 勾選要啟用的 AI 功能並保存

## 方案 B：OpenAI 或相容雲端服務

| 服務 | Base URL | 模型名稱範例 |
|---|---|---|
| OpenAI | `https://api.openai.com`（可省略 `/v1`） | `gpt-4o-mini` 等 |
| OpenRouter | `https://openrouter.ai/api/v1` | 依平台文件 |
| 其他 OpenAI 相容端點 | 依服務商文件（注意下方路徑規則） | 依服務商文件 |

填寫 API Key 並保存。

> **Base URL 路徑規則**：Ollama 與 OpenAI 填根目錄即可（程式會自動補 API 路徑）；**其他服務請填完整路徑**（含 `/v1` 等版本段）。填錯最常見的症狀是連線失敗或 404。

## 驗證是否生效

- **AI 助手**：按 `Ctrl+Shift+L` 問一句話，看是否正常回覆
- **AI 校稿／摘要**：開啟會議模式講一句話再關閉，檢查存檔內容是否被修正、有無產生摘要檔
- 程式啟動時會對端點做健康檢查；若當時 Ollama 尚未啟動，把 Ollama 開好後**重啟 Voxinel** 即可

## 常見問題對照

| 症狀 | 可能原因 |
|---|---|
| 校稿／摘要沒有生效 | 功能未勾選；LLM 端點不可用（啟動時健康檢查未通過） |
| 助手一直「思考中」 | 端點或模型名稱錯誤；API Key 無效 |
| 404 / model not found | 模型名稱與服務不符；Base URL 路徑不完整 |
| 回應很慢 | 雲端服務網路延遲；本機模型太大，可換較小的模型 |

---

[← 09 設定頁完整參考](09-settings.md) | [目錄](index.md) | [11 檔案與資料位置 →](11-data-and-files.md)
