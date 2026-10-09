# Agent Fleet - Overview

Owner: Pran H. Last updated: 2026-10-09.

The workspace runs six agents plus the orchestrator. Five are external CLI coding agents that sit
idle until given work; one is the GitHub triage agent; and `nebula` coordinates the fleet itself.

## Roster and status

| Agent | Role | Runtime | Status | Runs / work to date |
|---|---|---|---|---|
| github-triage | GitHub issue triage | Nebula agent (GitHub toolkit) | active | 2 triage runs logged (both blocked) |
| claude-code | Coding | Claude Code CLI | idle | None yet (first sweep 2026-10-12) |
| codex | Coding | Codex CLI | idle | None yet (first sweep 2026-10-12) |
| gemini-cli | Coding | Gemini CLI | idle | None yet (first sweep 2026-10-12) |
| opencode | Coding | opencode CLI | idle | None yet (first sweep 2026-10-12) |
| antigravity-cli | Coding | Antigravity CLI (agy) | idle | None yet (first sweep 2026-10-12) |
| nebula | Orchestration / fleet coordination | Nebula | active | Maintains ledger + 3 jobs |

## Productivity summary

- **github-triage** has completed 2 scheduled runs, both reporting 0 issues reviewed and 0 priority
  flags because GitHub was not reachable from the workspace at the time. It has produced no triage
  output yet.
- **The five coding agents** have not been exercised yet - the readiness sweep that tests each one
  runs for the first time on 2026-10-12. Their productivity record is currently empty rather than
  zero-scoring.
- **nebula** keeps the fleet ledger current and owns the three scheduled jobs below.

## Scheduled jobs

- **Weekday GitHub Issue Triage** - `0 9 * * 1-5` - runs in #github-triage, executed by the
  github-triage agent.
- **Weekly Fleet Readiness Sweep** - `15 9 * * 1` - pings every external CLI agent once, records
  whether it responded and how long it took, then appends a row per agent to the ledger.
- **Tomorrow GitHub Reminder** - `0 9 9 10 *` - one-shot reminder, already fired once.

## Shared ledger

All figures above come from the shared performance ledger (`shared/agent-fleet/performance-ledger.md`).
The ledger is the single source of truth; these READMEs are its human-readable mirror.
