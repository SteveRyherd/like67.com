# Build Journal

A short, dated log of work sessions on like67.com. Each entry summarizes what happened and links to the full transcript in `sessions/`.

## How to read this

- Skim the journal for the arc.
- Click into a session for the actual prompts and the actions they produced.
- Sessions are numbered chronologically. Session 000 is pre-Claude (a ChatGPT preview).

---

## 2026-04-29 — Session 005: Docs update and mobile chant layout

Updated `README.md` and `KICKOFF.md` to reflect the live site at like67.com and the Cloudflare Pages deployment model (push to any branch, get an auto-preview URL; merge to main to ship). Baked the preview-branch workflow into the session instructions so it's the default going forward. On the site itself, split the "SIX SEVEN SIX SEVEN" chant into a responsive layout: widescreen keeps the single bottom row, mobile shows "SIX SEVEN" above and below the big numbers. Also fixed the white safe-area border that appeared in landscape on notched iPhones — `viewport-fit=cover` plus `html { background: #000 }`.

→ Full transcript: [sessions/005-docs-and-tweaks.md](./sessions/005-docs-and-tweaks.md)

## 2026-04-29 — Session 004: Title, mobile layout, GitHub link

Fixed the link-preview title (`6 7 Meme Chaos Animation` → `like 6… 7`), added Open Graph meta tags so iMessage and social previews render something intentional, fixed iOS Safari viewport clipping (the `100vh` bug that was cutting off the chant text and clipping the top of the color spiral) by layering `100dvh` over the existing fallbacks, tuned the chant font size for mobile, added `theme-color: black` for the iOS status bar, and added a small GitHub badge in the bottom-right corner. Also discovered that Cloudflare Pages custom domains always track production — removed the misleading `preview.like67.com` alias; staging lives at `preview.like67-com.pages.dev`.

→ Full transcript: [sessions/004-title-mobile-github.md](./sessions/004-title-mobile-github.md)

## 2026-04-29 — Session 003: License, hosting, and DNS

Added a CC BY-NC 4.0 license, picked Cloudflare Pages for hosting (free tier, CDN-distributed, auto-deploys on push), and got like67.com live. Also documented the git identity gotcha that surfaces on a fresh machine — worth capturing for anyone following along. DNS runs through Cloudflare; domain registration stays at Namecheap for now.

→ Full transcript: [sessions/003-license-hosting-dns.md](./sessions/003-license-hosting-dns.md)

## 2026-04-29 — Session 002: Import the ChatGPT prototype

Backfilled Session 000 with the actual ChatGPT conversation that produced the first HTML draft. The transcript was preserved twice: once as a styled HTML artifact (captured via the Claude in Chrome extension) and once as a prompt-and-action markdown file. Assembled the JSFiddle-ready HTML/CSS/JS blocks ChatGPT provided into a single `index.html` at the project root — the site now has a working first version.

→ Full transcript: [sessions/002-import-chatgpt-prototype.md](./sessions/002-import-chatgpt-prototype.md)
→ The pre-Claude origin: [sessions/000-chatgpt-html-preview.md](./sessions/000-chatgpt-html-preview.md)

## 2026-04-29 — Session 001: Kickoff and strategy

Decided how this project would be documented. Settled on a layered approach: raw transcripts in `sessions/`, a running summary here, and the rule that the AI writes files while the human runs environment-changing commands. Scaffolded the repo skeleton, initialized git, and pushed the first commit to https://github.com/SteveRyherd/like67.com. Captured a `KICKOFF.md` so future sessions can be primed with the documentation rules in a single paste.

→ Full transcript: [sessions/001-kickoff-and-strategy.md](./sessions/001-kickoff-and-strategy.md)
