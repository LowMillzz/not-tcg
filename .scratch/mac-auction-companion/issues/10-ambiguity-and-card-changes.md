# How should uncertain identity and rapid card changes behave?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: prototype
Labels: wayfinder:prototype
Mode: HITL
Status: claimed
Assignee: t3 (prototype with user)
Blocked by: 04, 08

## Question

What recognition and correction behavior avoids confidently pricing the wrong printing, grade, or scan when the video is ambiguous or the user scans again immediately?

Prototype representative candidate identities, visible evidence for a match, unresolved finish/edition/grade, raw condition unknown, multiple cards, and a new scan overtaking an old one. Decide when to show alternatives, request another image, reuse a previous confirmed identity, or abstain. Explain whether calibrated confidence is available; do not display a model's self-reported percentage as measured correctness.

Use a cheap state model or interaction sketch with synthetic examples and user feedback. Establish scan identity, cancellation/late-response rules, duplicate-scan behavior, and limits on carrying a correction forward. Since hotkey scanning does not automatically detect every lot transition, decide how any retained result is labeled until another scan. Preserve the prototype as an asset, not production code.

## Comments

- 2026-10-31: [Exact raw and graded coverage](04-card-identity-and-grading-scope.md) is resolved. Prototype identity candidates or a rescan within its printing/grade gate; showing prices for unresolved alternatives is not the chosen behavior. Use its unknown-raw-condition, plain-numeric-PSA, catalog-gap, and visible-label-only boundaries when constructing ambiguous and unsupported examples; do not reopen settled scope.

- 2026-10-31: Claimed as the next available ticket after AI compatibility resolved. Build a throwaway state demo, not production UI: latest scan ownership, ambiguous identity without prices, canceled/late responses, and explicit last-scan labeling. Use synthetic fixtures, no screenshots, no provider calls, no persistence, and no valuation claims. Keep the prototype on a separate local prototype branch; record the user's verdict before resolving this ticket.

- 2026-10-31: Prototype ready for review on local branch `prototype/scan-identity-states` at commit `7aad479`; the single-file demo is `.scratch/mac-auction-companion/prototypes/10-scan-identity-states.html`. It drives scan ownership, supersession and late-response rejection, ambiguous printing with withheld price, unreadable-grade rescan, unsupported labels, multi-card abstention, no-price success, last-scan retention, and explicit adjacent-scan reuse. The page has ten guided walkthroughs plus free play; all fixtures are synthetic. Awaiting the user's verdict on: (1) tap-to-confirm for plausible printings versus always rescanning, (2) whether the retained result needs an age-based stale warning beyond the scan timestamp, (3) whether adjacent-scan reuse belongs in the MVP or failures should only offer retry, and (4) whether a new scan should clear the previous price immediately as modeled. Do not resolve until those are answered.
