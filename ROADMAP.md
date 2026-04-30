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

- [ ] **Session 014 — Tutorial design pass.** No bulk authoring yet. Decide structure (one HTML page or per-session?), URL (`/tutorial/`?), and the canonical session-entry template: *where we were → what we wanted → what we asked → what got built → new concepts → try asking your AI → going deeper*. Ship the page shell + one fully-fleshed session as proof of concept.
- [ ] **Session 015 — Glossary.** Twenty terms in plain English: repo, branch, push, fork, deploy, manifest, OG, PWA, DNS, CDN, etc. Lives in `GLOSSARY.md`. Tutorial pages deep-link individual entries.
- [ ] **Session 016 — Tutorial entries for sessions 000-004.** Apply the template: origin → ChatGPT prototype → license/hosting/DNS → mobile fixes → docs and chant layout.
- [ ] **Session 017 — Tutorial entries for sessions 005-009.** Continue through to the strategy/roadmap session.
- [ ] **Session 018 — Template + gallery.** The "make your own" path. `template/` folder containing a stripped-down meme site, 5-step README in plain English, `GALLERY.md` with one or two seeded examples and a "yours could be here" slot.

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
