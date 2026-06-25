---
name: example-skill
description: Example skill demonstrating the Agent Skills format. Use as a reference when creating new skills. Shows required frontmatter fields, progressive disclosure, and common patterns.
---

# Example Skill

This skill serves as a reference implementation. It follows the Agent Skills specification defined at [agentskills.io](https://agentskills.io).

## Structure

A skill is a directory containing:

```
skill-name/
├── SKILL.md          # Required: frontmatter + instructions
├── references/        # Optional: deep docs loaded on demand
├── scripts/           # Optional: executable helpers
└── assets/            # Optional: templates, icons, fonts
```

## Progressive Disclosure

Skills use a three-level loading system:
1. **Metadata** (name + description) — Always in context
2. **SKILL.md body** — In context when the skill triggers
3. **References/Scripts/Assets** — Loaded as needed

## Frontmatter

Required fields in the YAML frontmatter:

```yaml
name: skill-name            # Unique identifier (kebab-case)
description: What & when    # Trigger description
```

Optional fields:

```yaml
metadata:
  author: your-name
  version: "1.0.0"
  internal: true            # Hidden from normal discovery
```

## Writing Tips

- Keep SKILL.md under 500 lines. Approaching that? Add another hierarchy layer with clear pointers on where to go next
- Use `references/` for files that exceed ~300 lines; include a table of contents in each reference file
- Explain the *why* behind instructions. Modern LLMs perform better with reasoning, not just rules
- Use imperative tone: "Fetch the latest guidelines", "Read the specified files", not "You should fetch..."

## Example Reference File

If this skill had a reference file, you'd point to it like this:

> For the full API schema, see `references/api-schema.md`. Read it only when handling API-related requests.
