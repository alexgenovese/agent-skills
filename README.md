# Agent Skills

[![skills.sh](https://skills.sh/b/alexgenovese/agent-skills)](https://skills.sh/alexgenovese/agent-skills)

A curated collection of agent skills for OpenCode, Claude Code, Cursor, Codex, and any agent that supports the [Agent Skills](https://agentskills.io) format.

## Install

```bash
# Install all skills
npx skills add alexgenovese/agent-skills

# Install a specific skill
npx skills add alexgenovese/agent-skills --skill skill-name

# Use a skill without installing
npx skills use alexgenovese/agent-skills@skill-name | opencode
```

## Skills

| Skill | Description |
|-------|-------------|
| [example-skill](skills/example-skill/) | Reference implementation showing the Agent Skills format and conventions |
| <!-- add your skills here --> | |

## Creating a Skill

Skills are directories with a `SKILL.md` file and YAML frontmatter:

```markdown
---
name: my-skill
description: What this skill does and when to use it
---

# My Skill

Instructions for the agent...
```

Use the [template](template/SKILL.md) as a starting point.

```
skills/<skill-name>/
├── SKILL.md        # Required: name, description, instructions
├── references/     # Optional: deep docs loaded on demand
├── scripts/        # Optional: executable helpers
└── assets/         # Optional: templates, icons, fonts
```

## Compatibility

These skills follow the [Agent Skills specification](https://agentskills.io) and work with any compatible agent. See [skills.sh](https://skills.sh) for the ecosystem.

## License

MIT
