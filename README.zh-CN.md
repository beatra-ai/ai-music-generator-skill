# AI Music Generator Skill

[English](./README.md) | 简体中文

从主题、歌词或参考音频生成歌曲、纯音乐和配乐，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 从主题、歌词、画面或参考音频开始，明确曲风、结构与人声方向，制作可试听的歌曲、纯音乐、BGM 和视频配乐，再集中调整最关键的问题。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Green Lights All the Way》的封面，画面是深夜空无一人的城市街道。由 Beatra AI 生成。"></p>

*歌曲《Green Lights All the Way》的封面，画面是深夜空无一人的城市街道。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`music-generation-studio`](skills/music-generation-studio) | [SKILL.md](skills/music-generation-studio/SKILL.md) | 0.1.7 |

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

也可以克隆本仓库，把 `skills/music-generation-studio` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-music-generator-skill 安装 music-generation-studio skill（目录 skills/music-generation-studio），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="歌曲《Green Lights All the Way》的封面，画面是深夜空无一人的城市街道。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*独立流行歌曲《Green Lights All the Way》前 60 秒，女声主唱，主题是深夜在城市里开车。由 Beatra AI 生成。*

提示词：

```text
Upbeat English indie-pop single about a late-night drive through an empty city. Arc: restless and quiet at the start, lifting into carefree release by the final chorus. Driving straight eighth-note groove, mid-fast tempo feel. Chorus-pedal electric guitar arpeggios, pulsing analog synth bass, bright vintage polysynth pads, crisp live drums with tambourine on the chorus. Compact conversational verses, rising pre-chorus, wide vowel-led chorus hook, short instrumental synth-guitar break, final chorus gains stacked harmonies, clean ending. Warm, slightly breathy female lead, natural English. Polished modern indie mix, wide stereo, warm tape sheen.
```

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

Suno 5.5 是默认创作模型。你也可以明确选择当前可用且适合需求的其他音乐模型。

### 可以根据参考音频制作新编曲吗？

可以。先说明希望保留和改变的部分，再根据生成结果试听旋律、人声质感、能量、乐器和编曲是否符合方向。

## 更新

安装后的 skill 每天最多检查一次新版本，替换前先校验官方归档，任何一步失败都不会动你已安装的版本。
随时可以关闭，见 skill 内的 `references/automatic-updates-and-safety.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。
