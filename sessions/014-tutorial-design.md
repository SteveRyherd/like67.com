# Session 014 — Tutorial Design Pass

**Date:** 2026-05-01
**Goal:** Decide the structure of the tutorial (single long page vs. per-session pages, ordering, layout, navigation), then ship the page shell + one fully-fleshed proof-of-concept session.

---

## Prompts and actions

### 1. Kickoff — visual plan

> We're going to work on Phase 2, session 14+. Before we do this, let's come up with a visual plan for this: Currently I'm thinking the tutorial could be 1 long web page. … table of contents / jump menu on the side … picking and registering a URL … picking a code repository … picking a host … then the actual code. Which in my experience was actually the first thing we did. Maybe we show them that first.

Read `JOURNAL.md`, `README.md`, `ROADMAP.md`, `STORY.md`, `sessions/README.md`, and `sessions/013-readme-restructure.md` for context. Created session stub at `sessions/014-tutorial-design.md`.

Surfaced the central design tension: *logical onboarding order* (domain → repo → host → code) vs. *what actually happened* (code → repo → host → DNS). Argued for chronological as the spine — it matches the site's "leveling is a chat window" thesis, keeps the tutorial honest to the per-session journal, and lets a sticky sidebar TOC handle the "I just want hosting" use case via a small "by topic" cross-index.

Proposed: single long page; sticky left sidebar with chronological list + small "by topic" index; scrollspy to bold the current section; legible old-web visual register (cream/paper, dark text, site's pinks/cyans reserved for callouts).

### 2. Adding "what we already knew" + the question triad

> I think each tutorial section should end with questions to ask AI or to ask on Google or to ask a reader. The understood knowledge here is ... we already knew web pages were handled by HTML, that HTML was stored in a file, that file could be saved to my computer instead of just living in the chat.

Adopted both:

- New template slot: **"What we already knew (without realizing it)"** — surfaces the invisible scaffolding baked into every prompt, so a beginner sees what knowledge is being assumed before hitting the wall of not knowing it.
- Questions slot becomes a triad: **Ask your AI** (exploratory) / **Search** (canonical references) / **Ask yourself** (reflective). All three live in one labeled callout.

### 3. Two-column shape — kid version + replicate-it version

> What about having a table view, 2 columns. 1 side written for a 10 year old just wanting the basic idea, no high level knowledge, no brands … the other column written a little more detailed, involving which companies we used specifically.

Adopted. Each session entry gets two parallel columns: **For the 10-year-old** (left, plain English, no brand names) and **To replicate it** (right, specific tools, verbatim prompts, commands). Two complete narratives, synced by section anchors but readable on their own. Mocked the shape and showed it before agreeing on details.

### 4. Refining: table rows, raw-transcript slot, abbr tags, "new concepts"

> They don't have to be perfectly parallel. But we could line up the parts that are parallel. Rows/Columns like a table. … the raw transcript should have it's own special place … any time that an acronym is used we should always use the full version first or at least put it in parentheses. We should use the html for acronyms so that it pops up properly when hovered as well as making a glossary new words in each section. … Maybe "new concepts" …

Locked in:

- Lined-up rows with shared labels spanning both cells. Builder-only rows leave the left cell em-dashed.
- Raw-transcript callout in its own quiet box at the top of every section, separate from "Going deeper," so the meta-lesson (curated story vs. unedited record) is visible up front.
- All acronyms get `<abbr title="...">` with a dotted underline. First mention writes out the full term: *HyperText Markup Language (HTML)*.
- Slot renamed from "New words" to **"Concepts introduced in this section."** Built as a row of clickable chips using native `<details>` so each concept expands inline with a definition + example, working without JS, on mobile, and accessibly.
- "Before any of this" intro section deferred — each session's *What we already knew* handles its own scaffolding inline.
- Mobile toggle deferred — columns stack at narrow widths, but no separate "just the basics / just the build" mode yet.

### 5. Scope cut — idea-to-live only

> With how big this is... we may want to skip any sessions that don't have anything to do with getting the site live. … From idea, to live, that's what we want to focus on.

Cut self-referential sessions from the tutorial. The seven on the idea-to-live spine:

| § | Session | Topic |
|---|---|---|
| §1 | 000 | The idea (ChatGPT prototype) |
| §2 | 002 | Saving the work (file → repo → first push) |
| §3 | 003 | On the internet (license, hosting, DNS) |
| §4 | 004 (+ chant fix from 005) | Looking right on phones |
| §5 | 007 | Save it as an app (PWA, manifest, icons) |
| §6 | 010 | Knowing if anyone's there (analytics) |
| §7 | 011 | A real share image (OG image) |

Skipped: 001 (kickoff strategy), 005-docs, 006 (easter egg), 008 (README front door), 009 (strategy/roadmap), 012 (placard/STORY), 013 (README restructure). All self-referential or off the spine.

### 6. Build

> Go ahead and try to one-shot this tutorial section. We want it ideally in a single file … like67.com/how-this-was-made-in-6-7-hours would be fitting.

Created `how-this-was-made-in-6-7-hours/index.html` — a single self-contained file. Inline styles, inline scrollspy. Cream/paper background, dark text, system serif for the narrative, system sans for UI/sidebar/headers, system mono for code chips. Pink callout for *Questions to try*; subtle gray for raw-transcript and *Going deeper* boxes.

Built:
- Sticky top bar with brand + back-to-site link.
- Sticky left sidebar: chronological session list with `§N` numbering + small "By topic" cross-index (Repos & Git, Domains & DNS, Hosting, Mobile fixes, Apps & PWA, Analytics, Sharing & OG) + footer link to repo & journal.
- Page intro spelling out the two-column convention and the dotted-underline acronym hint.
- §1 fully fleshed: raw-transcript callout, two-column header strip, five narrative rows (where we were / what we wanted / what we already knew / what we asked / what got built), full-width concepts (six accordion entries: HTML, CSS, JavaScript, prompt, iteration loop, JSFiddle), full-width tools, full-width commands, full-width questions triad, full-width going-deeper.
- §2–§7 stubbed: section header + source-session subtitle + raw-transcript callout + a one-paragraph "topic preview" placeholder noting the full entry comes in a later session.
- Scrollspy via `IntersectionObserver` so the sidebar bolds the section in view.
- Narrow-viewport fallback: sidebar hides, a `<details>` "Jump to a section" menu appears at the top of `<main>`, and the two narrative columns stack.

### 7. Repointed the main site's corner-link

The bottom-right `How was this made? →` label on `index.html` previously linked to the GitHub repo. Repointed it to `/how-this-was-made-in-6-7-hours` so visitors land on the curated tutorial first. The GitHub link still lives at the bottom of the tutorial sidebar and footer.

### 8. Roadmap update

Updated `ROADMAP.md` Phase 2:

- Marked Session 014 as done with a summary of what shipped.
- Added the tutorial's URL, two-column shape, and per-session template to the phase preamble.
- Listed which sessions are intentionally skipped (idea-to-live focus).
- Reframed Sessions 016 & 017 from "tutorial entries for sessions 000-004 / 005-009" to "flesh out §2–§4" and "flesh out §5–§7" so the scope matches the actual tutorial sections.

### 9. Tone pass — first-person singular, centered labels, less jargon up front

> Even this tutorial and recap was generated without typing any code. … all the other subheadings should be centered. … On the right hand side, we casually start by saying "no repo, no folder," — Even for someone replicating this, we don't want to jump in and say "no repo," we want to assume they don't know anything code related. "No code, no website, nothing." … no "We" when talking about self. Part of the appeal of the early internet was it was made by "one person" … let's use the word "I" when describing the situation.

Four refinements to the tutorial copy:

- **Lead paragraph.** Trimmed *"and everybody laughs and nobody can quite explain why"* (the joke is funnier left at *"like 6… 7."*) and added a second-line punchline: *"Even this tutorial and recap was generated without typing any code."*
- **Centered subheadings.** Added `text-align: center` to `.row .label`, `.questions .label`, and `.deeper .label`. The labels (Where I was, What I wanted, …) now sit centered above each row rather than left-flush.
- **Right-column opening de-jargoned.** *"No repo, no folder on the laptop, no AI conversation open, no domain registered, no host picked"* replaced with *"No code, no website, nothing yet. Just an idea and a closed laptop."* The replicator track shouldn't open by assuming the reader already knows what a repo or a host is — those terms can be introduced when they actually appear in the work.
- **First-person singular throughout.** Replaced every author-voice "we" with "I" — both in the row labels (*Where we were → Where I was*, *What we wanted → What I wanted*, *Tools we used → Tools I used*, etc.) and in the body copy. The historical verbatim prompt block keeps its original wording. The point is to put a single person at the keyboard — the way an early-web webmaster did. Not a team.
- **Lane explanation reframed.** The columns intro got rewritten away from *"never made a website"* / *"wants to copy the whole thing"* (which read as two separate audiences) toward *"just curious in seeing the pieces"* / *"wants to learn a little more technical language (jargon) with the goal of being detailed enough to copy the whole thing"*. The right column is now framed as instructional too — it teaches jargon en route to replication, rather than assuming a reader who already speaks it. Also dropped the *"Pick a lane"* line — read snarky, wasn't needed; both columns are open to anyone.
- **Inline gloss for *build step* / *framework*.** The right cell of *What I wanted* dropped both terms without unpacking them. Added a brief inline gloss: *"No assembly step before it could run (a 'build step'), and no extra library like React to install first (a 'framework')"*. Pattern is reusable for other right-cell jargon in later sessions.
- **Three-level hierarchy.** Reorganized the per-session shape into a real heading hierarchy. **h2** is the section title (e.g. `§1 The idea`). **h3** is the subsection level: *How it went*, *Concepts introduced in this section*, *Tools I used*, *Commands I ran*, *Questions to try*, *Going deeper* — left-aligned, 20px, sans-serif, weight 500. **Row labels** (Where I was / What I wanted / What I already knew / What I asked / What got built) are now correctly third-level headings inside *How it went* — centered, small, uppercase. The narrative rows belong to one logical group; before this they sat at the same level as Tools/Commands/Questions, which made the hierarchy feel flat. Picked **"How it went"** for the umbrella name (over *Step by step*, *Narrative*, *What happened*) — plain English, doesn't claim sequence the way *Step by step* does, fits the project tone.
- **"For the 10-year-old" → "In plain English."** The original column header assumed a reader's age; the new one is about the register, not the audience. Right column header (*To replicate it*) unchanged.
- **"What I already knew (without realizing it)" → "What I already knew (that might be new to you)."** Switched the parenthetical to face the reader rather than the author. Same slot, different framing — the row is for surfacing things a reader might not yet know but the prompter took for granted.
- **Removed inner labels from the callout boxes.** *Questions to try* and *Going deeper* used to carry their own internal `.label` divs; with the h3 above each box, the inner label was redundant and got dropped. Top-margin on those boxes set to 0 so the h3's `margin-bottom: 14px` does the spacing.

---

## Files touched

- `how-this-was-made-in-6-7-hours/index.html` — created. Page shell + §1 fully fleshed + §2–§7 stubs.
- `index.html` — corner-link repointed from GitHub repo to `/how-this-was-made-in-6-7-hours`.
- `ROADMAP.md` — Phase 2 updated to reflect tutorial URL, shape, scope cut, and Session 014 done.
- `sessions/014-tutorial-design.md` — this file.
- `sessions/README.md` — index entry added.
- `JOURNAL.md` — session 014 entry appended.

## Commands run

```bash
git add -A
git commit -m "Session 014: tutorial design + page shell + §1 fully fleshed"
git push
# verify on preview.like67-com.pages.dev — open /how-this-was-made-in-6-7-hours
# then ship to production:
git checkout main
git merge preview
git push
git checkout preview
```
