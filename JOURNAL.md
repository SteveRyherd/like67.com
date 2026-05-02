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

Reviewed the project through the eyes of a beginner who clicks the GitHub link with no prior context, named the vocabulary trap and the invisible scaffolding (Cowork Project, pre-existing accounts) that make the project look easier than it really is, and picked off a tight first-pass set of quick wins. Rewrote `README.md` for a curious 10+ reader: new welcoming lede pointing at `JOURNAL.md` as the entry point, a sentence calling out that the whole site was built in a single afternoon, a plain-English "what each file is" list (now including `manifest.json`, `LICENSE`, and `.gitignore`, with `KICKOFF.md` clearly labeled as "for the AI, not for you"), a new "Tools used" section that's honest about what costs money and what's optional, and inline parentheticals defining "repo," "push," and "diff" the first time each appears. Also set the GitHub repo's About sidebar — description, homepage link, and topic tags — so a kid-friendly summary greets anyone who lands on the repo before they ever scroll to the README.

→ Full transcript: [sessions/008-readme-front-door.md](./sessions/008-readme-front-door.md)

## 2026-04-30 — Session 009: Strategy review and roadmap

Stepped back from building to review the project as a marketing/business advisor would. Worked through the strategic crossroads (joke site versus durable educational artifact) and locked in the educational artifact as the primary audience. Surfaced the project's real mission in one sentence — *AI can be a tool that helps kids and the general public level the playing field with their ideas* — anchored by the user's own origin stories: Million Dollar Homepage, GameFAQs, and Geocities-on-a-friend's-computer where saving a page to the desktop felt like editing the live internet. Reframed like67 as the Geocities of the AI era: talking to an AI as the new View Source, same magic restored. Talked through whether money is a stronger hook than possibility (it isn't, for this project) and sharpened a sponsor-ticker concept — live MDH-style counter, historic page, curated and COPPA-safe — into something that fits Phase 3 without becoming the project's center of gravity. Closed by writing `ROADMAP.md`: three phases (Foundation → On-ramp + Tutorial → Amplification), session numbers as scope guides, plus the standing pattern that every future session gets its own tutorial entry. The OG share card got pulled forward into Phase 1; the sponsor mechanic stays in Phase 3. No site code changed — that starts in session 010.

→ Full transcript: [sessions/009-strategy-and-roadmap.md](./sessions/009-strategy-and-roadmap.md)

## 2026-04-30 — Session 010: Analytics and corner-link rewrite

First Phase 1 build session. Replaced the bottom-right GitHub icon with text reading "How was this made? →", styled to match the existing fullscreen/home-screen hints — same `system-ui` font, same 11px size, same low resting opacity, same brighten-on-hover. All three bottom-corner labels now read as one typographic family, and the link points at the artifact's *story* rather than just its source code. On the analytics side, enabled Cloudflare Web Analytics for `like67.com` from the Cloudflare dashboard. Cloudflare auto-detected the Pages project and skipped the manual-snippet flow, so the beacon is auto-injected on every route — cookie-free, COPPA-safe, no code change to the repo. Documented the trade-off: the analytics tag isn't visible in `index.html`, which is a small loss for the educational-artifact angle but easy to revisit later by flipping the Web Analytics site setting to manual.

→ Full transcript: [sessions/010-analytics-and-corner-link.md](./sessions/010-analytics-and-corner-link.md)

## 2026-04-30 — Session 011: OG image and hint polish

Created a real 1200×630 OG share image (`assets/og-image.png`) generated via a Pillow/numpy script: dark radial gradient, coloured glow blobs at the corners, scanlines, glowing "6 ⚡ 7" numbers, a "like 6… 7" headline at the top, "you know why you're here." tagline, and a `like67.com` pill-button CTA at the bottom. Wired into `index.html` with `og:image` tags and `twitter:card: summary_large_image`. Ran the result through opengraph.xyz mid-session; revised the image to add the headline and CTA, and expanded `og:title` (~38 chars) and `og:description` (~120 chars) to hit recommended lengths. Also bumped the resting opacity on all three corner labels ("How was this made? →", fullscreen hint, home-screen hint) from 0.3 to 0.5 — still subtle, actually readable.

→ Full transcript: [sessions/011-og-image-and-hint-polish.md](./sessions/011-og-image-and-hint-polish.md)

## 2026-04-30 — Session 012: The placard

Wrote `STORY.md` — the first-person origin essay that answers "why does this exist." Drawn from source memories: editing the MSN homepage at age 9-10 on a friend's dad's computer (right-click save, didn't know if they were changing it for everyone), Geocities and the Yahoo directory era before Google, GameFAQs and user #1694 "Steve" (Jeff's one-person internet that mattered to everyone who played games), Million Dollar Homepage as a mark on the world. The pivot section ("Then the internet got big. Then it got smooth. Then it got owned.") sets up the AI reveal: like67.com, built in an afternoon, no code written. Closes with the thesis: the craziness is back. Also wired `STORY.md` as the README's first "start here" link, with full restructure deferred to session 013.

→ Full transcript: [sessions/012-the-placard.md](./sessions/012-the-placard.md)

## 2026-04-30 — Session 013: README restructure

Restructured `README.md` to make `STORY.md` the front door. The new opening line is a direct "Start with the story →" link. The mission statement — *AI can be a tool that helps kids and the general public level the playing field with their ideas* — is now pinned as a blockquote near the top. The file list was reordered (story docs first, then site files) and `ROADMAP.md` was added (it was missing). The redundant "Why document this way" closing section was trimmed. Also completed the `sessions/README.md` index, which was missing entries for sessions 008–013.

→ Full transcript: [sessions/013-readme-restructure.md](./sessions/013-readme-restructure.md)

## 2026-05-01 — Session 014: Tutorial design pass

First Phase 2 build session. Designed the tutorial through three rounds of iteration: locked in chronological order as the spine (instead of a "logical" setup-first sequence) because the project's whole pitch is that you don't need a setup checklist; agreed on a two-column shape per session — *For the 10-year-old* on the left (plain English, no brand names) and *To replicate it* on the right (specific tools, verbatim prompts, commands); added a "What we already knew (without realizing it)" slot to surface the invisible scaffolding baked into every prompt; renamed the vocabulary slot to "Concepts introduced in this section" and built it as native `<details>` accordions so each concept expands inline with a definition and an example; gave the raw-transcript link its own quiet callout at the top of every section so the "this is curated, the unedited record lives one click away" meta-lesson is explicit; ran every acronym through `<abbr title="...">` with a dotted underline, full term on first mention. Cut self-referential sessions from the tutorial (001, 005-docs, 006, 008, 009, 012, 013) so the walkthrough stays an idea-to-live how-to instead of a meta-doc — the seven kept sections are 000, 002, 003, 004 (+ chant from 005), 007, 010, 011. Shipped a single self-contained page at `/how-this-was-made-in-6-7-hours/index.html` with a sticky chronological sidebar, a small "by topic" cross-index, scrollspy, §1 (the ChatGPT prototype) fully fleshed, and §2–§7 stubbed with topic previews. Repointed the main site's bottom-right *How was this made? →* corner-link from the GitHub repo to the tutorial. Updated `ROADMAP.md` Phase 2 to reflect the URL, the per-session template, the scope cut, and the new framing of Sessions 016/017 as "flesh out §2–§4" and "flesh out §5–§7."

→ Full transcript: [sessions/014-tutorial-design.md](./sessions/014-tutorial-design.md)

## 2026-05-02 — Session 015: Flesh out all tutorial sections (§2–§7)

Corrected the roadmap's session order (glossary moved to 016, after all sections are written). Fleshed out all six remaining tutorial stubs in one session. Also locked in a writing standard: both columns assume zero programming knowledge — the left column uses plain English only, the right column *introduces* jargon with inline explanations rather than dropping terms cold. Fixed several violations of that standard in §2–§4 (removed "not in version control," introduced Git as "software that records a full history of every change, like an undo button that goes back years," explained `git add/commit/push` inline on first use). Corrected the §2 "What I already knew" row to reflect that Steve had prior Git/GitHub experience — the tutorial had falsely implied he was learning it from scratch. §5 (PWA, manifest, icons, device hints), §6 (Cloudflare Web Analytics + corner-link rewrite), and §7 (AI-generated Python/Pillow OG image, opengraph.xyz testing). Tutorial grew from 783 to 1,603 lines; no stubs remain.

→ Full transcript: [sessions/015-flesh-out-s2-s4.md](./sessions/015-flesh-out-s2-s4.md)

## 2026-05-02 — Session 016: DIY prompt and "how it was made" landing page

Meta session: no site features, all infrastructure. Distilled the sixteen build sessions into a single copyable AI prompt that walks a complete beginner from blank folder to live website — behavior rules, seven phases, capability detection so it adapts to whatever AI they're using. Shipped the prompt as a new page at `/make-your-own/`, designed as the "how it was made" landing entry point rather than just a prompt dump. Main new feature is a five-row **layer nav** — numbered 1–5, plain English per row, "you're here" badge on the current layer — so an 8-year-old and a developer hit the same page and each finds their natural next step. Sidebar phase list changed from links to plain bullets (they had nowhere useful to go). All GitHub-facing links relabeled to "view the code (on github.com)" for the younger audience. Added "Made with ♥ by Steve Ryherd 2026" to the footer of both tutorial pages alongside the existing CC BY-NC 4.0 license line.

→ Full transcript: [sessions/016-diy-prompt-landing-page.md](./sessions/016-diy-prompt-landing-page.md)
