# Agenticnebula J.A.R.V.I.S.

Documentation for the Nebula agent fleet in Pran's workspace.

_Last generated: 2026-10-09 (America/Chicago). Status and productivity figures are a point-in-time snapshot of the workspace fleet ledger._

## Fleet at a glance

| Agent | Role | Runtime | Status |
|---|---|---|---|
| github-triage | GitHub issue triage | Nebula agent (GitHub toolkit) | active |
| claude-code | Coding | Claude Code CLI | idle |
| codex | Coding | Codex CLI | idle |
| gemini-cli | Coding | Gemini CLI | idle |
| opencode | Coding | opencode CLI | idle |
| antigravity-cli | Coding | Antigravity CLI (agy) | idle |
| nebula | Orchestration / fleet coordination | Nebula | active |

## Agent READMEs

- [Fleet overview](agents/README.md) - roster, productivity summary, shared ledger
- [github-triage](agents/github-triage/README.md) - GitHub issue triage
- [claude-code](agents/claude-code/README.md)
- [codex](agents/codex/README.md)
- [gemini-cli](agents/gemini-cli/README.md)
- [opencode](agents/opencode/README.md)
- [antigravity-cli](agents/antigravity-cli/README.md)
- [nebula (orchestrator)](agents/nebula/README.md)

## Scheduled jobs

| Job | Schedule | Route | Runs to date |
|---|---|---|---|
| Weekday GitHub Issue Triage | 09:00, Mon-Fri | #github-triage / github-triage agent | 2 |
| Weekly Fleet Readiness Sweep | 09:15, Mondays | Fleet orchestrator | 0 (first run 2026-10-12) |
| Tomorrow GitHub Reminder | 09:00, Oct 10 (one-shot) | Home channel | 1 |

## How this stays current

The fleet's shared performance ledger lives at `shared/agent-fleet/performance-ledger.md` in the
workspace sandbox. The weekday triage job appends one row per run and the weekly readiness sweep
appends one row per agent; these READMEs are regenerated from that ledger.
