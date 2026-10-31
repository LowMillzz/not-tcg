# Find the route to a build-ready macOS auction companion

Labels: wayfinder:map
Status: open
Owner: t3
Created: 2026-10-31

## Destination

A build-ready MVP specification for an open-source macOS app that uses the user's AI provider to identify English Pokémon singles visible in a Mac auction video and provide sourced fair-price guidance within a roughly five-second bidding opportunity. The map is complete when product scope, data feasibility, latency and correctness criteria, architecture, and release prerequisites are settled enough to create implementation tasks.

## Notes

### Boundaries confirmed by the user

- This effort produces the specification and decisions before implementation.
- English Pokémon single cards first, including raw cards and PSA slabs at launch; remaining grade/printing boundaries are being specified in [exact raw and graded coverage](issues/04-card-identity-and-grading-scope.md).
- The auction video is visible on the Mac. Initial capture uses a global hotkey and a previously selected window or region.
- The first user is a collector judging whether a bid is fair. Bidding stays manual.
- Bring your own AI means user-supplied API keys or compatible endpoints. Inference may have user-paid costs; this is distinct from price-data access.
- No paid price-data subscription or paid data-service dependency in the MVP. Free accounts or API keys are acceptable, provided access is available to new users. Paid price-data integrations may be revisited after the MVP.
- Cropped images may be sent to the configured AI provider. Provide an explicit capture indicator; discard screenshots by default and avoid full-screen uploads by default. Provider-side retention must be described separately from app retention.
- Recognition success and pricing success are separate. Do not silently drop raw or graded coverage to make a source fit; surface any conflict with the launch scope as a human decision.

### Working conventions

- Use the wayfinder, grilling, and domain-modeling skills for decision sessions; use research and prototype for those ticket types. Charting does not resolve human decision tickets.
- This repo uses the local-Markdown tracker. [Tracker conventions](README.md) describe child relationships, claims, blocking, and frontier queries. The map indexes resolved decisions only; open tickets are discovered from the issue files.
- Research is evidence, not approval to implement. Distinguish verified facts, provider claims, hypotheses, and measurements. No model-generated price is a sourced comparable sale.
- Preserve research separately without merging throwaway branches. This repo has no Git remote as of charting; remote branch pushes are unavailable. Record local commit/artifact pointers instead, and leave pushing pending until a remote exists.
- No production app, platform signups, credential changes, capture sessions, or Mac host changes are authorized by charting. Future Mac validation uses the fleet computer-use playbook and linked macmini environment.
- Research reports cite direct primary sources with verification dates. Never put credentials, full chat histories, or captured private screens in the tracker.

## Decisions so far

- [Which free sources can identify exact printings and provide credible raw and graded prices?](issues/01-free-card-and-price-data.md): Free catalogs and conditional graded aggregates exist, but no dependable, permission-established free raw-plus-slab sold-comp feed is established; the evidence and source choices remain human decisions.
- [What macOS capture and distribution constraints shape the hotkey MVP?](issues/02-macos-capture-and-release.md): Public APIs support a conditional capture path; consent reuse, actual viewing-platform capture, crop geometry, and focus need targeted Mac validation before architecture is locked.
- [Which BYO AI paths can return verifiable card identities quickly enough to test?](issues/03-byo-ai-recognition.md): Documented recognition paths are feasible to test; speed, accuracy, and raw-plus-slab coverage remain unmeasured, with provider compatibility and retention questions carried forward.

## Not yet specified

- Additional failure scenarios exposed by realistic auction footage: borderline printing distinctions, seller demonstrations, obstructed labels, and transitions whose handling cannot yet be designed precisely.
- Source-specific access or permission work that may become necessary once free sources have been investigated. No signup task is implied until its purpose is known.
- Onboarding and recovery details exposed by testing permissions, endpoint compatibility, missing source access, and revoked credentials.
- Additional extension or catalog migration decisions revealed by the selected recognition and pricing pipeline.

## Out of scope

- Implementation, building the production app, and executing its release; those follow the completed specification.
- Other card games, non-English cards, bundles or multi-card lot valuations, and separate-phone capture in this MVP.
- CGC/BGS and other graders at launch; the user selected PSA first, with expansion later.
- Windows, Linux, iOS, and browser-extension releases.
- Automatic bidding, checkout, auction-account automation, and reseller profit optimization.
- Continuous automatic watching as a launch requirement; the first release uses the selected-region hotkey workflow.
- Paid price-data integrations or a project-hosted paid pricing service as MVP dependencies. Revisit after the MVP in a separate effort.
- A guarantee that every arbitrary AI endpoint or local model meets the latency target. The compatibility contract and tested configurations remain decisions.
