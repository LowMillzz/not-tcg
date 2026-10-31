# What price evidence is sufficient for fair-bid guidance without paid data?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: claimed
Assignee: t3 (live decision with user)
Blocked by: 01, 04

## Question

Which feasible free source or combination should the MVP use, and what must it know before showing a collector an actionable fair-price range for each supported raw or graded card?

Decide whether actual sold transactions are required or whether labeled catalog valuations or asking prices provide acceptable initial utility. If sold evidence or graded evidence is unavailable, choose the fallback with the user; recognition and a search link must not be presented as equivalent to sold comps. Resolve any conflict between the no-paid-data rule and raw-plus-graded launch coverage before architecture is locked.

Agree exact-printing/grade/condition matching, missing condition, source attribution and deep links, timestamps and cache freshness, sample size and sale recency, outliers, accepted offers, bundles, currency, geography, shipping, fees, and tax assumptions. Keep scope to collector guidance with manual bidding, not reseller margins or an automated bid ceiling. Define when evidence is insufficient, stale, or incomparable and the app must withhold a number.

Do not let a model invent market prices or convert its confidence into pricing evidence. Establish separate identity confidence, match quality, and evidence sufficiency concepts.

## Comments

- 2026-10-31: [Free-data research](01-free-card-and-price-data.md) is resolved with [candidate-specific evidence](../../../docs/research/free-card-and-price-data.md). Consider named aggregates separately from individual sold records. PokemonPriceTracker is a conditional non-revenue raw/graded aggregate lead, not a selected source; JustTCG's free distribution guidance is restrictive. Neither open-source code nor per-user keys resolve upstream rights, printing/grade coverage, freshness, or permission. Resolve the acceptable evidence class and missing-price behavior with the user.

- 2026-10-31: Claimed after [exact raw and graded coverage](04-card-identity-and-grading-scope.md) resolved. Its PSA-numeric, exact-printing, unknown-raw-condition, and ambiguity boundaries are inputs here, not questions to reopen.

### First interview round — awaiting answers

Settle the following independent choices before selecting or validating a source:

- Are clearly attributed aggregate valuations acceptable for the MVP, or must every price be backed by individually inspectable sold transactions? Recommendation: allow named, dated aggregates, labeled as estimates; no calling them individual sold comps and no model-invented prices.
- For an identified card with no usable evidence, show price unavailable plus manual research links, or treat any such case as a launch blocker? Recommendation: explicit per-card unavailability, while retaining meaningful numeric-price coverage for both raw and PSA cards as a separate release criterion. Identification alone does not count as actionable price guidance.
- Which market/currency is the initial comparison context? Recommendation: US market in USD, with source geography and shipping/tax inclusion explicit rather than treating cross-market prices as interchangeable.

These are recommendations awaiting the user's answers. Accepting an evidence class does not approve a particular provider, its permissions, freshness, or grade/printing coverage. Raw unknown-condition presentation, source choice, acceptable staleness/sample sufficiency, and other dependent rules require later rounds within this ticket.
