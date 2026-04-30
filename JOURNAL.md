# Build Journal

A short, dated log of work sessions on like67.com. Each entry summarizes what happened and links to the full transcript in `sessions/`.

## How to read this

- Skim the journal for the arc.
- Click into a session for the actual prompts and the actions they produced.
- Sessions are numbered chronologically. Session 000 is pre-Claude (a ChatGPT preview).

---

## 2026-04-29 — Session 001: Kickoff and strategy

Decided how this project would be documented. Settled on a layered approach: raw transcripts in `sessions/`, a running summary here, and the rule that the AI writes files while the human runs environment-changing commands. Scaffolded the repo skeleton, initialized git, and pushed the first commit to https://github.com/SteveRyherd/like67.com. Captured a `KICKOFF.md` so future sessions can be primed with the documentation rules in a single paste.

→ Full transcript: [sessions/001-kickoff-and-strategy.md](./sessions/001-kickoff-and-strategy.md)

## 2026-04-29 — Session 002: Import the ChatGPT prototype

Backfilled Session 000 with the actual ChatGPT conversation that produced the first HTML draft. The transcript was preserved twice: once as a styled HTML artifact (captured via the Claude in Chrome extension) and once as a prompt-and-action markdown file. Assembled the JSFiddle-ready HTML/CSS/JS blocks ChatGPT provided into a single `index.html` at the project root — the site now has a working first version.

→ Full transcript: [sessions/002-import-chatgpt-prototype.md](./sessions/002-import-chatgpt-prototype.md)
→ The pre-Claude origin: [sessions/000-chatgpt-html-preview.md](./sessions/000-chatgpt-html-preview.md)

## 2026-04-29 — Session 003: License, hosting, and DNS

Added a CC BY-NC 4.0 license, picked Cloudflare Pages for hosting (free tier, CDN-distributed, auto-deploys on push), and got like67.com live. Also documented the git identity gotcha that surfaces on a fresh machine — worth capturing for anyone following along. DNS runs through Cloudflare; domain registration stays at Namecheap for now.

→ Full transcript: [sessions/003-license-hosting-dns.md](./sessions/003-license-hosting-dns.md)

## 2026-04-29 — Session 004: Title, mobile layout, GitHub link

Fixed the link-preview title (`6 7 Meme Chaos Animation` → `like 6… 7`), added Open Graph meta tags so iMessage and social previews render something intentional, fixed iOS Safari viewport clipping (the `100vh` bug that was cutting off the chant text and clipping the top of the color spiral) by layering `100dvh` over the existing fallbacks, tuned the chant font size for mobile, added `theme-color: black` for the iOS status bar, and added a small GitHub badge in the bottom-right corner. Also discovered that Cloudflare Pages custom domains always track production — removed the misleading `preview.like67.com` alias; staging lives at `preview.like67-com.pages.dev`.

→ Full transcript: [sessions/004-title-mobile-github.md](./sessions/004-title-mobile-github.md)

## 2026-04-29 — Session 005: Docs update and mobile chant layout

Updated `README.md` and `KICKOFF.md` to reflect the live site at like67.com and the Cloudflare Pages deployment model (push to any branch, get an auto-preview URL; merge to main to ship). Baked the preview-branch workflow into the session instructions so it's the default going forward. On the site itself, split the "SIX SEVEN SIX SEVEN" chant into a responsive layout: widescreen keeps the single bottom row, mobile shows "SIX SEVEN" above and below the big numbers. Also fixed the white safe-area border that appeared in landscape on notched iPhones — `viewport-fit=cover` plus `html { background: #000 }`.

→ Full transcript: [sessions/005-docs-and-tweaks.md](./sessions/005-docs-and-tweaks.md)

## 2026-04-29 — Session 006: Easter egg and text selection lock

Added a long-press (600ms) easter egg: hold anywhere on screen — finger or mouse — and "for Audrey Burns 🏀" pops up as a gradient pill banner for three seconds. Suppressed the iOS context menu so the long-press doesn't open a "Copy" sheet instead. Also hardened text-selection prevention: `-webkit-user-select: none` on `*`, plus `-webkit-tap-highlight-color` and `-webkit-touch-callout: none` on `body` to kill tap flash and the iOS callout balloon on all devices.

→ Full transcript: [sessions/006-easter-egg-and-no-select.md](./sessions/006-easter-egg-and-no-select.md)

## 2026-04-29 — Session 007: Fullscreen hints and PWA install

Added a subtle "Double-click for full screen" label in the bottom-left — desktop/mouse-only via `@media (hover: hover) and (pointer: fine)`, fades out after 7 seconds. On Windows/Linux it reads "Double-click · F11 for full screen" (Mac-aware UA sniff). On touch devices the same slot shows "Tap Share → Add to Home Screen" (iOS) or "Tap ⋮ → Add to Home Screen" (Android), suppressed if already running standalone. Wired up the PWA layer: `manifest.json` with `display: standalone`, generated `assets/icon-192.png` and `assets/icon-512.png` (deep purple rounded rect, hot-pink 6 / cyan 7), plus the full suite of Apple mobile web app meta tags and `apple-touch-icon`.

→ Full transcript: [sessions/007-fullscreen-hints-spa.md](./sessions/007-fullscreen-hints-spa.md)

## 2026-04-30 — Session 008: README front door for new readers

Reviewed the project through the eyes of a beginner who clicks the GitHub link with no prior context, named the vocabulary trap and the invisible scaffolding (Cowork Project, pre-existing accounts) that make the project look easier than it really is, and picked off a tight first-pass set of quick wins. Rewrote `README.md` for a curious 10+ reader: new welcoming lede pointing at `JOURNAL.md` as the entry point, a sentence calling out that the whole site was built in a single afternoon, a plain-English "what each file is" list (now including `manifest.json`, `LICENSE`, and `.gitignore`, with `KICKOFF.md` clearly labeled as "for the AI, not for you"), a new "Tools used" section that's honest about what costs money and what's optional, and inline parentheticals defining "repo," "push," and "diff" the first time each appears.

→ Full transcript: [sessions/008-readme-front-door.md](./sessions/008-readme-front-door.md)
