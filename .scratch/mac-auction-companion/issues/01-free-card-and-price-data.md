# Which free sources can identify exact printings and provide credible raw and graded prices?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: research
Labels: wayfinder:research
Mode: AFK
Status: resolved
Assignee: t3 (free-data research)
Blocked by: none

## Question

What current, primary-source-supported card catalogs and price-data paths can a newly registered user of a public open-source macOS app use without a paid data subscription, for both raw and graded English Pokémon singles?

Investigate eBay, TCGplayer, PriceCharting, Pokémon TCG API, TCGdex, and credible alternatives as candidates, not promised dependencies. Separate catalog identity and images from price rights, inherited TCGplayer fields from direct TCGplayer access, active asking prices from actual sold transactions, and aggregated valuations from sale records. Verify free-tier onboarding and practical availability; a free API wrapper is not proof that its upstream data is licensed or current.

Establish condition/grade/grader/variant coverage, freshness, timestamps, source links, request limits, caching/distribution rights, attribution, currency and shipping treatment, maintenance signals, and whether source terms permit a distributed client with per-user credentials. Mark undocumented points as unresolved; do not infer permission or build a scraper. Test no paid service and create no accounts.

If actual sold comps or graded pricing cannot be established under these constraints, say so explicitly. Compare the feasible fallback classes (sourced valuation, clearly labeled asking prices, user-opened research links, or recognition-only) without choosing one on the user's behalf. Identify whether insufficient free graded evidence conflicts with launch coverage.

Write one report in `docs/research/free-card-and-price-data.md` with checked dates, direct citations, a candidate-by-candidate verdict, unresolved permission questions, and recommendations for the price-evidence decision. Preserve research separately; no production code.

## Comments

### Research recovery — 2026-10-31

The delegated run failed with a provider usage-limit error after writing the complete report but before committing it. The parent reviewed the recovered report, preserved the sole untracked research file on the already prepared branch, and copied the report into the parent checkout as an asset. No replacement provider or agent was used, and no new research calls or registrations were made during recovery.

## Answer

Evidence gathering is complete; a launch pricing dependency is not selected or approved. The [free catalog and price-evidence report](../../../docs/research/free-card-and-price-data.md), checked 2026-10-31, finds a plausible free catalog candidate in TCGdex, direct raw aggregates in Cardmarket exports with major language/condition limitations, and advertised free raw-plus-graded aggregates from PokemonPriceTracker under non-revenue-use terms. None establishes a dependable, permission-established free feed of individual sold transactions covering the required raw and graded launch scope.

Important distinctions: direct TCGplayer access is closed to new developers; the legacy Pokémon TCG API has a retirement notice; PriceCharting API access is paid; eBay sold-history access is restricted. A wrapper's availability does not establish upstream rights, English/condition specificity, or freshness. PokemonPriceTracker's advertised free graded aggregates are a conditional lead, not proof of individual comps or upstream authorization. JustTCG's distribution guidance introduces paid-access requirements. The report records anonymous observations and source-specific documentation limits; free-key registration and authenticated price coverage were not tested.

Take the remaining choices to [exact raw and graded coverage](04-card-identity-and-grading-scope.md), [the price-evidence contract](06-price-evidence-contract.md), and [the open-source release contract](12-open-source-and-release-contract.md). Preserve both raw and slabs as user requirements. If available evidence cannot meet them, obtain an explicit scope/evidence decision; do not silently substitute raw values for slabs or asking prices for sales.

Research commit: `7dec1be12e785c347cfc90a1185f4fd3064060a6`, preserved as local `research/free-card-and-price-data`. The throwaway branch was not merged. Remote push is pending because there is no Git remote. This resolves the documented investigation only, not source permission, endpoint onboarding, data quality, or any human decision.
