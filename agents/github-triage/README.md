# github-triage

**Role:** GitHub issue triage
**Runtime:** Nebula agent with the GitHub toolkit
**Status:** Active
**Last updated:** 2026-10-09

## What it is doing now

Idle between scheduled runs. Next sweep: the next weekday at 09:00 (America/Chicago), posting into the #github-triage channel.

## Productivity

- **2 scheduled triage runs logged** (2026-10-08 and 2026-10-09), both **success** as job
  executions but reporting **0 issues reviewed and 0 priority flags**.
- Both runs were **blocked at the connection layer**: the workspace had no usable GitHub App
  installation at the time, so no repositories or issues were reachable.
- Average run duration: **~1 minute** (30s and 136s across the two runs).
- A later access check confirmed the GitHub App now resolves for the workspace, so the next run
  should be the first able to actually list and triage issues.

## Associated jobs

Executes **Weekday GitHub Issue Triage** (`0 9 * * 1-5`), which posts into #github-triage. The job
has run twice to date.

## Notes

The agent, its channel, and its weekday job all exist and are healthy. Its productivity is limited
only by repository reachability, not by the agent itself. Once repositories are reachable, each run
will sweep open issues, rank them, flag priority items, and append a row to the fleet ledger.
