# agent-skills

[![skills.sh](https://skills.sh/b/alexgenovese/agent-skills)](https://skills.sh/alexgenovese/agent-skills)

Raccolta di agenti AI con skill organizzate per ambiti di competenza, compatibili con lo standard **Agent Skills** (Claude Code, Cursor, GitHub Copilot, Codex CLI, Amp, Goose e altri).

## Progressive disclosure (context minimo)

Principio base di Agent Skills: all'avvio l'agente carica **solo `name` + `description`** di ogni skill. Il contenuto completo (`SKILL.md` + references) viene iniettato **solo quando la skill viene invocata** — nessuno spreco di contesto. [gotranscript](https://gotranscript.com/public/agent-skills-practical-way-to-cut-llm-context-bloat)

| Livello | Meccanismo | Quando usarlo |
|---------|------------|---------------|
| **1. Progressive disclosure** | L'agente vede solo `name`/`description` di tutte le skills. Legge il `SKILL.md` completo solo se decide di usarla. | Sempre attivo; mantiene il contesto minimo. |
| **2. Invocazione esplicita** | `Usa la skill "nome-skill" per…` o `/nome-skill "query"` | Forzi l'uso, eviti ambiguità. |
| **3. Sub-agent isolato** | `context: fork` → esecuzione in sub-agent con contesto separato | Task lunghi/rischiosi, eviti context rot. |
| **4. `allowed-tools` ristretto** | Limit i tool visibili alla skill attiva | Sandboxing, sicurezza, focus. |
| **5. Orchestratore esterno** | Policy engine che inietta la skill giusta al momento giusto basandosi su eventi | Team/workflow complessi, skill amnesia. |

## Standard cross-tool (Agent Skills)

Dal 2025-2026 i principali strumenti AI adottano lo stesso formato:

| Componente | Formato |
|------------|---------|
| **Skill** | Cartella con `SKILL.md` | Markdown + YAML frontmatter (`name`, `description`) |
| **Script** | `.py`, `.js`, `.sh` | Nella sottocartella `scripts/` |
| **Riferimenti** | `.md`, `.txt`, `.pdf` | Nella sottocartella `references/` |
| **Indice progetto** | `AGENTS.md` | Universale (Claude, Copilot, Cursor, Codex, Windsurf, Amp, Devin) |

## Agenti

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
      scripts/                  ← script eseguibili (.py, .js, .sh)
      references/               ← documentazione di supporto (.md, .txt, .pdf)
```

**Gerarchia**: `agent > skills > scripts, references`

## Checklist context bloat

- [ ] Ogni skill < 500 righe; dettagli in `references/`
- [ ] `AGENTS.md` elenca solo skills del progetto corrente
- [ ] `context: fork` per task > 10 step o con tool distruttivi
- [ ] `allowed-tools` minimalista per ogni skill
- [ ] Sessioni lunghe: reset contesto (`/clear` o nuovo terminale) tra task diversi

## Install

```bash
# Installa agente e skill
npx skills add alexgenovese/agent-skills

# Usa una skill specifica
npx skills use alexgenovese/agent-skills@nextjs-core | opencode
```

## License

MIT
