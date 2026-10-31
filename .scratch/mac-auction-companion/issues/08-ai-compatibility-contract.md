# Which AI configurations are supported and how is compatibility checked?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: open
Assignee: unassigned
Blocked by: 03, 07

## Question

Which provider adapters or compatible endpoints will the first release explicitly support, and how will users verify that their selected model can accept images and return catalog-verifiable identity candidates?

Use the research to choose a minimal launch contract for endpoint configuration, model selection, structured output, image transport, timeouts, cancellation, rate limits, schema errors, credentials, and privacy disclosure. Distinguish merely connecting from passing accuracy and speed checks. Determine the position of optional local endpoints without imposing local-only inference as a launch requirement.

Agree any capability check and its cost/consent UX, spend or repeated-request controls, degraded operation, and the tested configurations for which latency claims may be made. User-paid AI usage is allowed; paid price-data access remains excluded. No provider choice should silently introduce an app-owned paid backend.

## Comments

- 2026-10-31: [BYO AI research](03-byo-ai-recognition.md) is resolved with [documented protocol and compatibility findings](../../../docs/research/byo-ai-recognition.md). Review the Gemini collector-use/region eligibility question before offering it as a launch adapter. Choose supported protocol/model pairs and test image plus structured output together; an OpenAI-compatible label alone is insufficient. No adapter has been selected and no recognition request has been measured.
