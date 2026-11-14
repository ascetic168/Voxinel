# Voxinel

**[正體中文](README.md)** | **[简体中文](README.zh-CN.md)** | **[English](README.en.md)**

![Version](https://img.shields.io/badge/version-0.6.1-2563eb) ![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-64748b) ![Privacy](https://img.shields.io/badge/audio-100%25%20local-16a34a) ![GPU](https://img.shields.io/badge/GPU-not%20required-16a34a) ![License](https://img.shields.io/badge/license-freeware-f59e0b)

> **按住 Ctrl 開口說話，放開自動打字。**
> 全本地語音輸入工具 — 串流辨識邊說邊出字，SenseVoice 高精度修正；純 CPU 流暢運行，免 GPU、免上雲、免 API 金鑰。

📖 **完整使用說明書**：[正體中文](docs/zh-TW/index.md) · [简体中文](docs/zh-CN/index.md) · [English](docs/en/index.md)

## 30 秒上手

| 想做什麼 | 怎麼做 |
|---|---|
| 把說的話打成字 | 按住 `Ctrl` 說話 → 放開自動辨識、貼上 |
| 長段落連續聽寫 | 連按兩下**右** `Ctrl` 開啟傾聽模式，逐句自動貼上 |
| 幫影片／通話上字幕 | 系統托盤選單 →「即時字幕模式」 |
| 會議逐字稿＋AI 摘要 | 系統托盤選單 →「會議模式」 |
| 免打字問 AI | 說出「小花同學」，或按 `Ctrl+Shift+L` |

第一次使用：[下載安裝檔](https://github.com/ascetic168/Voxinel/releases) → 啟動後自動下載模型（約 600MB，僅一次性）→ 開始說話。

## 為什麼選擇 Voxinel

### 1. 音訊不出你的電腦，免 GPU 也能流暢跑
所有辨識都在本機完成，音訊不會上傳到任何伺服器——適合企業與保密機關的內部環境。串流 Zipformer 即時辨識＋SenseVoice 離線修正的雙引擎架構，**純 CPU 即可流暢運行**，無需顯示卡、無需 CUDA、無需網路與 API 金鑰。

### 2. 邊說邊出字，放開即成稿
獨創的串流－離線雙引擎協作：按下熱鍵的瞬間串流引擎（Zipformer）就開始辨識、即時顯示；放開後離線引擎（SenseVoice）對完整音訊做高精度重辨，自動加上標點並替換串流結果。即時回饋與最終品質，兩者兼得。

### 3. 單鍵 Ctrl 就能說話，卻不干擾你原來的鍵盤習慣
按住 Ctrl 即錄音，程式內建完整的使用意圖判斷：與其他修飾鍵連按不啟動、錄音中按任何鍵立即取消、過短錄音自動丟棄、辨識結果為空不貼上——Ctrl+C、Ctrl+V 與輸入法切換完全不會被干擾，貼上後剪貼簿原內容自動還原。

## 與純雲端語音輸入的差別

| | Voxinel | 純雲端工具 |
|---|---|---|
| 音訊去向 | 完全留在本機 | 上傳第三方伺服器 |
| 離線使用 | ✅ 裝好模型後完全離線 | ❌ 需要網路 |
| 硬體需求 | 純 CPU，免 GPU | 不需要（但運算在雲端） |
| 即時回饋 | ✅ 邊說邊出字 | 依服務而定 |
| 保密環境 | ✅ 適合企業／機關內部 | 通常被禁止 |
| 費用 | 免費；選用雲端引擎才需金鑰 | 訂閱或按量計費 |

## 五種模式，各司其職

| 模式 | 開啟方式 | 聲音來源 | 適用情境 |
|---|---|---|---|
| **按住說話**（預設） | 按住 `Ctrl` | 麥克風 | 取代打字 |
| **傾聽模式** | 連按兩下右 `Ctrl` | 麥克風 | 長文聽寫，逐句貼上 |
| **即時字幕模式** 🧪 | 系統托盤選單 | 系統播放的聲音 | 影片／演講／通話字幕 |
| **會議模式** 🧪 | 系統托盤選單 | 麥克風＋系統音訊 | 會議逐字稿、說話人標示、AI 摘要 |

五種模式互斥運作、自動切換；細節見[使用說明書](docs/zh-TW/index.md)。

## 功能特色

**核心輸入**
- 全本地雙引擎 — 串流 Zipformer 即時回饋＋SenseVoice 離線修正，全程離線零隱私疑慮
- 純 CPU 流暢運行 — 無需 GPU、無需 CUDA，一般筆電或桌機皆可
- 自動標點 — 直接輸出。，？等標點，無需額外模型
- 語音活動偵測 — Ten-VAD 過濾靜音停頓，消除垃圾字符（敏感度可調）
- 繁簡轉換 — 依系統地區自動轉換，串流與最終結果皆適用

**進階模式**
- 即時字幕模式 🧪 — 系統音訊即時字幕，關閉時自動存檔
- 會議模式 🧪 — 近端＋遠端雙軌記錄、回音抑制、聲紋自動標示說話人、右下角按鈕暫停近端錄音

**AI 加持（透過本機 Ollama 或 OpenAI 相容 LLM）**
- AI 輔助校稿 — 關閉字幕／會議模式時自動修正文稿
- AI 會議摘要 — 會議結束自動產生結構化摘要

**便利與整合**
- 多引擎 ASR — 本地（預設）、騰訊雲 ASR、Google Gemini，自訂優先順序與自動 Fallback
- 系統托盤常駐、開機自啟、記錄檔一鍵開啟、剪貼簿保護
- 多語言介面 — 繁體中文／简体中文／English
- 中國大陸下載加速 — 简体中文環境自動使用鏡像站

## 支援的 ASR 引擎

| 引擎 | 類型 | 說明 |
|---|---|---|
| 本地雙引擎（預設） | 離線 | 串流 Zipformer（中英）＋SenseVoice-Small（中英日韓粵、自動標點），免金鑰，模型首次啟動自動下載 |
| 騰訊雲 ASR | 雲端 | SentenceRecognition API；普通話／視頻／英文／粵語／川渝方言；需 Secret ID＋Secret Key |
| Google Gemini | 雲端 | gemini-3.5-transcribe（預設）等系列；自動標點、移除語氣詞；需 API Key |

模型存放位置：`C:\ProgramData\Voxinel\models\`（Windows）。

## 安裝與快速開始

1. 至 [Releases 頁面](https://github.com/ascetic168/Voxinel/releases)下載安裝檔
2. 首次啟動自動開啟設定視窗，點擊下載即自動取得所有模型（串流、離線、VAD、聲紋合計約 **460MB**）
3. 下載完成即可使用，無需設定任何 API 金鑰；之後完全離線運行

## 截圖

<!-- TODO: 放入實際截圖後，將 docs/images/ 下的圖檔取消註解即可
| 設定視窗 | 按住說話 Overlay | 會議模式雙字幕 |
|---|---|---|
| ![設定視窗](docs/images/settings.png) | ![按住說話](docs/images/overlay-ptt.png) | ![會議模式](docs/images/conference.png) |
-->

*截圖即將補上。*

## 最新版本

✅ **已發布 v0.6.1** — 斷句大改版：會議／字幕模式移除連續講話強制切斷，改由靜音確認與聲紋換人偵測決定斷行；修復長段落下 Speaker 標籤消失問題，unknown 講者改為顯示以利事後登錄；抑制近端幻影段落；新增會議麥克風靜音鈕與字幕模式 toast 回饋。

<details><summary>v0.5.10</summary>v0.5.10 — 強化 PTT 誤觸防護：與其他修飾鍵連按不啟動錄音、錄音中任何按鍵立即取消，空辨識結果不再注入模擬貼上按鍵，解決鍵盤輸入偶爾殘留怪字元的問題。</details>

<details><summary>v0.5.9</summary>v0.5.9 — AI 助手語音回覆音色可在設定頁選擇與試聽（預設改用中文音色），助手視窗開啟時 PTT 熱鍵不再誤觸。</details>

<details><summary>v0.5.8</summary>v0.5.8 — 修復從托盤選單啟動傾聽模式時，辨識文字未貼入目標視窗的問題。</details>

## 授權

閉源軟體，免費使用。由朱國棟 (Charlie Chu) 開發。
