# OpenCode Agent Config

Questo repository contiene un agente software engineer con skill organizzate per ambiti di competenza.

## Struttura

```
software-engineer/           ← agente (directory principale)
  SKILL.md                   ← metadati agente + system prompt
  skills/
    <area>/<skill-name>/     ← skill organizzate per area
      SKILL.md               ← metadati skill + istruzioni
      resources/             ← documentazione caricabile su richiesta
      assets/                ← template, icone, font
      functions/             ← script eseguibili (deterministici)
```

## Scrivere Skill

- Ogni skill vive sotto `skills/<area>/<nome>/SKILL.md`
- Frontmatter richiede: `name`, `description`
- SKILL.md sotto 500 righe; usa `resources/` per documentazione più lunga
- Tono imperativo, spiega il *perché* oltre al *cosa*
- `functions/` contiene script per task ripetitivi/deterministici
- `assets/` contiene file usati nell'output (template, icone, font)

## Naming

- Nome directory skill: kebab-case
- Campo `name` in frontmatter: corrisponde al nome directory
- Nome area: una parola in italiano (es. `prodotto`, `foundation`)

## Validazione

Prima del commit:
- `name` e `description` presenti in ogni SKILL.md
- Ogni SKILL.md ha `resources/`, `assets/`, `functions/` (anche vuote)
