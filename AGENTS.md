# AGENTS.md

Agent definitions for the DEDZED documentation site live in `.claude/agents/`. These are custom Claude Code agents that can be dispatched individually or as a team to improve and maintain this documentation.

## Available agents

| Agent | File | Purpose |
|---|---|---|
| `docs-writer` | `.claude/agents/docs-writer.md` | Creates new MDX pages following DEDZED conventions and registers them in navigation |
| `docs-reviewer` | `.claude/agents/docs-reviewer.md` | Reviews pages for style, terminology, structure, and content quality |
| `site-architect` | `.claude/agents/site-architect.md` | Manages `docs.json` navigation, detects orphaned/phantom pages, maintains site structure |
| `content-auditor` | `.claude/agents/content-auditor.md` | Performs comprehensive audits across all pages for gaps, staleness, and inconsistencies |
| `terminology-guard` | `.claude/agents/terminology-guard.md` | Scans and fixes terminology violations (DEDZED, Ping Identity, Kasm, etc.) |

## Usage

These agents are auto-discovered by Claude Code from `.claude/agents/`. They can be used as `subagent_type` values when dispatching with the Task tool, or spawned as teammates in a team workflow.

### Single agent dispatch

Spawn one agent for a focused task:

```
Task tool → subagent_type: "docs-reviewer"
prompt: "Review all pages in getting-started/ for style and terminology compliance"
```

### Team workflow

Spawn multiple agents in parallel for a full documentation improvement pass:

1. **content-auditor** — audit the entire site, identify priorities
2. **terminology-guard** — scan and fix all terminology violations
3. **docs-reviewer** — review flagged pages for quality issues
4. **site-architect** — verify navigation structure and fix orphaned pages
5. **docs-writer** — create any new pages identified as gaps

## Adding new agents

Create a new markdown file in `.claude/agents/` with:

- A `# agent-name` heading matching the filename
- A "Your role" section describing the agent's purpose
- A "Workflow" section with numbered steps
- Any rules, checklists, or output format specifications

The filename (minus `.md`) becomes the agent identifier.
