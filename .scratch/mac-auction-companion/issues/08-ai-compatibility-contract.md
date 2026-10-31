# Which AI configurations are supported and how is compatibility checked?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: resolved
Assignee: t3 (live decision with user)
Blocked by: 03, 07

## Question

Which provider adapters or compatible endpoints will the first release explicitly support, and how will users verify that their selected model can accept images and return catalog-verifiable identity candidates?

Use the research to choose a minimal launch contract for endpoint configuration, model selection, structured output, image transport, timeouts, cancellation, rate limits, schema errors, credentials, and privacy disclosure. Distinguish merely connecting from passing accuracy and speed checks. Determine the position of optional local endpoints without imposing local-only inference as a launch requirement.

Agree any capability check and its cost/consent UX, spend or repeated-request controls, degraded operation, and the tested configurations for which latency claims may be made. User-paid AI usage is allowed; paid price-data access remains excluded. No provider choice should silently introduce an app-owned paid backend.

## Comments

- 2026-10-31: [BYO AI research](03-byo-ai-recognition.md) is resolved with [documented protocol and compatibility findings](../../../docs/research/byo-ai-recognition.md). Review the Gemini collector-use/region eligibility question before offering it as a launch adapter. Choose supported protocol/model pairs and test image plus structured output together; an OpenAI-compatible label alone is insufficient. No adapter has been selected and no recognition request has been measured.

- 2026-10-31: Claimed after [privacy and session history](07-crop-privacy-and-local-history.md) resolved. Keep provider traffic direct, respect the user's simple-MVP preference, and do not introduce a hosted proxy or hidden billable setup calls.

### First interview round — answered

- Launch connector proposal: one configurable OpenAI-compatible vision connector with user-owned API key, endpoint URL and model selection, rather than separate native vendor adapters. Require image-plus-structured-output capability checks and at least one documented/tested configuration before support claims. Other model/endpoint combinations are unverified until they pass the same checks; a compatibility label is not a promise. Native Anthropic/Gemini and packaged local runtimes would not be implied by this proposal.
- Request/cost proposal: at most one AI request to the selected configuration per scan, bounded by the agreed deadline, with no automatic retries, provider switching or hidden warm-up calls. Any potentially billable setup test is explicitly user-triggered; failures/timeouts offer manual retry. This does not guarantee remote cancellation or an exact final bill.

The user selected **OpenRouter for the MVP**, with direct OpenAI and Anthropic support in later releases, and accepted at most one AI request per scan with manual retry. This narrows the generic compatible-endpoint proposal to one service. Named model defaults, conformance cases and speed/accuracy claims must still be grounded in future validation, not guessed from documentation.

### Documentation check

Checked 2026-10-31 using OpenAI Docs guidance: official [image-input documentation](https://developers.openai.com/api/docs/guides/images-vision?api-mode=chat) documents Chat Completions image analysis; [structured-output documentation](https://developers.openai.com/api/docs/guides/structured-outputs?api-mode=chat) documents JSON Schema output for supported models. These facts support testing this protocol as a candidate; they do not establish another provider's compatibility, card accuracy, model eligibility, or end-to-end latency. No model was selected or API request executed.

### OpenRouter documentation check — 2026-10-31

OpenRouter's [vision guide](https://openrouter.ai/blog/tutorials/send-image-to-llm/) documents inline base64 image input through Chat Completions. The MVP can send an in-memory crop without a publicly hosted image. Image-capable model/endpoint eligibility still needs checking.

Its [structured-output guide](https://openrouter.ai/docs/guides/features/structured-outputs) documents `response_format` with JSON Schema and endpoint-specific support. Enforcement varies, so validate returned data locally even with strict mode; no valid JSON response alone proves a real card identity.

Its [routing reference](https://openrouter.ai/docs/guides/routing/provider-selection) documents provider fallback enabled by default, `allow_fallbacks: false` to disable backup attempts, and `require_parameters: true` to require parameter support. Use a single explicit model, no automatic model router or fallback list, and no client retries. Model/endpoint availability and served-provider identity belong in validation and diagnostics, with no payload logging.

OpenRouter's [data-collection policy](https://openrouter.ai/docs/guides/privacy/data-collection) and [provider logging policy](https://openrouter.ai/docs/guides/privacy/provider-logging) distinguish OpenRouter's handling from upstream hosts' policies. Account logging settings and documented exceptions matter; local screenshot disposal is not a guarantee of external zero retention. No account or inference request was used for this check.

### Resolution

The user chose the service and request policy. API compatibility is a launch contract with validation obligations, not a claim that a particular model already works.

## Answer

- **MVP service:** OpenRouter only. The app uses the user's OpenRouter API key, stored in Keychain, and a selected eligible OpenRouter model. Use its Chat Completions image-plus-schema path directly from the Mac; no app-owned proxy or publicly hosted screenshots. Arbitrary API base URLs, native local runtimes, and direct OpenAI/Anthropic/Gemini adapters are not launch requirements.
- **Future expansion:** direct OpenAI and Anthropic support is explicitly deferred. Models accessed through OpenRouter may be from those vendors if they meet the contract; that does not create a direct vendor integration. No OpenRouter BYOK feature or additional upstream-provider keys are required by the app.
- **Compatibility:** require image input and supported structured output on the actual serving route, perform local schema and catalog validation, and handle refusal, invalid/truncated output, rate limits, auth/balance errors and unsupported configurations explicitly. Model-list or text-only connection success is insufficient. Maintain at least one documented tested configuration before launch support claims; other configurations do not inherit its accuracy or speed claims.
- **Request bound:** at most one AI inference request per deliberate scan, with an absolute deadline. Disable client automatic retries, OpenRouter provider fallback, model-fallback lists and automatic model routing. Failure or timeout offers manual retry; never silently switch services or issue a second paid recognition attempt.
- **Setup/cost:** any potentially billable compatibility test is explicit and user-triggered. No hidden warm-up or background inference calls. Returned usage/cost can inform the current session, but the app does not claim a guaranteed final bill or refund after cancellation.
- **Result ownership:** tie every response to its scan, stop local/transport work on cancel or supersession where possible, and reject late results. Price-source lookups are separate from this one-AI-request bound.
- **Retention:** disclose both OpenRouter and the selected serving provider, with their applicable policies/settings. Do not equate provider training controls, local disposal, and external zero retention.

Specific model/route recommendations, empirical image/schema conformance, paid test budget, and latency/accuracy measurements remain work for [quality and latency validation](09-latency-and-quality-bar.md) and the dependent prototypes/architecture. No model has been benchmarked, key accessed, or inference call made. This decision resolves provider scope and the compatibility/request contract only.
