# Session 012 — The Placard

**Date:** 2026-04-30
**Goal:** Write the first-person origin essay — the placard that gives the project its "why." Geocities and the friend's computer, the save-to-desktop misunderstanding, GameFAQs, MDH, the moment AI changed what's possible, the leveling-the-playing-field thesis. Lands as `STORY.md`, linked from `README.md`.

---

## Prompts and actions

### 1. Kickoff

> I'm scared, let's start session 12.

Read `README.md`, `JOURNAL.md`, `sessions/README.md`, `sessions/011-og-image-and-hint-polish.md`, and `ROADMAP.md`. Confirmed session 012 scope: the placard essay. Created session stub.

### 2. Source material

> I was about 9-10, playing on my friend Justin's dad's computer. He had discovered you can right-click save a page, and then we found that we could open the file and edit the page. No clue if internet explorer had a built in editor back then, we didn't really understand what we were doing to the msn homepage.
> Later I remember when we finally got a computer of our own, I remember geocities being the resource. Everyone who had a webpage had a geocities account. You could find them by going into yahoo and browsing their catalog of pages. This was before searching by words really became the thing that Google made it.
> GameFAQs started as a web page where people submitted text files on how to beat games, and a single person uploaded and categorized them. Then later I remember when he wrote message boards for people to communicate with each other. And then he made a message board for every single game that existed. I was user number 1694: "Steve" if that gives any idea of how small the internet was back then.
> Million Dollar Homepage, it was all of that. One person was selling a spot on the internet to anyone.... and the idea was really before myspace/facebook. it was a mark on the world. It was also an insane idea, that just happened to work. People sold a lot of things on the early internet and it was the wild west.
> The essay could be read by anyone, writing it now it almost feels like a memoir.

Drew out four source memories: the Justin's-dad save-to-desktop moment (~age 9-10), Geocities and the Yahoo directory era, GameFAQs (user #1694, "Steve"), and Million Dollar Homepage. Tone guidance: memoir voice, audience is anyone.

### 3. First draft

Wrote `STORY.md` — five sections separated by `---` rules:

1. **The Justin moment** — right-click save on MSN homepage, edited the file, didn't know if they were changing it for everyone. "That confusion was the whole magic."
2. **Geocities + GameFAQs** — named Jeff, user #1694, the handmade internet before Google. "You could still be early to it."
3. **Million Dollar Homepage** — the mark on the world, audacity and simplicity.
4. **The turn** — "Then the internet got big. Then it got smooth. Then it got owned."
5. **The AI reveal + thesis** — like67.com in an afternoon, no code written. "The craziness is back — the good kind."

### 4. User edits

User revised the draft directly:
- Added "my family" for specificity ("my family finally got a computer of our own").
- Added "Seriously." for conversational punch after the Google line.
- Named Jeff in the GameFAQs section.
- Removed the "I am not a developer" paragraph — the essay earns the point without stating it.
- Changed "confusion" → "craziness" in the closing.
- Trimmed the "good confusion had drained out of it" line from the pivot section.

### 5. README wiring

Added two-line "start here" block to the README lede: `STORY.md` → why it exists, `JOURNAL.md` → how it was built. Added `STORY.md` to the "what each file is" list. Full README restructure deferred to session 013.

---

## Files touched

- `STORY.md` — new. The origin essay.
- `README.md` — lede updated to surface `STORY.md` as entry point; `STORY.md` added to file list.
- `sessions/012-the-placard.md` — this file.
- `JOURNAL.md` — session 012 entry added.

## Commands run

```bash
git add -A
git commit -m "Session 012: The placard (STORY.md) + README link"
git push
# verify on preview.like67-com.pages.dev, then:
git checkout main
git merge preview
git push
git checkout preview
```
