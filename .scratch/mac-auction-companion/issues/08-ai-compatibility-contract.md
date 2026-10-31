# Which AI configurations are supported and how is compatibility checked?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: claimed
Assignee: t3 (live decision with user)
Blocked by: 03, 07

## Question

Which provider adapters or compatible endpoints will the first release explicitly support, and how will users verify that their selected model can accept images and return catalog-verifiable identity candidates?

Use the research to choose a minimal launch contract for endpoint configuration, model selection, structured output, image transport, timeouts, cancellation, rate limits, schema errors, credentials, and privacy disclosure. Distinguish merely connecting from passing accuracy and speed checks. Determine the position of optional local endpoints without imposing local-only inference as a launch requirement.

Agree any capability check and its cost/consent UX, spend or repeated-request controls, degraded operation, and the tested configurations for which latency claims may be made. User-paid AI usage is allowed; paid price-data access remains excluded. No provider choice should silently introduce an app-owned paid backend.

## Comments

- 2026-10-31: [BYO AI research](03-byo-ai-recognition.md) is resolved with [documented protocol and compatibility findings](../../../docs/research/byo-ai-recognition.md). Review the Gemini collector-use/region eligibility question before offering it as a launch adapter. Choose supported protocol/model pairs and test image plus structured output together; an OpenAI-compatible label alone is insufficient. No adapter has been selected and no recognition request has been measured.

- 2026-10-31: Claimed after [privacy and session history](07-crop-privacy-and-local-history.md) resolved. Keep provider traffic direct, respect the user's simple-MVP preference, and do not introduce a hosted proxy or hidden billable setup calls.

### First interview round — awaiting answers

- Launch connector proposal: one configurable OpenAI-compatible vision connector with user-owned API key, endpoint URL and model selection, rather than separate native vendor adapters. Require image-plus-structured-output capability checks and at least one documented/tested configuration before support claims. Other model/endpoint combinations are unverified until they pass the same checks; a compatibility label is not a promise. Native Anthropic/Gemini and packaged local runtimes would not be implied by this proposal.
- Request/cost proposal: at most one AI request to the selected configuration per scan, bounded by the agreed deadline, with no automatic retries, provider switching or hidden warm-up calls. Any potentially billable setup test is explicitly user-triggered; failures/timeouts offer manual retry. This does not guarantee remote cancellation or an exact final bill.

These are proposals awaiting the user, not provider/model selections. Named model defaults, conformance cases and speed/accuracy claims must still be grounded in future validation, not guessed from API documentation.

### Documentation check

Checked 2026-10-31 using OpenAI Docs guidance: official [image-input documentation](https://developers.openai.com/api/docs/guides/images-vision?api-mode=chat) documents Chat Completions image analysis; [structured-output documentation](https://developers.openai.com/api/docs/guides/structured-outputs?api-mode=chat) documents JSON Schema output for supported models. These facts support testing this protocol as a candidate; they do not establish another provider's compatibility, card accuracy, model eligibility, or end-to-end latency. No model was selected or API request executed.
