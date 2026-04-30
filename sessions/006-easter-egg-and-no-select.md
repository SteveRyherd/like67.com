# Session 006 — Easter egg and text selection lock

**Date:** 2026-04-29
**Goal:** Add a long-press easter egg that reveals "Audrey Burns", and harden text-selection prevention across all devices.

---

> Alright, we'd like to do a small easter egg to show "Audrey Burns" name, when doing a certain action. This should be something that can be done on a tablet, laptop, or phone. So no keyboard shortcut style easter egg if it's possible to avoid.
>
> The other thing we'd like to do is stop the text from being selectable if possible.

Chose **hold the ⚡ lightning bolt for 3 seconds** as the easter egg trigger — specific enough not to stumble on accidentally, works with a finger or mouse button, no keyboard required. Shows a pill-shaped "Audrey Burns 🎉" banner at the top of the screen using a new `.audrey` element and `@keyframes audreyPop` (3-second display, pop-in/pop-out, purple→hot-pink→cyan gradient). Added a small padding to `.dash` for an easier touch target on mobile.

For text selection: `user-select: none` was already on `body` but not vendor-prefixed. Added `-webkit-user-select: none` to the `*` selector (cascades to pseudo-elements in older WebKit), plus `-webkit-tap-highlight-color: transparent` and `-webkit-touch-callout: none` on `body` to kill the iOS tap flash and callout balloon. Suppressed the context menu on `document` so nothing leaks through on long-press anywhere.

> That's not going to be a big enough delay 600ms is very easy to accidentally discover. How about hold for 3 seconds on the lightning bolt? And we should have it say "Audrey Burns <cheer emoji>" instead

Updated: trigger moved to the `#dashBtn` (⚡) element only, hold extended to 3000ms, text changed to "Audrey Burns 🎉".

> Context menu suppression? Why wouldn't we want that for the whole page?

Moved `contextmenu` suppression from the dash element to `document`.

> The mouse cursor betrays the easter egg.

Changed `.dash` cursor from `pointer` to `default`.

---

## Files touched

- `index.html` — easter egg element + CSS + JS long-press logic; hardened selection prevention
- `sessions/006-easter-egg-and-no-select.md` — this file
- `JOURNAL.md` — session 006 entry added

## Commands run

```bash
git add -A
git commit -m "Session 006: Audrey Burns easter egg, no-select hardening"
git push
# verify at preview.like67-com.pages.dev, then:
git checkout main
git merge preview
git push
git checkout preview
```
