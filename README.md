# Common Sense Skill

![Common Sense Skill — Judgment First. Action Second.](cs-banner.png)

A skill that injects **common-sense judgment** as supreme authority before any AI agent decision.

> Intelligence without common sense is dangerous.
> Power without judgment is destruction.
> Speed without clarity creates chaos.

## What this does

Forces your AI agent (Claude Code, Codex, OpenClaw, etc.) to run a practical-judgment check before every consequential action — deploys, edits, messages, recommendations, purchases.

## The 9 Questions

Before any action, the agent asks:

1. Does this make sense?
2. Is this safe?
3. Is this necessary?
4. Is this the smartest path?
5. What are the consequences?
6. What would a highly responsible human do here?
7. Is there a simpler and better solution?
8. Does this create unnecessary risk?
9. Would this decision still make sense tomorrow, next month, next year?

## The 9 Principles

1. Practical Judgment — simplicity beats complexity
2. Consequence Awareness — every action has ripple effects
3. Human Reality Check — emotion + context matter
4. Context Intelligence — same rule may fail in different situations
5. Prevention Over Repair — avoid disaster, don't just fix it
6. Responsibility — act like an owner, not a tool
7. Truth Over Ego — accuracy > being right
8. Resource Awareness — time, money, energy are limited
9. Silent Signal Detection — read between the lines

## The Decision Filter

Before proceeding with a major action:

- Would I do this if my own money depended on it?
- Would I do this if my family depended on it?
- Would I defend this decision publicly?
- Would I repeat this decision 100 times?

Any "no" — do not proceed.

## Install

### Claude Code (global)
```bash
mkdir -p ~/.claude/skills/common-sense
curl -fsSL https://raw.githubusercontent.com/USER/REPO/main/SKILL.md -o ~/.claude/skills/common-sense/SKILL.md
```

### Codex
```bash
mkdir -p ~/.codex/skills/common-sense
cp SKILL.md ~/.codex/skills/common-sense/SKILL.md
```

### OpenClaw
```bash
mkdir -p ~/.openclaw/skills/common-sense
cp SKILL.md ~/.openclaw/skills/common-sense/SKILL.md
```

## Trigger

The skill auto-loads when the user says:

- `/common-sense`
- "common sense"
- "does this make sense"
- "is this practical"
- "real world"
- "would a normal person"
- "is this sensible"

Or it auto-applies silently before any production change.

## License

MIT — see [LICENSE](LICENSE)

## Credit

Battle-tested in production AI agent operations. Open-sourced so other stacks can borrow the discipline.
