[📖 目錄](index.md)

# 10 檔案與資料位置

## 模型目錄

| 作業系統 | 位置 |
|---|---|
| Windows | `C:\ProgramData\Voxinel\models` |
| macOS | `~/Library/Application Support/Voxinel/models` |
| Linux | `~/.local/share/voxinel/models` |

| 子目錄／檔案 | 內容 | 約略大小 |
|---|---|---|
| `model.int8.onnx` + `tokens.txt` | SenseVoice 離線辨識 | 229MB |
| `streaming\` | Zipformer 串流辨識（4 個檔案） | 58MB |
| `vad\` | Ten-VAD 語音活動偵測 | 342KB |
| `speaker\` | 聲紋辨識模型＋`speakers.db` 聲紋資料庫 | 130MB |

## 記錄檔

位置：**「文件」資料夾下的 `Voxinel` 子資料夾**（`Documents\Voxinel`）。托盤選單「打開記錄檔目錄」可一鍵開啟。

| 檔案 | 來源 |
|---|---|
| `caption_YYYYMMDD_HHMMSS.txt` | [即時字幕模式](05-mode-caption.md)逐字稿 |
| `conference_YYYYMMDD_HHMMSS.txt` | [會議模式](06-mode-conference.md)合併逐字稿 |
| `conference_summary_YYYYMMDD_HHMMSS.md` | AI 會議摘要 |

## 設定檔

| 項目 | 位置（Windows） |
|---|---|
| `config.json`（所有設定值） | `%APPDATA%\com.voxinel.app\config.json` |

設定會在程式運行期間自動保存，一般不需手動編輯。

## 日誌

Voxinel 平時**不寫日誌檔**。需要診斷問題時，以 `--debug` 參數啟動會開啟主控台視窗顯示詳細運行訊息。

## 完整移除

1. 主程式：從「應用程式與功能」（或對應的系統設定）解除安裝
2. 模型與聲紋：刪除上方的模型目錄
3. 設定：刪除 `config.json`
4. 記錄檔：刪除 `Documents\Voxinel` 資料夾

---

[← 09 AI 功能與 LLM 設定](09-ai-features.md) | [目錄](index.md) | [11 常見問題與疑難排解 →](11-faq.md)
