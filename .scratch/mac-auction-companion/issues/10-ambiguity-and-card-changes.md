# How should uncertain identity and rapid card changes behave?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: prototype
Labels: wayfinder:prototype
Mode: HITL
Status: open
Assignee: unassigned
Blocked by: 04, 08

## Question

What recognition and correction behavior avoids confidently pricing the wrong printing, grade, or scan when the video is ambiguous or the user scans again immediately?

Prototype representative candidate identities, visible evidence for a match, unresolved finish/edition/grade, raw condition unknown, multiple cards, and a new scan overtaking an old one. Decide when to show alternatives, request another image, reuse a previous confirmed identity, or abstain. Explain whether calibrated confidence is available; do not display a model's self-reported percentage as measured correctness.

Use a cheap state model or interaction sketch with synthetic examples and user feedback. Establish scan identity, cancellation/late-response rules, duplicate-scan behavior, and limits on carrying a correction forward. Since hotkey scanning does not automatically detect every lot transition, decide how any retained result is labeled until another scan. Preserve the prototype as an asset, not production code.

## Comments

- 2026-10-31: In [exact raw and graded coverage](04-card-identity-and-grading-scope.md), the user accepted withholding a matched price until exact printing and relevant slab grade are resolved. Prototype identity candidates or a rescan within that boundary; showing prices for unresolved alternatives is not the chosen behavior. Raw condition stays unknown unless supplied by the collector, and PSA is the first supported grader. Remaining label/printing coverage details are still being discussed in that ticket.
