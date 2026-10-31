# Which free source passes the MVP raw-and-PSA valuation checks?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: task
Labels: wayfinder:task
Mode: HITL
Status: open
Assignee: unassigned
Blocked by: 06, 07

## Question

Before committing to a launch source, establish the actual access and records needed to use a free provider's reported US-market USD valuations directly for raw English Pokémon singles and supported numeric PSA slabs. This task supplies facts for the source choice in [the open-source release contract](12-open-source-and-release-contract.md); it does not build a valuation algorithm, select a source on the user's behalf, or implement production integration.

Use the [free-data report](../../../docs/research/free-card-and-price-data.md) to identify a candidate worth validating. PokemonPriceTracker's advertised non-revenue free aggregates are one lead, not an approved dependency. Record the candidate and purpose before any access request. No paid subscription, project-distributed secret, unlicensed mirror or scraper is an acceptable shortcut.

Checklist for the driving session:

1. Establish whether the documented free plan is currently available to a new user, and whether its terms support this distributed macOS use with user-owned credentials. Record revenue restrictions, key handling, cache/display/attribution rules, any required backend, and unresolved upstream provenance. A provider's refusal to provide upstream assurances is a documented limitation, not permission and not an excuse to keep asking the same support question.
2. If a free account/key is needed, give the user the specific enrollment purpose and use the secret-delivery tool for credentials. Make no signup, external contact or key transfer merely because this task exists. Keep credentials on their owning host and out of reports, logs and Git.
3. With authorized no-cost access, inspect representative matching raw and PSA records, including missing prices and printings/grades that should not match. Record identifiers, exact printing/grade fields, original currency/market, reported condition basis, source update timestamp, source link, absent metadata and provider-returned value. Treat interpolated values as provider estimates, not observed sales.
4. Establish quota and refresh behavior for a realistic short auction session, legal cache limits, and the simplest supported expiry rule. Distinguish source age from fetch age. Do not create source-specific pricing statistics or consume paid credits; document limits that prevent useful sustained use.
5. Report passed checks, failed checks and unverified points for source selection. If the candidate cannot meet the no-paid-data/raw-plus-PSA boundaries, preserve that failure and return it as a decision; do not silently switch to raw-only, asking-price-only, or a paid backend.

Link a concise evidence artifact. Resolve when the observations needed for a source decision are established, including a documented negative outcome where appropriate. Final source acceptance and any remaining permission/expiry policy belong to the release contract; measured useful-price coverage belongs to the quality ticket. Until these pass, a free raw-plus-PSA pricing dependency is not established.
