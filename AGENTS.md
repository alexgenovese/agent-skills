# OpenCode Agent Config

Questo repository contiene agenti con skill organizzate per ambiti di competenza, seguendo lo standard [Agent Skills](https://agentskills.io) compatibile con Claude Code, Cursor, GitHub Copilot, Codex CLI, Amp, Goose e altri.

## Struttura

```
agent/                     ← agente (directory principale)
  SKILL.md                 ← metadati agente + system prompt
  skills/
    <area>/<skill-name>/   ← skill organizzate per area
      SKILL.md             ← metadati skill + istruzioni
      scripts/             ← script eseguibili (.py, .js, .sh)
      references/          ← documentazione caricabile su richiesta (.md, .txt, .pdf)
```

## Scrivere Skill

- Ogni skill vive sotto `skills/<area>/<nome>/SKILL.md`
- Frontmatter richiede: `name`, `description`
- SKILL.md sotto 500 righe; usa `references/` per documentazione più lunga
- Tono imperativo, spiega il *perché* oltre al *cosa*
- `scripts/` contiene script per task ripetitivi/deterministici
- `references/` contiene documentazione di supporto

## Naming

- Nome directory skill: kebab-case
- Campo `name` in frontmatter: corrisponde al nome directory
- Nome area: una parola in italiano (es. `prodotto`, `foundation`)

## Validazione

Prima del commit:
- `name` e `description` presenti in ogni SKILL.md
- Ogni SKILL.md ha `scripts/` e `references/` (anche vuote)
