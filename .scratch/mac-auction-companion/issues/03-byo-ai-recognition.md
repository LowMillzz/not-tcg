# Which BYO AI paths can return verifiable card identities quickly enough to test?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: research
Labels: wayfinder:research
Mode: AFK
Status: claimed
Assignee: t3 (BYO AI research)
Blocked by: none

## Question

What current API capabilities and on-device recognition options support sending one cropped raw card or slab image to the user's configured provider and obtaining structured identity candidates that can be checked against a real catalog?

Investigate representative documented vision APIs (OpenAI, Anthropic, Google) and compatible/local endpoints, plus Apple's on-device Vision OCR as a possible preprocessing path. Treat these as candidates rather than a promise to ship every adapter. For OpenAI facts, consult the available openai-docs skill and official sources. Establish image support, schema/tool-output differences, IDs and grades that require verification, endpoint compatibility limits, request cancellation/timeouts, rate limits, credentials, image retention, and user-paid inference-cost considerations. Never treat an OpenAI-compatible label as evidence of vision or schema compatibility.

Separate published provider claims from measured latency. No API credentials are available and this is document research, so do not make paid calls or invent end-to-end performance results. Describe how image size, cold requests, network distance, retries, cache hits, and provider choice would affect a future benchmark. Consider whether a fast OCR/catalog path with AI fallback could help, while making clear that unreadable card numbers and lookalike variants still require abstention.

Write `docs/research/byo-ai-recognition.md` with checked dates, direct citations, a minimal compatibility-contract proposal, unverified assumptions, and recommendations for future measurements. No production code or provider signup.
