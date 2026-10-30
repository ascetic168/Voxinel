[📖 目录](index.md)

# 11 文件与数据位置

## 模型目录

| 操作系统 | 位置 |
|---|---|
| Windows | `C:\ProgramData\Voxinel\models` |
| macOS | `~/Library/Application Support/Voxinel/models` |
| Linux | `~/.local/share/voxinel/models` |

| 子目录／文件 | 内容 | 约略大小 |
|---|---|---|
| `model.int8.onnx` + `tokens.txt` | SenseVoice 离线识别 | 229MB |
| `streaming\` | Zipformer 流式识别（4 个文件） | 58MB |
| `vad\` | Ten-VAD 语音活动检测 | 342KB |
| `speaker\` | 声纹识别模型＋`speakers.db` 声纹数据库 | 130MB |
| `tts\kokoro-int8-multi-lang-v1_1\` | TTS 语音合成 | 140MB |

## 记录文件

位置：**「文档」文件夹下的 `Voxinel` 子文件夹**（`Documents\Voxinel`）。托盘菜单「打开记录档目录」可一键开启。

| 文件 | 来源 |
|---|---|
| `caption_YYYYMMDD_HHMMSS.txt` | [即时字幕模式](05-mode-caption.md)逐字稿 |
| `conference_YYYYMMDD_HHMMSS.txt` | [会议模式](06-mode-conference.md)合并逐字稿 |
| `conference_summary_YYYYMMDD_HHMMSS.md` | AI 会议摘要 |

## 配置文件

| 项目 | 位置（Windows） |
|---|---|
| `config.json`（所有设置值） | `%APPDATA%\com.voxinel.app\config.json` |

设置会在程序运行期间自动保存，一般不需手动编辑。

## 日志

Voxinel 平时**不写日志文件**。需要诊断问题时，以 `--debug` 参数启动会开启控制台窗口显示详细运行信息。

## 完整移除

1. 主程序：从「应用和功能」（或对应的系统设置）卸载
2. 模型与声纹：删除上方的模型目录
3. 设置：删除 `config.json`
4. 记录文件：删除 `Documents\Voxinel` 文件夹

---

[← 10 AI 功能与 LLM 设置](10-ai-features.md) | [目录](index.md) | [12 常见问题与疑难排解 →](12-faq.md)
