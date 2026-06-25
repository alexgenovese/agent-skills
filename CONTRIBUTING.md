# Contributing

Thanks for contributing to the agent-skills collection.

## Adding a Skill

1. Create a directory under `skills/<your-skill-name>/`
2. Write a `SKILL.md` with YAML frontmatter containing `name` and `description`
3. Add optional `references/`, `scripts/`, or `assets/` subdirectories as needed
4. Ensure the `name` field matches the directory name (kebab-case)
5. Keep SKILL.md under 500 lines; use reference files for supplementary material

## Guidelines

- Skills must be self-contained and portable across agents
- Prefer the Agent Skills format defined at [agentskills.io](https://agentskills.io/specification)
- Test your skill with at least one realistic test prompt before submitting
- Do not include malicious code, exploit logic, or anything that could compromise system security

## PR Process

1. Open a PR with your new skill
2. Include a brief description of what the skill does and when it should trigger
3. A maintainer will review for format compliance and clarity
