# What capture, retention, and local-history boundaries should users control?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: grilling
Labels: wayfinder:grilling
Mode: HITL
Status: resolved
Assignee: t3 (live decision with user)
Blocked by: none

## Question

With cropped uploads and screenshot disposal by default already accepted, what remaining privacy and persistence contract should apply to capture, AI requests, local history, diagnostics, and credentials?

Decide how users see and change the selected region, confirm which provider receives it, stop capture, understand provider-side retention, and avoid uploading surrounding chats or account details. Decide whether history stores identities and source links, whether any image storage can be opted into, how correction feedback is retained, and how deletion and opt-in diagnostics work. Identify whether accessibility permission is needed at all rather than assuming it.

Establish credential handling for user-chosen endpoints and free data accounts, with no project-distributed secrets. Consider Keychain storage, redacted logs, clear errors, endpoint transport rules, and how local endpoints are represented. Do not promise the app can delete an image from an external provider once it has been sent.

## Comments

- 2026-10-31: [BYO AI research](03-byo-ai-recognition.md) supplies [provider retention and credential evidence](../../../docs/research/byo-ai-recognition.md). App-side screenshot disposal and provider-side retention require separate disclosure. The report flags inconsistent Anthropic descriptions and recent Google logging defaults; these are unresolved inputs to this decision, not a universal retention guarantee.

- 2026-10-31: Claimed after the price-evidence contract resolved. Honor the user's request for a simple MVP. Propose a single minimal privacy/history baseline and confirm the hotkey upload behavior rather than introducing optional storage/telemetry systems by default.

### First interview round — answered

- Minimal baseline proposal: API keys in the Mac's Keychain; image data in memory only; non-image scan history only until quit; no telemetry, screenshot storage, or project-hosted backend. Send the crop only to the configured AI endpoint and necessary card identifiers only to the configured pricing source. Explain that external provider retention is separate from app retention. Persistent text-only history is an alternative if the user wants it.
- Capture proposal: preview/confirm the region and destination during setup, then each deliberate hotkey sends the current crop immediately with a visible indicator and a cancel action, without a repeated confirmation dialog. No full-screen upload fallback; reselect if the crop/source becomes invalid. Window pixels may briefly exist in local memory before cropping; the upload is cropped.

The user accepted the complete minimal baseline and setup-once/immediate-hotkey behavior. They explicitly requested longer-term history in a future release, not in the MVP. Source/endpoint transport compatibility and no-backend feasibility must still pass their validation decisions.

### Resolution

The user's answers settle the MVP privacy, history and upload interaction contract. Optional image storage, persistent scan history, telemetry and project-hosted services are not required to implement it.

## Answer

- **Credentials and configuration:** store user API keys in the Mac's Keychain, bound to their configured service; no project-distributed shared secret or credential forwarding when a destination changes. Non-secret settings may persist locally so setup is reusable; session-only refers to scan history, not deleting preferences or keys on quit.
- **Session history:** retain non-image scan identities, outcomes and source evidence only for the current app session; discard that history on quit and start empty on relaunch. No screenshot archive, background history synchronization, or automatic export. Longer-term history is a future-release feature.
- **Image handling:** the app does not write screenshot files, image history, or payload-bearing diagnostics. Keep captured pixels in memory only as needed for cropping and the active request, then release them. A full selected window can briefly exist locally before cropping; only the selected crop is uploaded. Do not silently fall back to full-window/full-screen uploads.
- **Destinations:** send crops to the explicitly configured AI endpoint, and only necessary card/printing/grade identifiers to the configured pricing source. No project-hosted backend, telemetry, or app-owned image collection in the MVP. Source validation must establish that direct user-owned access is actually possible.
- **Setup and trigger:** preview/confirm the capture region and AI destination during setup. Each deliberate hotkey then sends the current crop immediately, without a per-scan confirmation dialog, with a visible capture/upload indicator and a cancel action. An invalidated source/region requires reselection instead of guessing another capture target. Destination changes must be explicit.
- **Cancel and disclosure:** cancel local/transport work where possible and prevent late results from becoming current; do not promise to reverse external processing, deletion, or charges after sending. Explain provider-side retention separately from local app retention using the actual selected endpoint's policies.
- **Permissions and diagnostics:** request only permissions required by the chosen capture/shortcut implementation. Keep keys and screen content out of logs and error reports; no additional keyboard monitoring or analytics system is implied by this decision.

This approves a product contract, not a running capture session, external account signup, credential access, or paid inference test. Actual region invalidation/focus behavior, endpoint compatibility, and source access remain subject to the existing Mac, AI and free-source validation work.
