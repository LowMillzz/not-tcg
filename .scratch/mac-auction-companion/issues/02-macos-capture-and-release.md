# What macOS capture and distribution constraints shape the hotkey MVP?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: research
Labels: wayfinder:research
Mode: AFK
Status: resolved
Assignee: t3 (macOS research)
Blocked by: none

## Question

Which documented macOS capabilities and constraints apply to selecting an auction window or region once, triggering repeated cropped captures with a global hotkey, and showing results without taking focus from manual bidding?

Use current Apple documentation and maintained first-party project sources. Investigate ScreenCaptureKit still capture versus a low-rate stream, system content selection, permissions and revocation, window movement/resizing, scaling and multiple displays, occluded/minimized windows, full-screen Spaces, protected or unavailable video, and excluding our own overlay. Distinguish documented behavior from anything that requires an actual Mac experiment. Do not assume every platform's video is capturable.

Compare a native SwiftUI/AppKit implementation with a cross-platform shell plus native capture bridge as architectural inputs, not a selection. Establish deployment-version and Apple Silicon/Intel implications, signing, notarization, sandbox/App Store versus direct distribution, global shortcut and focus constraints, and Xcode/CI prerequisites. Distinguish OS requirements of an API from those of its latest sample project.

Do not access another host, capture a screen, run a GUI experiment, or alter host readiness. Identify the future validation checklist for Whatnot, TikTok Live, and eBay Live viewed on the Mac and note that catalog/data support does not prove viewing-platform compatibility.

Write `docs/research/macos-capture-and-release.md`, citing checked dates and direct primary sources. Include a feasibility verdict and the smallest experiments needed later.

## Comments

### Resolution — 2026-10-31

Reviewed the [macOS capture and release report](../../../docs/research/macos-capture-and-release.md), checked 2026-10-31. The child committed only the report and performed no Mac experiments. The parent preserved the evidence locally without merging the throwaway branch.

## Answer

Public macOS APIs provide a conditional route to hotkey still capture, local cropping, and a result panel that does not activate the app. Documented API availability makes macOS 14 a candidate floor for original still capture plus the system picker, not a selected launch target. Current sample-project prerequisites must not be confused with API introduction versions.

Reusable picker consent for repeated standalone stills, actual auction-video capture, crop geometry/freshness, and focus preservation remain unmeasured. Single-window capture's original configuration ignores `sourceRect`, so the documented path involves cropping the returned window image locally before upload. This must not be described as ensuring that only the crop ever enters app memory. A persistent low-rate capture stream is an alternative requiring an explicit acquisition/privacy decision even if inference stays hotkey-triggered.

The report records native-versus-shell inputs, shortcuts, focus/Spaces behavior, protected/unavailable video, Intel/universal considerations, signing/notarization, sandboxing and CI. It establishes no platform/browser support or five-second performance claim.

Newly precise follow-ups: choose [launch Mac and viewing environments](14-launch-mac-and-viewing-environments.md), then perform [disposable capture validation](15-validate-hotkey-capture.md) before committing to the capture architecture. Packaged-release smoke tests belong in the eventual release acceptance plan; building/signing a production app is outside this map. Existing [privacy](07-crop-privacy-and-local-history.md), [architecture](11-mvp-architecture.md), and [release](12-open-source-and-release-contract.md) decisions retain their other inputs.

Evidence commit: `7ff260c5671ecd86f86194a2697a75f76cccbb2b`, preserved as local `research/macos-capture-and-release`; report copied into the parent checkout as an asset. Remote push remains pending because no remote exists. No Mac access, captures, builds, signups, credentials, or host changes occurred.
