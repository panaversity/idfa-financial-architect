# IDFA Financial Architect

A Claude Code plugin that applies **Intent-Driven Financial Architecture (IDFA)** to every financial modelling interaction — automatically.

IDFA is a methodology for building financial models that are human-readable, AI-operable, and mathematically audit-proof. Developed by the [Panaversity](https://panaversity.org) team.

## Installation

### Claude Code

Add the marketplace and install the plugin:

```
/plugin marketplace add panaversity/idfa-financial-architect
/plugin install idfa-financial-architect@panaversity-idfa
```

The skill auto-activates whenever a conversation mentions financial models, named ranges, spreadsheet formulas, or model audits.

### Cowork (Claude.ai)

1. Open the **Cowork** tab in Claude
2. Click **Customize** in the left sidebar
3. Click **Browse plugins** or upload this plugin directly
4. The IDFA skill will be available in all Cowork sessions

### Local Testing

Clone the repo and load it directly:

```bash
git clone https://github.com/panaversity/idfa-financial-architect.git
claude --plugin-dir ./idfa-financial-architect
```

### Other Agents (GitHub Copilot, VS Code, Codex, Cursor)

Download `skills/financial-architect/SKILL.md` from this repo and place it in your agent's custom instructions path:

| Agent          | Path                                         |
| -------------- | -------------------------------------------- |
| GitHub Copilot | `.github/copilot-instructions.md`            |
| VS Code        | `.vscode/copilot-instructions.md`            |
| Codex (OpenAI) | Project instructions or system prompt        |
| Cursor         | `.cursorrules` or project-level instructions |

The SKILL.md content is identical across all platforms — only the file path changes.

## What It Does

When the plugin is active, the agent automatically applies four deterministic guardrails to every financial model interaction:

1. **Named Range Priority** — every formula uses Named Ranges, zero coordinate references
2. **LaTeX Verification** — complex formulas (WACC, NPV, DCF, IRR) are verified in LaTeX before writing
3. **Audit-Ready Intent Notes** — every AI-generated formula includes an Intent Note documenting its purpose
4. **MCP Dependency** — the agent writes inputs and reads results via the Excel MCP Server, never calculating internally

## The Three Layers

Every IDFA-compliant model separates:

- **Layer 1 — Assumptions**: inputs only, all prefixed with `Inp_`
- **Layer 2 — Calculations**: Named Ranges only, readable as business rules
- **Layer 3 — Output**: presentation and formatting only

## Plugin Structure

```
idfa-financial-architect/
├── .claude-plugin/
│   ├── plugin.json            ← Plugin metadata
│   └── marketplace.json       ← Marketplace catalog (for /plugin marketplace add)
├── skills/
│   └── financial-architect/
│       ├── SKILL.md           ← Complete IDFA methodology
│       └── references/
│           └── IDFA-reference.md  ← Enterprise governance, complex formulas
├── README.md
└── LICENSE
```

## Learn More

This plugin is taught in **Chapter 18: Intent-Driven Financial Architecture** of [The AI Agent Factory](https://panaversity.org) book, which covers the full methodology from the Coordinate Trap through enterprise governance.

## License

Apache-2.0 — see [LICENSE](./LICENSE).

## Attribution

The Intent-Driven Financial Architecture (IDFA) is original research developed by the **Panaversity team** (https://panaversity.org). Published under the [agentskills.io](https://agentskills.io) open standard.
