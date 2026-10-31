# How should repeated hotkey scans and price evidence fit around manual bidding?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: prototype
Labels: wayfinder:prototype
Mode: HITL
Status: open
Assignee: unassigned
Blocked by: 02, 06, 07, 09, 10

## Question

What selected-region capture and result-panel behavior lets a collector scan again, read credible evidence, and keep control of the auction within a short bid window?

Prototype the setup-once/hotkey loop, region updates after window movement, a non-focusing panel, keyboard correction, pinned versus transient results, and clear capture/upload progress. Show identity before pricing when needed, source type and age, insufficient evidence, unsupported card, rate limiting, provider failure, and timeout states. Distinguish retaining an earlier result for history from presenting it as the new card's value.

Use the settled price contract and latency target. Include a cold scan, a repeat scan, an immediate second card, and a late first-card response. Have the user react to a cheap prototype; no production UI implementation is implied. Link the artifact from the ticket.
