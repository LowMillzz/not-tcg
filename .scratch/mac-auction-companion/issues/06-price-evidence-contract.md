# What price evidence is sufficient for fair-bid guidance without paid data?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: resolved
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

### First interview round — answered

Settle the following independent choices before selecting or validating a source:

- Are clearly attributed aggregate valuations acceptable for the MVP, or must every price be backed by individually inspectable sold transactions? Recommendation: allow named, dated aggregates, labeled as estimates; no calling them individual sold comps and no model-invented prices.
- For an identified card with no usable evidence, show price unavailable plus manual research links, or treat any such case as a launch blocker? Recommendation: explicit per-card unavailability, while retaining meaningful numeric-price coverage for both raw and PSA cards as a separate release criterion. Identification alone does not count as actionable price guidance.
- Which market/currency is the initial comparison context? Recommendation: US market in USD, with source geography and shipping/tax inclusion explicit rather than treating cross-market prices as interchangeable.

The user accepted named, dated aggregate valuations, price-unavailable plus research links, and the US market in USD. They explicitly asked to keep the MVP simple and defer source algorithms. Accepting this evidence class does not approve a particular provider, its permissions, freshness, or raw/PSA coverage.

### Resolution

Use source-reported valuations directly for the MVP. Detailed source-specific valuation algorithms, cross-source blending, outlier handling, inferred ranges and proprietary fair-price calculations are deferred beyond this MVP rather than expanded into more policy interviews here.

## Answer

- **Evidence type:** named, dated source aggregate valuations are acceptable. Label them as source estimates, not individual sold comps. The model identifies the card; it does not invent a price.
- **Calculation:** display an eligible source's reported estimate and any source-provided range without creating a new blended value, confidence percentage or synthesized range. Do not reimplement the source's valuation algorithm for this MVP. A provider's own method is attributable context, not an algorithm the app claims to validate or reproduce.
- **Matching:** apply the resolved printing/grade gate from [card coverage](04-card-identity-and-grading-scope.md). Use the supported PSA grade exactly; do not substitute raw or adjacent-grade values. Raw condition remains unknown unless supplied. Label a raw source estimate's condition basis as reported, or as unspecified if the source does not supply one; a source condition is not an assessment of this particular card.
- **Context:** use US-market USD evidence. Show the source name, source update date/age, relevant condition or PSA grade basis, and a research/source link. Keep source observation time separate from app fetch time. Shipping/tax inclusion is reported as known or unknown; do not silently treat unknown costs as zero or convert another market into equivalent US evidence.
- **Unavailable:** if no usable evidence exists, show the identified card, price unavailable, and manual research links. Do not invent a number or silently downgrade slab pricing to raw pricing. This outcome counts as recognition, not successful price guidance.
- **Release coverage:** useful numeric-price coverage for both supported raw cards and PSA slabs remains a release requirement. Occasional unavailable results are acceptable; a release that is normally recognition-only for slabs would change the agreed product and needs an explicit user decision. Quantitative thresholds belong to [latency and quality](09-latency-and-quality-bar.md).
- **Source gate:** no source is selected by this resolution. The now-specific [free-source validation task](16-validate-free-valuation-source.md) must establish access, permitted distributed use, actual records, dates, condition/grade mapping and quota/refresh facts before the source can be committed to in the [open-source release contract](12-open-source-and-release-contract.md). Simple source freshness/expiry rules remain part of that validation/selection and the architecture; they must not be replaced with a fetched-now timestamp or a custom valuation algorithm. Until that gate passes, availability is unproved.

This closes the product's price-evidence contract and simplifies its calculation scope; it does not close the free-data feasibility gate or approve source rights, coverage, sustained usage, freshness, or five-second performance.
