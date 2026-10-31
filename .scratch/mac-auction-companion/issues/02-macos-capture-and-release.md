# What macOS capture and distribution constraints shape the hotkey MVP?

Parent: [Find the route to a build-ready macOS auction companion](../map.md)
Type: research
Labels: wayfinder:research
Mode: AFK
Status: claimed
Assignee: t3 (macOS research)
Blocked by: none

## Question

Which documented macOS capabilities and constraints apply to selecting an auction window or region once, triggering repeated cropped captures with a global hotkey, and showing results without taking focus from manual bidding?

Use current Apple documentation and maintained first-party project sources. Investigate ScreenCaptureKit still capture versus a low-rate stream, system content selection, permissions and revocation, window movement/resizing, scaling and multiple displays, occluded/minimized windows, full-screen Spaces, protected or unavailable video, and excluding our own overlay. Distinguish documented behavior from anything that requires an actual Mac experiment. Do not assume every platform's video is capturable.

Compare a native SwiftUI/AppKit implementation with a cross-platform shell plus native capture bridge as architectural inputs, not a selection. Establish deployment-version and Apple Silicon/Intel implications, signing, notarization, sandbox/App Store versus direct distribution, global shortcut and focus constraints, and Xcode/CI prerequisites. Distinguish OS requirements of an API from those of its latest sample project.

Do not access another host, capture a screen, run a GUI experiment, or alter host readiness. Identify the future validation checklist for Whatnot, TikTok Live, and eBay Live viewed on the Mac and note that catalog/data support does not prove viewing-platform compatibility.

Write `docs/research/macos-capture-and-release.md`, citing checked dates and direct primary sources. Include a feasibility verdict and the smallest experiments needed later.
