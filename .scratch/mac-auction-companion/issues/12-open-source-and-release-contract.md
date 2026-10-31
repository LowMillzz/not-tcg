# What licensing and release contract makes this a usable open-source Mac project?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: open
Assignee: unassigned
Blocked by: 01, 02, 06, 08, 14, 16

## Question

Which source-code license, data and image boundaries, and Mac distribution commitments let others use and contribute to this MVP without depending on private project credentials or unlicensed bundled data?

Agree the OSS license with the user; separate code licensing from card artwork, provider terms, source attribution, cached data rights, benchmark assets, and trademarks. Confirm the free-data enrollment path and whether users can actually reproduce the app's setup. Do not assume an API's terms grant rights to redistribute its catalog or example images.

Select a distribution plan (for example, direct signed/notarized downloads versus an App Store release), who must supply signing ownership later, Intel/Apple Silicon policy informed by capture research, update and credential migration responsibilities, and the minimum contributor/CI documentation. Surface unavoidable release costs separately from the user's exclusion of paid price data. Choose repository hosting and preserve pending research pushes when a remote is configured; do not create an external repository from this ticket without authorization.

## Comments

- 2026-10-31: [Free-data evidence](../../../docs/research/free-card-and-price-data.md) includes non-revenue-use restrictions and unresolved upstream/artwork rights; the open-source license does not replace those permissions. [Mac evidence](../../../docs/research/macos-capture-and-release.md) separates direct notarized distribution from App Store obligations and release costs. Hardware and viewing-environment commitments now belong to [launch environment selection](14-launch-mac-and-viewing-environments.md); carry its result here without deciding it again.

- The resolved [price-evidence contract](06-price-evidence-contract.md) accepts direct source estimates rather than custom valuation algorithms. Use [free-source validation](16-validate-free-valuation-source.md) to choose a source with demonstrated raw/PSA records, access, usable quotas, expiry rules, and permitted display/cache behavior. Accepting aggregates does not approve a particular provider or its rights. This ticket owns final source acceptance; do not resolve it while that gate is unestablished.
