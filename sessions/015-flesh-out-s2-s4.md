# Session 015 — Flesh out all tutorial sections (§2–§7)

**Date:** 2026-05-02
**Goal:** Fill in all remaining tutorial stubs — §2 through §7 — replacing stub notes with fully-templated entries. Also correct the roadmap's session order and tighten the writing standard for both columns.

---

## Prompts and actions

### 1. Roadmap correction — glossary order

> The glossary you mention, is that just for section 1 of the tutorial? If not, then maybe this session should be moved back a bit?

The glossary is meant to serve all seven tutorial sections — the accordion concepts across §1–§7 are supposed to deep-link into it. Writing it before §2–§7 are fleshed out would mean guessing at vocabulary. Reordered the roadmap: flesh out §2–§4 (this session), flesh out §5–§7 (merged into this session), glossary (016, now grounded in what all seven sections actually introduce).

Updated `ROADMAP.md` to reflect the new sequence.

### 2. Flesh out §2–§4

> Let's fix the roadmap to reflect that and then go into fleshing out 2-4.

Read source sessions 002, 003, 004, and 005. Applied the full per-section template to §2, §3, and §4:

- **§2 — Saving the work** (Session 002): Git, commit, push, GitHub. The three-command loop that gets the HTML off a chat window and into the permanent record. Concepts: git, repo, commit, push, GitHub.
- **§3 — On the internet** (Session 003): License, hosting decision (Cloudflare Pages), DNS, auto-deploy pipeline. Concepts: hosting, DNS, CDN, deploy, license, SSL.
- **§4 — Looking right on phones** (Sessions 004 + 005): iOS Safari `100vh` clip, OG meta tags, `theme-color`, responsive chant layout, preview branch. Concepts: viewport, Open Graph, meta tag, responsive design, branch.

Updated §4 source line to credit both sessions 004 and 005.

### 3. Writing standard correction

> "Not in version control" — I think we should explain version control. There are a LOT of words used without introduction. Our target audience for BOTH sides is NOT programmers. One side is plain English, the other side INTRODUCES the technical jargon, but doesn't assume the knowledge.

Fixed across all affected rows in §2, §3, and §4:

- Removed "not in version control" — replaced with "not tracked by any history-keeping software."
- Rewrote §2 "What I wanted" right cell: introduced Git as "software that records a full history of every change you make, like an undo button that goes back years" before using the term.
- Rewrote §2 "What got built" right cell: introduced `git add`, `git commit`, `git push` inline with parenthetical explanations rather than dropping them cold.
- Rewrote §3 "What got built" right cell: removed "webhook" and "nameserver" jargon; replaced with plain-English descriptions of what Cloudflare does.
- Rewrote §4 "Where I was" right cell: removed "browser chrome" (ambiguous with the Google Chrome browser), `overflow: hidden`, and "conic gradient" — none of which add value to a beginner reader.
- Rewrote §4 "What got built" right cell: replaced raw CSS values with plain-English descriptions.

### 4. GitHub experience correction

> Where we mention GitHub, you implied I didn't use GitHub before. There are definitely parts I'm going to have to edit, because I've used GitHub plenty. The end-user may be a beginner, but I am not so much.

Fixed §2 "What I already knew" right cell: changed from "here's what Git and GitHub are" (implying Steve had never heard of them) to "I had used Git and GitHub before on other projects — I already knew the basic loop." Added a note for beginners that the concepts section below covers what each step does.

### 5. Flesh out §5–§7

> I know it's skipping ahead sessions, but let's flesh out everything in this session. Then we can use the future sessions for cleaning up.

Read source sessions 007, 010, and 011. Applied the full template to §5, §6, and §7:

- **§5 — Save it as an app** (Session 007): PWA manifest, app icons, Apple meta tags, device-aware hint labels. Concepts: PWA, manifest.json, standalone mode, media query (pointer type).
- **§6 — Knowing if anyone's there** (Session 010): Cloudflare Web Analytics (no code change — dashboard only), corner-link rewrite from SVG icon to "How was this made? →" text. Concepts: analytics, cookies, beacon script, COPPA.
- **§7 — A real share image** (Session 011): AI-written Python/Pillow script generates the 1200×630 OG PNG; iterated via opengraph.xyz; `twitter:card` upgraded to `summary_large_image`. Concepts: OG image, Python script, Pillow, summary_large_image.

Tutorial grew from 783 lines to 1,603 lines. All seven sections are now fully fleshed — no stubs remain.

## Files touched

- `ROADMAP.md` (reordered sessions 015–017; added rationale for glossary-last; marked 015 complete)
- `sessions/015-flesh-out-s2-s4.md` (this file — scope expanded to cover §2–§7)
- `how-this-was-made-in-6-7-hours/index.html` (§2–§7 fully fleshed; §4 source line updated; jargon-drop issues fixed across §2–§4)

## Commands run

Commit and push to `preview`:

```bash
git add -A
git commit -m "Session 015: flesh out all tutorial sections §2–§7, fix jargon standard"
git push
```

Verify on `preview.like67-com.pages.dev`, then ship:

```bash
git checkout main
git merge preview
git push
git checkout preview
```
