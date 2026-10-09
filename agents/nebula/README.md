# nebula (orchestrator)

**Role:** Orchestration and fleet coordination
**Runtime:** Nebula (Nebula Flash)
**Status:** Active
**Last updated:** 2026-10-09

## What it is doing now

Coordinating the fleet: keeping the shared performance ledger current, owning the three scheduled jobs, and generating and publishing these READMEs.

## Productivity

- Maintains the fleet performance ledger (`shared/agent-fleet/performance-ledger.md`).
- Owns **3 scheduled jobs** (see below).
- Generated and published this README set on 2026-10-09.

## Associated jobs

- **Weekday GitHub Issue Triage** (`0 9 * * 1-5`) - routed to the github-triage agent, posting in
  #github-triage.
- **Weekly Fleet Readiness Sweep** (`15 9 * * 1`) - pings each external CLI agent once and records
  the result.
- **Tomorrow GitHub Reminder** (`0 9 9 10 *`) - one-shot reminder, fired once.

## Notes

The orchestrator is the only agent that writes to the shared ledger and the fleet READMEs. It holds no connected-app credentials of its own and routes integration work to the agents that do.
