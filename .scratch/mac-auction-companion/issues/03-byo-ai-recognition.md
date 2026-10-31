# Which BYO AI paths can return verifiable card identities quickly enough to test?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: research
Labels: wayfinder:research
Mode: AFK
Status: resolved
Assignee: t3 (BYO AI research)
Blocked by: none

## Question

What current API capabilities and on-device recognition options support sending one cropped raw card or slab image to the user's configured provider and obtaining structured identity candidates that can be checked against a real catalog?

Investigate representative documented vision APIs (OpenAI, Anthropic, Google) and compatible/local endpoints, plus Apple's on-device Vision OCR as a possible preprocessing path. Treat these as candidates rather than a promise to ship every adapter. For OpenAI facts, consult the available openai-docs skill and official sources. Establish image support, schema/tool-output differences, IDs and grades that require verification, endpoint compatibility limits, request cancellation/timeouts, rate limits, credentials, image retention, and user-paid inference-cost considerations. Never treat an OpenAI-compatible label as evidence of vision or schema compatibility.

Separate published provider claims from measured latency. No API credentials are available and this is document research, so do not make paid calls or invent end-to-end performance results. Describe how image size, cold requests, network distance, retries, cache hits, and provider choice would affect a future benchmark. Consider whether a fast OCR/catalog path with AI fallback could help, while making clear that unreadable card numbers and lookalike variants still require abstention.

Write `docs/research/byo-ai-recognition.md` with checked dates, direct citations, a minimal compatibility-contract proposal, unverified assumptions, and recommendations for future measurements. No production code or provider signup.

## Comments

### Resolution — 2026-10-31

Documentation research is complete. The [research report](../../../docs/research/byo-ai-recognition.md) records documented hosted and local vision/schema paths, Apple OCR, compatibility limits, credentials, retention, cancellation, quotas, and a proposed validation plan. These establish recognition configurations worth testing, not validated performance: five-second usefulness, exact printing accuracy, grader/grade reading, and complete raw-plus-slab coverage remain unmeasured.

## Answer

Proceed to the existing human decisions and future bounded experiments; do not select an adapter or claim a performance result from documentation alone. Native hosted vision/schema APIs and some local runtimes have relevant documented capabilities. Endpoint interchangeability must be tested, model/OCR confidence is not calibrated correctness, catalog identity must be verified separately, and app screenshot disposal does not establish provider-side deletion.

The report flags Gemini collector-use/region eligibility, inconsistent Anthropic retention descriptions, and a Pokémon TCG API service notice as items requiring explicit follow-through. None is resolved by an adapter abstraction, and no source access or legal permission is inferred.

Remaining choices already have owners: [capture, retention, and local history](07-crop-privacy-and-local-history.md), [supported AI configurations](08-ai-compatibility-contract.md), [exact raw and graded coverage](04-card-identity-and-grading-scope.md), [latency and recognition quality](09-latency-and-quality-bar.md), and [ambiguity and rapid card changes](10-ambiguity-and-card-changes.md). Catalog availability belongs to [free catalog and price-data research](01-free-card-and-price-data.md). No new decision ticket is needed for questions those tickets already contain.

Evidence: [BYO AI recognition report](../../../docs/research/byo-ai-recognition.md), checked 2026-10-31; research commit `09875c197cc290ea1490b1a4f4c29bc32529b4e6`, preserved as local branch `research/byo-ai-recognition`. The cited report was copied into the parent checkout as an asset; the throwaway branch was not merged. Remote push remains pending because no remote exists. No inference calls, screen capture, signup, credential access, host changes, or app implementation occurred.
