# Session 007 — Fullscreen hints and PWA / home-screen install

**Date:** 2026-04-29
**Goal:** Add a subtle desktop hint for double-click fullscreen (F11 on non-Mac), a mobile hint for "Add to Home Screen", and wire up the site as a PWA so it can be saved as a standalone app.

---

> We're pretty stable now. Let's add a small subtle message in the bottom-left on desktop computers that support it, to let users know that double-clicking will open full screen. "Double-Click for Full Screen". This at least works on my mac safari and chrome. We may also want to let people know about F11.
>
> Again this should only display when on a desktop browser window.
>
> There are other things we could do for mobile. Like adding a mention about saving a shortcut of it to the desktop. We can make this an Single page app, SPA this session.

Created `assets/icon-192.png` and `assets/icon-512.png` using ImageMagick — deep purple rounded-rect background, "6 7" in hot-pink/cyan Helvetica Bold, ~7KB and ~19KB respectively.

Created `manifest.json` with `display: standalone`, both icons, black theme/background, `orientation: any`.

Added to `<head>` in `index.html`: manifest link, `apple-mobile-web-app-capable`, `apple-mobile-web-app-status-bar-style: black-translucent`, `apple-mobile-web-app-title`, and `apple-touch-icon`.

Added two new CSS classes:

- `.fs-hint` — `display: none` by default, shown only under `@media (hover: hover) and (pointer: fine)` (mouse devices). Fixed bottom-left, 11px system-ui, 30% white opacity.
- `.home-hint` — `display: none` by default, shown only under `@media (hover: none), (pointer: coarse)` (touch devices). Same position and style.

Added two `<div>` elements in the body (above the GitHub badge) for each hint.

Added JS logic:

- **Desktop**: if `document.fullscreenEnabled`, sets label to "Double-click for full screen" (Mac) or "Double-click · F11 for full screen" (Windows/Linux, detected via `navigator.userAgent`). Fades out at 7s, hides at 8.6s, and also hides immediately on `fullscreenchange` when entering fullscreen.
- **Mobile**: checks `window.navigator.standalone` and `(display-mode: standalone)` to suppress hint if already installed. Sets label to "Tap Share → Add to Home Screen" (iOS) or "Tap ⋮ → Add to Home Screen" (Android). Same 7s/8.6s fade-and-hide cadence.

---

## Files touched

- `assets/icon-192.png` — new PWA icon, 192×192
- `assets/icon-512.png` — new PWA icon, 512×512
- `manifest.json` — new web app manifest
- `index.html` — PWA meta tags; `.fs-hint` / `.home-hint` CSS + elements + JS
- `sessions/007-fullscreen-hints-spa.md` — this file
- `JOURNAL.md` — session 007 entry added

## Commands run

```bash
git add -A
git commit -m "Session 007: fullscreen hints, PWA manifest, home-screen install"
git push
# check preview.like67-com.pages.dev, then:
git checkout main
git merge preview
git push
git checkout preview
```
