# tipi — Repo Guidelines

Read and follow [AGENTS.md](AGENTS.md).

## Prime directive

`tipi` is a **view**, never a **source**. Never introduce a new write path. All writes to body/mind/spirit go through the runtime CLIs (`hermes`, `openclaw`, `claude`, `dizzy.py`) or through the consciousness layer owners (OBn, Khoj, future OB1 belief-ledger).

## Source of truth for three-layer consciousness

The ADR lives in the vault at `~/Documents/=notes/docs/architecture/three-layer-consciousness.md`. Do not duplicate its content here. Cite it.

## Python setup

- Python 3.11+ required
- `python3 -m venv .venv && .venv/bin/pip install -e '.[dev]'`
- Tests: `.venv/bin/pytest tests/ -v`

## Commit hygiene

- Explicit-path `git add` (never `git add -A` or `git add .`)
- Conventional-ish commits: `feat(mcp/consciousness): ...`, `test(mcp/dizzy): ...`
- Never force-push to main without explicit user consent

## Coordination

- Coordination with parallel work (infra-context-dashboard) is in `~/Documents/Coordination/2026-04-21-infra-context-dashboard-coordination.md` — un-gitted scratchpad per vault conventions §15.
- Vault plan that governs this repo: `~/Documents/=notes/docs/plans/2026-04-21-tipi-vs-tipi.md`

<!-- gitnexus:start -->
# GitNexus — Code Intelligence

This project is indexed by GitNexus as **tipi** (481 symbols, 877 relationships, 24 execution flows). Use the GitNexus MCP tools to understand code, assess impact, and navigate safely.

> If any GitNexus tool warns the index is stale, run `npx gitnexus analyze` in terminal first.

## Always Do

- **MUST run impact analysis before editing any symbol.** Before modifying a function, class, or method, run `gitnexus_impact({target: "symbolName", direction: "upstream"})` and report the blast radius (direct callers, affected processes, risk level) to the user.
- **MUST run `gitnexus_detect_changes()` before committing** to verify your changes only affect expected symbols and execution flows.
- **MUST warn the user** if impact analysis returns HIGH or CRITICAL risk before proceeding with edits.
- When exploring unfamiliar code, use `gitnexus_query({query: "concept"})` to find execution flows instead of grepping. It returns process-grouped results ranked by relevance.
- When you need full context on a specific symbol — callers, callees, which execution flows it participates in — use `gitnexus_context({name: "symbolName"})`.

## Never Do

- NEVER edit a function, class, or method without first running `gitnexus_impact` on it.
- NEVER ignore HIGH or CRITICAL risk warnings from impact analysis.
- NEVER rename symbols with find-and-replace — use `gitnexus_rename` which understands the call graph.
- NEVER commit changes without running `gitnexus_detect_changes()` to check affected scope.

## Resources

| Resource | Use for |
|----------|---------|
| `gitnexus://repo/tipi/context` | Codebase overview, check index freshness |
| `gitnexus://repo/tipi/clusters` | All functional areas |
| `gitnexus://repo/tipi/processes` | All execution flows |
| `gitnexus://repo/tipi/process/{name}` | Step-by-step execution trace |

## CLI

| Task | Read this skill file |
|------|---------------------|
| Understand architecture / "How does X work?" | `.claude/skills/gitnexus/gitnexus-exploring/SKILL.md` |
| Blast radius / "What breaks if I change X?" | `.claude/skills/gitnexus/gitnexus-impact-analysis/SKILL.md` |
| Trace bugs / "Why is X failing?" | `.claude/skills/gitnexus/gitnexus-debugging/SKILL.md` |
| Rename / extract / split / refactor | `.claude/skills/gitnexus/gitnexus-refactoring/SKILL.md` |
| Tools, resources, schema reference | `.claude/skills/gitnexus/gitnexus-guide/SKILL.md` |
| Index, status, clean, wiki CLI commands | `.claude/skills/gitnexus/gitnexus-cli/SKILL.md` |

<!-- gitnexus:end -->
