# ROADMAP

The next several sessions, mapped out. Session numbers are scope guides, not commitments — some compress, some expand once you're inside them.

## Mission

> AI can be a tool that helps kids and the general public level the playing field with their ideas.

The site is the demo. The repo is the proof. The tutorial is the gift.

## Phase 1 — Foundation

The conversion funnel doesn't exist yet. Phase 1 builds it.

- [ ] **Session 010 — Analytics + corner-link rewrite.** Cloudflare Web Analytics tag added to `index.html` (cookie-free, COPPA-safe). Bottom-right GitHub icon swapped for inviting copy ("How was this made? →" or "Make your own →").
- [ ] **Session 011 — OG image / share card.** A real share image of the chaos so iMessage, Twitter, Facebook, and Discord previews stop looking like text-only afterthoughts. Low effort, high leverage — pulled forward from a later phase because it's foundational to anything spreading.
- [ ] **Session 012 — The placard.** First-person origin essay. Geocities and the friend's computer, the save-to-desktop misunderstanding, GameFAQs, MDH, the moment AI changed what's possible, the leveling-the-playing-field thesis. Lands as `STORY.md` linked from README, or directly in the README's lede.
- [ ] **Session 013 — README pass around the placard.** Restructure so the placard is the front door. Trim, reorder, pin the mission statement somewhere durable, add `ROADMAP.md` and any new files to the "what each file is" list.

*Phase 1 done when: a kid arriving sees a story that hooks them, has an inviting next click, and the maintainer can see whether any of it's working.*

## Phase 2 — On-ramp + Tutorial

The placard tells kids "you can do this too." Phase 2 makes that promise real.

The tutorial lives at **`/how-this-was-made-in-6-7-hours`** — a single long page with a sticky sidebar TOC. Each session entry has a two-column shape: *for the 10-year-old* (plain English, no brand names) on the left, *to replicate it* (specific tools, verbatim prompts, commands) on the right. Per-session template: *where we were → what we wanted → what we already knew (without realizing it) → what we asked → what got built → concepts introduced (accordion) → tools we used → commands we ran → questions to try (ask your AI / search / ask yourself) → going deeper*.

The tutorial intentionally covers **only the seven sessions on the idea-to-live spine** — self-referential sessions (kickoff, README rewrites, strategy, the placard) are skipped so the walkthrough stays a how-to, not a meta-doc. Skipped from the tutorial: 001, 005-docs, 006, 008, 009, 012, 013.

- [x] **Session 014 — Tutorial design pass.** Designed the page structure, two-column shape, raw-transcript callout, accordion concepts, question triad. Shipped the page shell at `/how-this-was-made-in-6-7-hours/`, with **§1 (Session 000)** fully fleshed and §2–§7 stubbed. Repointed the main site's corner-link from GitHub to the tutorial.
- [x] **Session 015 — Flesh out §2–§4.** Apply the template to: §2 Saving the work (Session 002), §3 On the internet (Session 003), §4 Looking right on phones (Session 004 + chant fix from 005).
- [x] **Session 016 — Flesh out §5–§7.** Folded into Session 015 — all seven sections fleshed in one pass.
- [ ] **Session 016 — Glossary.** Twenty-ish terms in plain English drawn from the concepts introduced across all seven tutorial sections: repo, branch, push, deploy, manifest, OG, PWA, DNS, CDN, etc. Lives in `GLOSSARY.md`. The tutorial's accordion concepts deep-link individual entries.
- [ ] **Session 017 — Template + gallery.** The "make your own" path. `template/` folder containing a stripped-down meme site, 5-step README in plain English, `GALLERY.md` with one or two seeded examples and a "yours could be here" slot.

*Phase 2 done when: a kid who's hooked has somewhere concrete to go, the words to understand what they're reading, and an interactive tutorial that primes them to keep asking their own AI.*

## Phase 3 — Amplification

Foundation and on-ramp shipped. Phase 3 gives the artifact reasons to spread and reasons to compound.

- [ ] **Session 019 — Soft launch.** Show HN post, r/internetisbeautiful submission, parents-on-Twitter thread. The angle isn't the site, it's the placard's story. Watch the analytics.
- [ ] **Sessions 020-025 (rough scope) — Sponsor mechanic.** Multi-session build: schema and architecture, brainrot-tone submission UI, Stripe Checkout with 18+ gate, realtime push (PartyKit or Cloudflare Workers + D1 + Durable Objects) + ticker, moderation pipeline, historic page, then go-live. Curated submissions only (real first name + verified city, soft-moderated) to keep COPPA-clean. The big one — not critical to soft launch, intentionally placed after.

## Standing patterns (every session forward)

Not sessions of their own — habits that bake in once Phase 2's tutorial scaffolding exists.

- Every new session gets its own tutorial entry, written as part of the session's wrap-up. The journal stays the raw record; the tutorial is the curated companion.
- New vocabulary gets a `GLOSSARY.md` entry before the session closes.
- Polish (audio, gallery seeds, tutorial refinements) slots in anywhere there's energy.

## Tutorial design principles

Worth committing to before Phase 2 builds the template.

- **Plain English on top, technical detail underneath.** `<details>` collapsibles for the "how it actually works" deep dives. A 10-year-old should be able to skim and get the gist.
- **Every new concept gets a "try asking your AI" block** with 2-3 example prompts (e.g., *"I'm a total beginner — what is DNS in plain English?"* / *"Why do I need DNS to make my website work?"* / *"Can you set up a domain for me?"*). The meta-lesson: the AI is your tutor, not just your builder.
- **"Going deeper" is one or two links max** — Cloudflare doc, MDN page, Wikipedia entry. Curiosity, not curriculum.
- **Voice matches the site.** Light. Curious. The same tone that calls `KICKOFF.md` "for the AI, not for you" can carry the tutorial.

## How this document works

Treat the session numbers as scope guides, not deadlines. If a session expands or splits, update this file in the same session and note the shift in the journal. The roadmap is meant to survive the conversation that produced it — when a new session starts, this is the second file to read after `JOURNAL.md`.
