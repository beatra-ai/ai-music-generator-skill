# AI Music Generator Skill

English | [简体中文](./README.zh-CN.md) | [日本語](./README.ja.md)

> 👉 See also [Lyrics to Song Skill](https://github.com/beatra-ai/lyrics-to-song-skill)

Turn a theme, lyrics, or reference audio into songs, instrumentals, and soundtracks, from inside Claude Code, Cursor, Codex, Windsurf, Cline, or OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-music-generator-skill) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Turn a theme, lyric, scene, or reference audio into reviewable songs, instrumentals, BGM, and soundtracks with a clear creative direction and focused revisions. |
| **Models** | Suno 6, MiniMax Music 3.0 |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="Cover art for &quot;Green Lights All the Way&quot;, a song about a late-night drive through an empty city. AI-generated with Beatra."></p>

*Cover art for "Green Lights All the Way", a song about a late-night drive through an empty city. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`music-generation-studio`](skills/music-generation-studio) | [SKILL.md](skills/music-generation-studio/SKILL.md) | 0.2.9 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/music-generation-studio). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/ai-music-generator-skill
```

As a Claude Code plugin:

```bash
claude plugin marketplace add beatra-ai/ai-music-generator-skill
claude plugin install music-generation-studio@ai-music-generator-skill
```

As a Codex plugin:

```bash
codex plugin marketplace add beatra-ai/ai-music-generator-skill
codex plugin add music-generation-studio@ai-music-generator-skill
```

As a GitHub Copilot CLI plugin:

```bash
copilot plugin marketplace add beatra-ai/ai-music-generator-skill
copilot plugin install music-generation-studio@ai-music-generator-skill
```

As a Gemini CLI extension:

```bash
gemini extensions install https://github.com/beatra-ai/ai-music-generator-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/ai-music-generator-skill music-generation-studio
```

Or clone this repository and copy `skills/music-generation-studio` into `~/.claude/skills/` for Claude Code,
`~/.cursor/skills/` for Cursor, `~/.agents/skills/` for Codex, `~/.codeium/windsurf/skills/` for Windsurf,
`~/.cline/skills/` for Cline, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the music-generation-studio skill from https://github.com/beatra-ai/ai-music-generator-skill (folder skills/music-generation-studio), then follow its SKILL.md to connect my Beatra account.
```

## Examples

<p align="center"><img src="assets/cover.webp" width="800" alt="Cover art for &quot;Green Lights All the Way&quot;, a song about a late-night drive through an empty city. AI-generated with Beatra."></p>

[▶ Listen (MP3)](assets/sample.mp3)

*First 60 seconds of "Green Lights All the Way", an indie-pop song with a female lead, written and produced from a late-night city drive theme. AI-generated with Beatra.*

Ask your agent:

```text
Write and produce an upbeat English indie-pop song with a female lead about a late-night drive through an empty city: restless and quiet at the start, carefree by the last chorus.
```

Prompt:

```text
Upbeat English indie-pop single about a late-night drive through an empty city. Arc: restless and quiet at the start, lifting into carefree release by the final chorus. Driving straight eighth-note groove, mid-fast tempo feel. Chorus-pedal electric guitar arpeggios, pulsing analog synth bass, bright vintage polysynth pads, crisp live drums with tambourine on the chorus. Compact conversational verses, rising pre-chorus, wide vowel-led chorus hook, short instrumental synth-guitar break, final chorus gains stacked harmonies, clean ending. Warm, slightly breathy female lead, natural English. Polished modern indie mix, wide stereo, warm tape sheen.
```

## Technical Specifications & Output Limits

As of 2026-10-18. Live list: https://docs.beatra.ai/en/docs/models

- **Uploads** — up to 100 MB per file; the per-model input limits below also apply
- **Text to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters
  - MiniMax Music 3.0: prompt up to 2000, lyrics up to 3500, title up to 100 characters
- **Reference audio to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters; reference audio 6–480 s (FLAC, MP3, WAV)
  - MiniMax Music 3.0: prompt up to 300, lyrics up to 1000, title up to 100 characters; reference audio 6–360 s, up to 50 MB (FLAC, MP3, WAV)

## Why use Beatra instead of calling model APIs directly

- **One account for every model this skill uses** — Text to music 2; Reference audio to music 2 (Suno 6, MiniMax Music 3.0) (as of 2026-10-18), behind one Beatra sign-in; no keys from individual model providers to manage.
- **You decide what gets paid for** — Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate.
- **Direction before rendering** — the skill plans, directs, and reviews the work, then renders it on Beatra.
- **Files you can verify** — every file under `skills/` matches the release archive on cdn.beatra.ai byte for byte, checked by SHA-256 before each push.
- **Updates you control** — no self-updater; update with the tool you installed it with.
- **Runs in your agent** — Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw.

## What you get

- **Develop the whole musical idea** — Turn a fragment into a coherent title, hook, lyric, structure, vocal direction, and arrangement.
- **Choose the route that fits the destination** — Make a vocal song, instrumental, BGM, jingle, soundtrack, multilingual track, or reference-led arrangement from an existing recording.
- **Refine the strongest result** — Hear every returned version, preserve what works, and turn the biggest gap into one focused next direction.

## Use cases

- **Original songs from an idea** — Develop a story, mood, lyric fragment, or hook into a structured vocal track with a clear musical identity.
- **Lyrics into a song** — Use complete lyrics you provide or develop singable words before choosing the genre, voice, and arrangement.
- **Video, campaign, and brand music** — Create BGM, soundtracks, jingles, and campaign music around pace, emotion, dialogue space, and ending needs.
- **Games, podcasts, and product experiences** — Build themes, intros, transitions, atmosphere, and instrumental cues from a functional brief.
- **Multilingual and reference-led directions** — Plan bilingual songs or new arrangements from reference audio, then review melody, vocal character, and arrangement against the intended direction.

## FAQ

### What can Music Generation Studio make?

It can develop and create original songs, instrumentals, BGM, video and game soundtracks, jingles, brand music, podcast themes, multilingual tracks, and reference-led new arrangements.

### Can it write lyrics or use lyrics I already have?

Yes. It can develop singable lyrics from a brief or use complete lyrics you provide, keeping the words aligned with the selected genre, mood, structure, vocal, and arrangement direction.

### How can I shape instrumentals, loopable BGM, and track length?

Set the target duration, ending, loop point, energy curve, dialogue space, and instrumental palette, then listen to the result and refine the timing or edit point for its destination.

### Does it only use Suno?

Suno 6 is the creative default. You can explicitly choose another currently available music model when its capabilities fit the brief.

### Can it use reference audio for a new arrangement?

Yes. Choose what should carry over and what should change, then review the returned melody, vocal character, energy, instrumentation, and arrangement against that direction.

## Updates and security

Since the 2026-10 release, this skill contains no self-updater: it runs only the
files you installed and never replaces them on its own. Update it with the tool
you installed it with — `npx skills update music-generation-studio` or `gh skill update music-generation-studio`.
Details: `references/updates-and-security.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.

## Links

- Website — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-music-generator-skill
- Docs — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-music-generator-skill
- Console — https://console.beatra.ai
- For AI agents — https://beatra.ai/llms.txt (index) · https://beatra.ai/llms-full.txt (every skill in one file)
