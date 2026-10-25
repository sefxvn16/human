# human

**English** | [Tiếng Việt](README.vi.md)

A skill for AI assistants that removes the typical patterns of AI writing from finished documents: stock vocabulary in place of facts, mechanical triplets, fake balance, tacked-on analysis, slogan-like closing lines. It works for Vietnamese and English text. The skill instructions (`SKILL.md`) are written in Vietnamese.

## What the skill does

Language models tend to replace specific, rare details with generic, positive wording that fits any case. The text then reads as vague and inflated. This skill treats the cause, not the surface: it keeps the real details found in the input instead of swapping one word for another.

- **4 base principles** that outrank the rules: do not invent, follow the genre's own standard, treat rules as checks and not quotas, keep the author's meaning.
- **20 patterns to avoid**, such as empty vocabulary, negative parallelism, false ranges, vague sources, repeated summaries, rigid structures, hidden actors, false balance, synonym-swapping for terms.
- **Before writing:** the skill checks unconfirmed facts and the target reader, and asks everything in one round.
- **Self-check before delivery:** a pass over the 20 patterns, a concreteness test, a new-pattern test, then a 5-criterion score (directness, rhythm, trust in the reader, naturalness, concision). Below 35/50 means revise.
- **Reviewing existing text:** lists violations by rule number, reports the score, then gives the revised text without changing claims, terms or figures.

## Boundaries

- Applies to finished documents the user will send or publish: applications, letters, reports, essays, website and social content, administrative or legal text.
- Does **not** apply to ordinary chat answers, explanations or analysis.
- Covers form of expression only. It does not make content deeper or better sourced.
- It is not a tool for beating AI detectors and gives no guarantee against them.

## Folder structure

```
human/
  SKILL.md
  references/
    vietnamese-patterns.md   # Vietnamese examples for quick recognition
    english-patterns.md      # English phrase and structure lists
    LICENSE-stop-slop.txt    # MIT license of the adapted material
README.md
README.vi.md
LICENSE.md
```

## Installation

### Claude apps (claude.ai, Claude desktop)

1. Download the repo and zip the `human` folder as `human.zip` (the zip must contain the `human` folder at its top level).
2. Open Claude, go to **Customize → Skills**, click **+** → **Create skill** → **Upload a skill**, and choose `human.zip`. Menu names and locations may differ between app versions. Skills require code execution to be enabled.
3. Check that the `human` skill is listed and turned on.

### Claude Code

Copy the `human` folder into `~/.claude/skills/` (available in all projects) or into a project's `.claude/skills/`, then restart Claude Code.

## Usage

The skill triggers when you ask for a finished document, or when you give it a text and ask to make it sound less like AI. You can also call it with `/human`. Examples:

- "Write a cover letter for this job: …"
- "/human Review this report and fix the AI-sounding parts, keep all figures."

## Limits

- The Vietnamese pattern list is based on observation and English-language sources. No validated Vietnamese study backs it.
- The score is an internal aid, not a measurement.
- No pattern list is reliable enough to prove that a text was written by AI.

## Feedback

Please use the repo's **Issues**. It helps to include: the original text and what you asked for (personal or confidential information removed), the result you expected and the result you got.

## License

Released under **CC BY-NC 4.0**: free for non-commercial use with attribution. For commercial use, contact the author via **Issues**. Third-party material is listed in [LICENSE.md](LICENSE.md).
