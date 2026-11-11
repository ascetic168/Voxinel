[📖 目录](index.md)

# 09 AI 功能与 LLM 设置

Voxinel 的两个 AI 功能共用同一组 **OpenAI 兼容 LLM 端点**设置（Base URL + 模型名称 + API Key）：

| 功能 | 触发时机 | 作用 |
|---|---|---|
| AI 辅助校稿 | 关闭即时字幕／会议模式存档前 | 修正错别字与标点、合并被切断的句子，保留时间戳 |
| AI 会议摘要 | 会议模式关闭存档时 | 产生含摘要、与会者、讨论主题、重要决议、行动项目的 Markdown 摘要 |

## 方案 A：本机 Ollama（默认，零成本、完全离线）

1. 安装 [Ollama](https://ollama.com) 并确认服务在背景运行
2. 拉取模型，例如：`ollama pull gemma4`（设置页默认模型名 `gemma4:latest`，请以实际拉取的名称为准）
3. 设置页保持 Base URL `http://localhost:11434`，模型名称填 Ollama 的模型 id，API Key 留空
4. 勾选要启用的 AI 功能并保存

## 方案 B：OpenAI 或兼容云端服务

| 服务 | Base URL | 模型名称范例 |
|---|---|---|
| OpenAI | `https://api.openai.com`（可省略 `/v1`） | `gpt-4o-mini` 等 |
| OpenRouter | `https://openrouter.ai/api/v1` | 依平台文件 |
| 其他 OpenAI 兼容端点 | 依服务商文件（注意下方路径规则） | 依服务商文件 |

填写 API Key 并保存。

> **Base URL 路径规则**：Ollama 与 OpenAI 填根目录即可（程序会自动补 API 路径）；**其他服务请填完整路径**（含 `/v1` 等版本段）。填错最常见的症状是连接失败或 404。

## 验证是否生效

- **AI 校稿／摘要**：开启会议模式讲一句话再关闭，检查存档内容是否被修正、有无产生摘要文件
- 程序启动时会对端点做健康检查；若当时 Ollama 尚未启动，把 Ollama 开好后**重启 Voxinel** 即可

## 常见问题对照

| 症状 | 可能原因 |
|---|---|
| 校稿／摘要没有生效 | 功能未勾选；LLM 端点不可用（启动时健康检查未通过） |
| 404 / model not found | 模型名称与服务不符；Base URL 路径不完整 |
| 回应很慢 | 云端服务网络延迟；本机模型太大，可换较小的模型 |

---

[← 08 设置页完整参考](08-settings.md) | [目录](index.md) | [10 文件与数据位置 →](10-data-and-files.md)
