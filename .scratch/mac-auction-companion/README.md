# Local decision tracker

The canonical issue is [Find the route to a build-ready macOS auction companion](map.md). Its destination and user-confirmed boundaries take precedence over proposals in child issues.

This is the local-Markdown fallback from the wayfinder setup skill. Run `/setup-matt-pocock-skills` to configure a different tracker later; no remote service is currently configured.

## Issue relationships

- Each file in `issues/` is a child issue; its `Parent:` points to the map. Its numeric file prefix is its local identity.
- `Type:` is research, prototype, grilling, or task. `Labels:` carries only the corresponding `wayfinder:` label.
- `Status: open` with `Assignee: unassigned` is unclaimed. Claim before work by setting `Status: claimed` and the driving developer/agent in `Assignee:`.
- `Blocked by: none` means no prerequisites. Otherwise the listed numeric identities must all be `Status: resolved` before work starts. Dependencies are wired only after files exist.
- The frontier is every open, unassigned ticket whose blockers are resolved, ordered by numeric identity. Claimed research is in progress, not an available human ticket.
- Questions belong under `## Question`. Append discussion under `## Comments`; record resolution under `## Answer`, set `Status: resolved`, and append one named link and gist to the map. A research report is an asset, linked from its answer rather than duplicated into it.
- Consult related issue bodies only as needed. Refer to issues by linked title in human-facing text, rather than bare numeric identities.

## Research handoff

Research starts in orchestrator-prepared isolated checkouts. Each child investigates only its assigned question, writes one cited report, and commits it without changing the branch or preparing another checkout. The parent records the returned report/commit pointer, preserves a `research/<topic>` branch, resolves the canonical local ticket, and updates the map. Never merge the throwaway branch.

There is no Git remote, so pushing research is pending rather than silently claimed complete. Research can still establish facts locally. Workers do not modify sibling issues or the map from their isolated copy.

The optional HTML view is a charting-time snapshot. Live status always comes from the Markdown issue files; regenerate the view after resolutions rather than treating it as a second tracker.
