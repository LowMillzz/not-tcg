# Which app architecture meets the settled capture, evidence, and latency contracts?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: open
Assignee: unassigned
Blocked by: 02, 05, 06, 07, 08, 09, 10, 12, 15

## Question

Given the resolved behaviors and research, which implementation stack and module boundaries make the macOS MVP buildable, testable, and maintainable by an open-source project?

Choose native SwiftUI/AppKit versus a justified alternative, the supported macOS/hardware baseline, capture lifetime, scan ownership, local OCR/catalog matching versus AI work, pricing adapters, caching and expiry, asynchronous enrichment, source/model cancellation, local storage, credential handling, and bounded concurrency. Ground each choice in the agreed latency/privacy/data contracts rather than selecting tools first.

Specify authoritative catalog identity, source-specific ID mappings, versioning, request and result ownership, stale-response rejection, offline and degraded behavior, dependency licensing, and seams for later games/providers. Establish meaningful test layers and Mac integration validation without requiring a backend that scope or data rights do not support. Record ADRs only for consequential trade-offs. No implementation in this ticket.
