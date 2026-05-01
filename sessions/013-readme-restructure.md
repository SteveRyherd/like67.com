# Session 013 — README Restructure

**Date:** 2026-04-30
**Goal:** Make `STORY.md` the front door. Restructure `README.md` so the placard leads, the mission is pinned, and all current files (including `ROADMAP.md`) are accounted for in the file list. Trim, reorder, clean.

---

## Prompts and actions

### 1. Kickoff

> We've written the story. Let's go ahead and start working on Session 13.

Read `README.md`, `JOURNAL.md`, `sessions/README.md`, `sessions/012-the-placard.md`, `STORY.md`, and `ROADMAP.md`. Confirmed session 013 scope: README restructure. Created session stub.

### 2. README rewrite

Rewrote `README.md`:

- Opening line is now **"Start with the story →"** pointing directly at `STORY.md`.
- Mission statement pinned as a blockquote: *"AI can be a tool that helps kids and the general public level the playing field with their ideas. This site is the demo. The repo is the proof."*
- File list reordered — `STORY.md` at the top, flagged as "start here"; `JOURNAL.md` and `ROADMAP.md` follow. `index.html` moved down to after the docs.
- `ROADMAP.md` added to the file list (it was missing).
- "Why document this way" section removed — the content was redundant with "How this is documented."
- Everything else (`Tools used`, `How it gets to the internet`, `How this is documented`) unchanged except minor tightening.

### 3. Sessions index update

Updated `sessions/README.md` index — entries for sessions 008–012 were missing. Added all five, plus the 013 entry.

---

## Files touched

- `README.md` — restructured: story-first lede, mission blockquote, reordered file list, ROADMAP.md added, redundant closing section removed.
- `sessions/README.md` — sessions 008–013 added to index.
- `sessions/013-readme-restructure.md` — this file.
- `JOURNAL.md` — session 013 entry added.

## Commands run

```bash
git add -A
git commit -m "Session 013: README restructure — story first, mission pinned"
git push
# verify on preview.like67-com.pages.dev, then:
git checkout main
git merge preview
git push
git checkout preview
```
