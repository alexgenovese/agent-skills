# agent-skills

[![skills.sh](https://skills.sh/b/alexgenovese/agent-skills)](https://skills.sh/alexgenovese/agent-skills)

Raccolta di agenti AI con skill organizzate per ambiti di competenza, compatibili con [Agent Skills](https://agentskills.io).

## Agenti

### [software-engineer](software-engineer/)

Senior full-stack software engineer — abilità di prodotto, pianificazione e implementazione Next.js/TypeScript.

**Skill:** `nextjs-core`, `task-breakdown`, `architecture-design`, `time-estimation`, `code-review`, `testing-patterns`, `refactoring`

### [nextjs-expert-cto](nextjs-expert-cto/)

CTO tecnico specializzato Next.js — strategia tecnica, delivery e qualità del codice.

**Skill:** `technical-decision-making`, `team-velocity`, `deployment-strategy`, `quality-gates`, `typescript-ecosystem`, `api-design`

## Struttura

```
agent/                          ← agente (directory principale)
  SKILL.md                      ← definizione + sistema
  skills/
    <area>/<skill-name>/        ← skill organizzata per area semantica
      SKILL.md                  ← metadati + istruzioni
      resources/                ← documentazione caricabile su richiesta
      assets/                   ← template, icone, font
      functions/                ← script eseguibili deterministici
```

**Gerarchia**: `agent > skills > resources, assets, functions`

## Install

```bash
# Installa agente e skill
npx skills add alexgenovese/agent-skills

# Usa una skill specifica
npx skills use alexgenovese/agent-skills@nextjs-core | opencode
```

## License

MIT
