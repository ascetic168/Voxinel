# Voxinel

**[正體中文](README.md)** | **[简体中文](README.zh-CN.md)** | **[English](README.en.md)**

![Version](https://img.shields.io/badge/version-0.6.0-2563eb) ![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-64748b) ![Privacy](https://img.shields.io/badge/audio-100%25%20local-16a34a) ![GPU](https://img.shields.io/badge/GPU-not%20required-16a34a) ![License](https://img.shields.io/badge/license-freeware-f59e0b)

> **按住 Ctrl 开口说话，放开自动打字。**
> 全本地语音输入工具 — 流式识别边说边出字，SenseVoice 高精度修正；纯 CPU 流畅运行，免 GPU、免上云、免 API 密钥。

📖 **完整使用说明**：[正體中文](docs/zh-TW/index.md) · [简体中文](docs/zh-CN/index.md) · [English](docs/en/index.md)

## 30 秒上手

| 想做什么 | 怎么做 |
|---|---|
| 把说的话打成字 | 按住 `Ctrl` 说话 → 放开自动识别、贴上 |
| 长段落连续听写 | 连按两下**右** `Ctrl` 开启倾听模式，逐句自动贴上 |
| 帮视频／通话上字幕 | 系统托盘菜单 →「即时字幕模式」 |
| 会议逐字稿＋AI 摘要 | 系统托盘菜单 →「会议模式」 |
| 免打字问 AI | 说出「小花同学」，或按 `Ctrl+Shift+L` |

第一次使用：[下载安装包](https://github.com/ascetic168/Voxinel/releases) → 启动后自动下载模型（约 600MB，仅一次性）→ 开始说话。

## 为什么选择 Voxinel

### 1. 音频不出你的电脑，免 GPU 也能流畅跑
所有识别都在本机完成，音频不会上传到任何服务器——适合企业与保密机关的内部环境。流式 Zipformer 即时识别＋SenseVoice 离线修正的双引擎架构，**纯 CPU 即可流畅运行**，无需显卡、无需 CUDA、无需网络与 API 密钥。

### 2. 边说边出字，放开即成稿
独创的流式－离线双引擎协作：按下热键的瞬间流式引擎（Zipformer）就开始识别、即时显示；放开后离线引擎（SenseVoice）对完整音频做高精度重识别，自动加上标点并替换流式结果。即时反馈与最终品质，两者兼得。

### 3. 单键 Ctrl 就能说话，却不干扰你原来的键盘习惯
按住 Ctrl 即录音，程序内建完整的使用意图判断：与其他修饰键连按不启动、录音中按任何键立即取消、过短录音自动丢弃、识别结果为空不贴上——Ctrl+C、Ctrl+V 与输入法切换完全不会被干扰，贴上后剪贴板原内容自动还原。

## 与纯云端语音输入的差别

| | Voxinel | 纯云端工具 |
|---|---|---|
| 音频去向 | 完全留在本机 | 上传第三方服务器 |
| 离线使用 | ✅ 装好模型后完全离线 | ❌ 需要网络 |
| 硬件需求 | 纯 CPU，免 GPU | 不需要（但运算在云端） |
| 即时反馈 | ✅ 边说边出字 | 依服务而定 |
| 保密环境 | ✅ 适合企业／机关内部 | 通常被禁止 |
| 费用 | 免费；选用云端引擎才需密钥 | 订阅或按量计费 |

## 五种模式，各司其职

| 模式 | 开启方式 | 声音来源 | 适用情境 |
|---|---|---|---|
| **按住说话**（默认） | 按住 `Ctrl` | 麦克风 | 取代打字 |
| **倾听模式** | 连按两下右 `Ctrl` | 麦克风 | 长文听写，逐句贴上 |
| **即时字幕模式** 🧪 | 系统托盘菜单 | 系统播放的声音 | 视频／演讲／通话字幕 |
| **会议模式** 🧪 | 系统托盘菜单 | 麦克风＋系统音频 | 会议逐字稿、说话人标识、AI 摘要 |

五种模式互斥运作、自动切换；细节见[使用说明](docs/zh-CN/index.md)。

## 功能特色

**核心输入**
- 全本地双引擎 — 流式 Zipformer 即时反馈＋SenseVoice 离线修正，全程离线零隐私顾虑
- 纯 CPU 流畅运行 — 无需 GPU、无需 CUDA，一般笔电或桌机皆可
- 自动标点 — 直接输出。，？等标点，无需额外模型
- 语音活动检测 — Ten-VAD 过滤静音停顿，消除垃圾字符（灵敏度可调）
- 繁简转换 — 依系统地区自动转换，流式与最终结果皆适用

**进阶模式**
- 即时字幕模式 🧪 — 系统音频即时字幕，关闭时自动存档
- 会议模式 🧪 — 近端＋远端双轨记录、回音抑制、声纹自动标识说话人

**AI 加持（透过本机 Ollama 或 OpenAI 兼容 LLM）**
- AI 辅助校稿 — 关闭字幕／会议模式时自动修正文稿
- AI 会议摘要 — 会议结束自动产生结构化摘要

**便利与整合**
- 多引擎 ASR — 本地（默认）、腾讯云 ASR、Google Gemini，自定义优先顺序与自动 Fallback
- 系统托盘常驻、开机自启、记录文件一键开启、剪贴板保护
- 多语言界面 — 繁體中文／简体中文／English
- 中国大陆下载加速 — 简体中文环境自动使用镜像站

## 支持的 ASR 引擎

| 引擎 | 类型 | 说明 |
|---|---|---|
| 本地双引擎（默认） | 离线 | 流式 Zipformer（中英）＋SenseVoice-Small（中英日韩粤、自动标点），免密钥，模型首次启动自动下载 |
| 腾讯云 ASR | 云端 | SentenceRecognition API；普通话／视频／英文／粤语／川渝方言；需 Secret ID＋Secret Key |
| Google Gemini | 云端 | gemini-3.5-transcribe（默认）等系列；自动标点、移除语气词；需 API Key |

模型存放位置：`C:\ProgramData\Voxinel\models\`（Windows）。

## 安装与快速开始

1. 至 [Releases 页面](https://github.com/ascetic168/Voxinel/releases)下载安装包
2. 首次启动自动开启设置窗口，点击下载即自动取得所有模型（流式、离线、VAD、声纹合计约 **460MB**）
3. 下载完成即可使用，无需设置任何 API 密钥；之后完全离线运行

## 截图

<!-- TODO: 放入实际截图后，将 docs/images/ 下的图档取消注解即可
| 设置窗口 | 按住说话 Overlay | 会议模式双字幕 |
|---|---|---|
| ![设置窗口](docs/images/settings.png) | ![按住说话](docs/images/overlay-ptt.png) | ![会议模式](docs/images/conference.png) |
-->

*截图即将补上。*

## 最新版本

✅ **已发布 v0.6.0** — 声纹辨识大改版：比对/注册策略重构，修复影片音源同一人被反复注册成多个 Speaker 的碎片化问题；声纹管理新增「声纹登记」流程（朗读句子、3 秒倒数、10 秒录音、名称/注解），登记的声纹可附加注解。

<details><summary>v0.5.10</summary>v0.5.10 — 强化 PTT 误触防护：与其他修饰键连按不启动录音、录音中任何按键立即取消，空识别结果不再注入模拟贴上按键，解决键盘输入偶尔残留怪字符的问题。</details>

<details><summary>v0.5.9</summary>v0.5.9 — AI 助手语音回复音色可在设置页选择与试听（默认改用中文音色），助手窗口开启时 PTT 热键不再误触。</details>

<details><summary>v0.5.8</summary>v0.5.8 — 修复从托盘菜单启动倾听模式时，识别文字未贴入目标窗口的问题。</details>

## 授权

闭源软件，免费使用。由朱国栋 (Charlie Chu) 开发。
