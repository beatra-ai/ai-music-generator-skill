# AI Music Generator Skill

[English](./README.md) | 简体中文 | [日本語](./README.ja.md)

> 👉 也看看 [Lyrics to Song Skill](https://github.com/beatra-ai/lyrics-to-song-skill)

从主题、歌词或参考音频生成歌曲、纯音乐和配乐，在 Claude Code、Cursor、Codex、Windsurf、Cline 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-music-generator-skill) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 从主题、歌词、画面或参考音频开始，明确曲风、结构与人声方向，制作可试听的歌曲、纯音乐、BGM 和视频配乐，再集中调整最关键的问题。 |
| **底层模型** | Suno 6、MiniMax Music 3.0 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Green Lights All the Way》的封面，画面是深夜空无一人的城市街道。由 Beatra AI 生成。"></p>

*歌曲《Green Lights All the Way》的封面，画面是深夜空无一人的城市街道。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`music-generation-studio`](skills/music-generation-studio) | [SKILL.md](skills/music-generation-studio/SKILL.md) | 0.2.9 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/music-generation-studio) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-music-generator-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-music-generator-skill music-generation-studio
```

也可以克隆本仓库，把 `skills/music-generation-studio` 复制到 `~/.claude/skills/`（Claude Code）、`~/.cursor/skills/`（Cursor）、`~/.agents/skills/`（Codex）、`~/.codeium/windsurf/skills/`（Windsurf）、`~/.cline/skills/`（Cline）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-music-generator-skill 安装 music-generation-studio skill（目录 skills/music-generation-studio），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Green Lights All the Way》的封面，画面是深夜空无一人的城市街道。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*独立流行歌曲《Green Lights All the Way》前 60 秒，女声主唱，主题是深夜在城市里开车。由 Beatra AI 生成。*

在你的 Agent 里这样说：

```text
写一首轻快的英文独立流行歌，女声主唱，主题是深夜开车穿过空荡的城市：开头克制安静，最后一段副歌放开。
```

提示词：

```text
Upbeat English indie-pop single about a late-night drive through an empty city. Arc: restless and quiet at the start, lifting into carefree release by the final chorus. Driving straight eighth-note groove, mid-fast tempo feel. Chorus-pedal electric guitar arpeggios, pulsing analog synth bass, bright vintage polysynth pads, crisp live drums with tambourine on the chorus. Compact conversational verses, rising pre-chorus, wide vowel-led chorus hook, short instrumental synth-guitar break, final chorus gains stacked harmonies, clean ending. Warm, slightly breathy female lead, natural English. Polished modern indie mix, wide stereo, warm tape sheen.
```

## 技术规格与输出限制

截至 2026-10-18。实时列表：https://docs.beatra.ai/zh/docs/models

- **上传** — 单个文件最大 100 MB；同时适用下方各模型的输入限制
- **文生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；MP3
  - Suno 6：提示词最多 500、歌词最多 5000、标题最多 80 字符
  - MiniMax Music 3.0：提示词最多 2000、歌词最多 3500、标题最多 100 字符
- **参考音频生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；MP3
  - Suno 6：提示词最多 500、歌词最多 5000、标题最多 80 字符；参考音频 6–480 秒（FLAC、MP3、WAV）
  - MiniMax Music 3.0：提示词最多 300、歌词最多 1000、标题最多 100 字符；参考音频 6–360 秒，最大 50 MB（FLAC、MP3、WAV）

## 为什么用 Beatra，而不是直接调用模型 API

- **一个账号用到本 skill 的全部模型** — 文生音乐 2；参考音频生音乐 2（Suno 6、MiniMax Music 3.0）（截至 2026-10-18），一次 Beatra 登录即可使用，不必分别管理各家模型的 key。
- **花不花钱由你决定** — 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费。
- **先策划，再生成** — skill 先帮你规划、指导和检查，再在 Beatra 上生成。
- **文件可以核验** — `skills/` 下的每个文件都与 cdn.beatra.ai 上的发布归档逐字节一致，每次推送前用 SHA-256 校验。
- **更新由你掌控** — 不含自更新程序；用安装时的工具更新。
- **在你的 Agent 里运行** — Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw。

## 你能得到什么

- **把音乐想法发展完整** — 把零散灵感整理成彼此呼应的歌名、记忆点、歌词、结构、人声与编曲。
- **根据使用场景选择路线** — 制作人声歌曲、纯音乐、BGM、广告歌、视频配乐、多语言作品或基于参考音频的新编曲。
- **集中优化最好的结果** — 试听所有返回版本，保留表现好的部分，只围绕最需要改进的问题制定下一版方案。

## 适用场景

- **从灵感创作原创歌曲** — 把故事、情绪、歌词片段或副歌记忆点发展成结构完整、风格统一的人声歌曲。
- **把歌词变成歌曲** — 使用你提供的完整歌词，或先完善可唱歌词，再确定曲风、人声与编曲。
- **视频、营销与品牌音乐** — 根据节奏、情绪、对白空间和结尾需要制作 BGM、配乐、广告歌与品牌音乐。
- **游戏、播客与产品体验** — 根据功能需求，为主题曲、片头、转场和氛围场景创作纯音乐。
- **多语言与参考音频路线** — 规划双语歌曲或参考音频的新编曲，再根据实际结果试听旋律、人声质感、能量和编曲方向。

## 常见问题

### 音乐生成工作室可以制作什么？

可以发展并制作原创歌曲、纯音乐、BGM、视频与游戏配乐、广告歌、品牌音乐、播客主题、多语言歌曲，以及基于参考音频的新编曲。

### 可以写歌词或使用我已有的歌词吗？

可以。它可以根据需求完善可唱歌词，也可以使用你提供的完整歌词，并让歌词与所选曲风、情绪、结构、人声和编曲方向保持一致。

### 怎样设计纯音乐、循环 BGM 和目标时长？

设置目标时长、结尾、循环点、能量变化、对白空间和乐器方向，生成后试听完整结果，再针对使用场景调整节奏或剪辑点。

### 只能使用 Suno 吗？

Suno 6 是默认创作模型。你也可以明确选择当前可用且适合需求的其他音乐模型。

### 可以根据参考音频制作新编曲吗？

可以。先说明希望保留和改变的部分，再根据生成结果试听旋律、人声质感、能量、乐器和编曲是否符合方向。

## 更新与安全

自 2026 年 10 月的版本起，本 skill 不再包含自更新程序：它只运行你安装的文件，从不自行替换。
请用安装时的工具更新——`npx skills update music-generation-studio` 或 `gh skill update music-generation-studio`。
详见 skill 内的 `references/updates-and-security.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。

## 相关链接

- 官网 — https://www.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-music-generator-skill
- 文档 — https://docs.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-music-generator-skill
- 控制台 — https://console.beatra.cn
- 给 AI Agent 读的说明 — https://www.beatra.cn/llms.txt （索引）· https://www.beatra.cn/llms-full.txt （全部 skill 合成一个文件）

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
