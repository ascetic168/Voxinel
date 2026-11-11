[📖 Contents](index.md)

# 10 Files & Data Locations

## Model Directory

| OS | Location |
|---|---|
| Windows | `C:\ProgramData\Voxinel\models` |
| macOS | `~/Library/Application Support/Voxinel/models` |
| Linux | `~/.local/share/voxinel/models` |

| Subfolder／file | Contents | Approx. size |
|---|---|---|
| `model.int8.onnx` + `tokens.txt` | SenseVoice offline recognition | 229MB |
| `streaming\` | Zipformer streaming recognition (4 files) | 58MB |
| `vad\` | Ten-VAD voice activity detection | 342KB |
| `speaker\` | Speaker recognition model + `speakers.db` voiceprint database | 130MB |

## Transcripts

Location: the `Voxinel` subfolder of your **Documents folder** (`Documents\Voxinel`). The tray item "Open transcript folder" opens it directly.

| File | Produced by |
|---|---|
| `caption_YYYYMMDD_HHMMSS.txt` | [Live Caption Mode](05-mode-caption.md) transcript |
| `conference_YYYYMMDD_HHMMSS.txt` | [Conference Mode](06-mode-conference.md) merged transcript |
| `conference_summary_YYYYMMDD_HHMMSS.md` | AI meeting summary |

## Configuration

| Item | Location (Windows) |
|---|---|
| `config.json` (all settings) | `%APPDATA%\com.voxinel.app\config.json` |

Settings are saved automatically while the app runs; manual editing is normally unnecessary.

## Logs

Voxinel **does not write log files** in normal operation. For diagnostics, launch with the `--debug` argument to open a console window with detailed messages.

## Full Removal

1. Main program: uninstall from "Apps & features" (or your system's equivalent)
2. Models & voiceprints: delete the model directory above
3. Settings: delete `config.json`
4. Transcripts: delete the `Documents\Voxinel` folder

---

[← 09 AI Features & LLM Setup](09-ai-features.md) | [Contents](index.md) | [11 FAQ & Troubleshooting →](11-faq.md)
