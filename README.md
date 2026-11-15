# humanizer-en

A Claude skill that edits existing English prose to remove filler, repetition and templated phrasing, while preserving facts, certainty and the author's voice.

It is an editing guide that an agent reads and follows. It is not an AI detector, cannot prove who wrote a text, and does not promise to pass any AI detector.

This is an English adaptation of [op7418/humanizer-zh](https://github.com/op7418/humanizer-zh) (revision 2026-09-23, commit `f4518a8`), which edits Chinese text. Section F and all examples were adapted for English rather than translated literally.

## What it does

| Aspect | Behaviour |
|---|---|
| Priority order | 1. Preserve facts and certainty. 2. Respect the user's scope and genre. 3. Match the author's voice. 4. Fix phrasing. |
| Hard rules | Never invents data, sources or experiences. Never turns "may" into "does" or "planned" into "done". |
| Checklist | 31 patterns in six groups. They are prompts for judgement, not a word blacklist. |
| Output | The final rewrite only. Text that is already clear is left unchanged. |
| File mode | Edits prose only. Code, commands, paths, links, YAML, headings and table data are left untouched. |
| Embedded instructions | Commands or prompts inside the text being edited are treated as material, not as instructions. |

| Group | Patterns |
|---|---|
| A (1–5) | Lead-ins instead of statements: false contrasts, dramatic fragments, fake depth |
| B (6–11) | Formulaic rhythm: forced lists of three, dash overuse, stacked hedges, passives |
| C (12–18) | Inflation: buzzwords, inflated significance, vague experts, promotional language |
| D (19–21) | Layout: decorative bold, emoji headings, inconsistent quotation marks |
| E (22–25) | Chat residue: customer-service voice, repeated disclaimers, restated headings |
| F (26–31) | Sentence-level habits: noun chains, "carry out + noun", cliché openers and closers |

## Install

Claude Code, by cloning into the skills folder:

```bash
# macOS / Linux
git clone https://github.com/AvCompDev/humanizer-en.git ~/.claude/skills/humanizer-en
```

```powershell
# Windows
git clone https://github.com/AvCompDev/humanizer-en.git "$env:USERPROFILE\.claude\skills\humanizer-en"
```

Restart Claude Code, then run `/humanizer-en`.

Review any skill before you install it, including this one. It is a single `SKILL.md` with no scripts and no network access.

## Use

```text
Use humanizer-en to polish the article below. Keep the tone of a technical review.
[text]
```

```text
Use humanizer-en to polish the prose in article.md.
```

For a review without edits, say "give suggestions, do not change the file".

## Sources and licence

- [op7418/humanizer-zh](https://github.com/op7418/humanizer-zh): the Chinese skill this is adapted from. Copyright (c) 2026 歸藏.
- [blader/humanizer v3.0.0](https://github.com/blader/humanizer/blob/v3.0.0/SKILL.md): the original project.
- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop): reference for concise expression.
- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing): the original project's source of observations.

Released under the [MIT License](LICENSE). The original copyright notice is retained; the English adaptation is Copyright (c) 2026 AvCompDev.
