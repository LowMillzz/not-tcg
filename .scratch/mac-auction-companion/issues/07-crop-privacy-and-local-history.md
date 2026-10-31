# What capture, retention, and local-history boundaries should users control?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: claimed
Assignee: t3 (live decision with user)
Blocked by: none

## Question

With cropped uploads and screenshot disposal by default already accepted, what remaining privacy and persistence contract should apply to capture, AI requests, local history, diagnostics, and credentials?

Decide how users see and change the selected region, confirm which provider receives it, stop capture, understand provider-side retention, and avoid uploading surrounding chats or account details. Decide whether history stores identities and source links, whether any image storage can be opted into, how correction feedback is retained, and how deletion and opt-in diagnostics work. Identify whether accessibility permission is needed at all rather than assuming it.

Establish credential handling for user-chosen endpoints and free data accounts, with no project-distributed secrets. Consider Keychain storage, redacted logs, clear errors, endpoint transport rules, and how local endpoints are represented. Do not promise the app can delete an image from an external provider once it has been sent.

## Comments

- 2026-10-31: [BYO AI research](03-byo-ai-recognition.md) supplies [provider retention and credential evidence](../../../docs/research/byo-ai-recognition.md). App-side screenshot disposal and provider-side retention require separate disclosure. The report flags inconsistent Anthropic descriptions and recent Google logging defaults; these are unresolved inputs to this decision, not a universal retention guarantee.

- 2026-10-31: Claimed after the price-evidence contract resolved. Honor the user's request for a simple MVP. Propose a single minimal privacy/history baseline and confirm the hotkey upload behavior rather than introducing optional storage/telemetry systems by default.

### First interview round — awaiting answers

- Minimal baseline proposal: API keys in the Mac's Keychain; image data in memory only; non-image scan history only until quit; no telemetry, screenshot storage, or project-hosted backend. Send the crop only to the configured AI endpoint and necessary card identifiers only to the configured pricing source. Explain that external provider retention is separate from app retention. Persistent text-only history is an alternative if the user wants it.
- Capture proposal: preview/confirm the region and destination during setup, then each deliberate hotkey sends the current crop immediately with a visible indicator and a cancel action, without a repeated confirmation dialog. No full-screen upload fallback; reselect if the crop/source becomes invalid. Window pixels may briefly exist in local memory before cropping; the upload is cropped.

These remain proposals awaiting the user's choices. Source/endpoint transport compatibility and no-backend feasibility must still pass their respective validation decisions.
