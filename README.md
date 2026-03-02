# IDFA Financial Architect

A Claude Code plugin that applies **Intent-Driven Financial Architecture (IDFA)** to every financial modelling interaction — automatically.

IDFA is a methodology for building financial models that are human-readable, AI-operable, and mathematically audit-proof. Developed by the [Panaversity](https://panaversity.org) team.

## Installation

### Claude Code (plugin)

```bash
claude plugin install panaversity/idfa-financial-architect
```

Or for local testing:

```bash
claude --plugin-dir ./plugins/idfa-financial-architect
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

## Learn More

This plugin is taught in **Chapter 18: Intent-Driven Financial Architecture** of [The AI Agent Factory](https://panaversity.org) book, which covers the full methodology from the Coordinate Trap through enterprise governance.

## License

Apache-2.0 — see [LICENSE](./LICENSE).

## Attribution

The Intent-Driven Financial Architecture (IDFA) is original research developed by the **Panaversity team** (https://panaversity.org). Published under the [agentskills.io](https://agentskills.io) open standard.
