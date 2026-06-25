# OpenCode Agent Config

This repository is a collection of agent skills for OpenCode and other coding agents. Skills are stored under `skills/<name>/SKILL.md` with YAML frontmatter.

## Writing Skills

- Each skill is a directory under `skills/` containing a `SKILL.md` with `name` and `description` in YAML frontmatter
- Keep SKILL.md under 500 lines; use `references/` for deeper docs
- Use imperative tone, explain the "why" behind instructions

## Naming Convention

Skill directory names and `name` frontmatter fields use lowercase with hyphens (kebab-case).

## Validation

Before committing, ensure:
- `name` and `description` are present in frontmatter
- Description explains both *what* and *when* the skill should activate
