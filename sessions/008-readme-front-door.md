# Session 008 — README front door for new readers

**Date:** 2026-04-30
**Goal:** Make the README approachable for a curious 10+ reader who's never built a website before. Add a friendly opening, a "what each file is" plain-English list, a "tools used" list (with what costs money and what's optional), and inline parentheticals for the most-loaded jargon words. Demote `KICKOFF.md` so readers know it's for AI assistants, not them.

---

## Prompts and actions

### 1. Reframing the project through a beginner's lens

> With only 7 sessions, we've got a fully functional single page app, website, and it's deployed completely.
>
> Let's revisit a little bit. This project is specifically going to be shared likely from kids of all ages. The idea to share the prompts, to avoid any actual coding, and to make it as transparent as possible all started with the goal of getting kids into computers and technology.
>
> I have a lens that I see this project from, where a kid might not know a lot of the tools, technologies. For instance I'm using Claude and specifically Claude Cowork for the majority of creating this project. I'm not manually pasting [kickoff.md](http://kickoff.md) every time, I have created a Project inside of Claude Cowork and am just giving basic prompts, the instructions are copied every time and the LLM has access to my sandbox/files because I set it up that way. I also had knowledge in advance about website hosting, domain name registration, and how html works.
>
> Yes, I did "all of this" without actually touching code once, but it's not so impressive if it's not replicable by a complete beginner. It's also failed if it's not approachable by a beginner.
>
> In this session, I'd like to review everything from the eyes of a 5-10 year old beginner. They just clicked on the github link, now what? Do they have enough information to see behind the scenes? Is it friendly and approachable enough to be engaging. I don't want to make any changes to the code yet, but I'd like to review the entire project from the Point of View of an educator and with critical thinking.
>
> Later we can turn the "sessions" we've logged into tutorials, but how do we make sure that this looks approachable now, and stays that way? Let's just brainstorm a bit about these ponderings.

Walked through what a kid lands on when they click the GitHub link, surfaced the vocabulary trap (repo, branch, deploy, push, merge, manifest, PWA, viewport, OG, etc.), named the invisible scaffolding (Cowork Project, pre-existing accounts, file access pre-wired) that makes the project look easier than it is, flagged the drift problem (without discipline, the docs get less approachable as sessions pile up), and brainstormed a list of things to consider — "start here" doc, glossary, honest "what you'd need" page, plain-English ledes on sessions, a flow diagram, and a tutorial track.

### 2. Quick wins

> The target probably is a LOT closer to 10+. That's very insightful. Any "quicks wins" for the readme or project? Low hanging fruit that would help make it more approachable from that lens?

Listed eight low-effort, high-leverage changes ranked by impact. Recommended a tight first-pass scope: a friendly opening line, inline parenthetical definitions for jargon, a plain-English "what each file is" list, a "how long did this take?" sentence, demoting `KICKOFF.md` so kids don't try to use it, and a "tools used" list that's honest about what costs money and what's optional.

### 3. Doing the README pass

> Let's do it.

Rewrote `README.md`:

- New lede paragraph at the top: "The site is a joke. The rest of this folder is the *story* of how it got made…" with a clear pointer to `JOURNAL.md` as the entry point.
- Added a sentence calling out that the entire site was built across seven sessions on a single afternoon, and named the human/AI split in plain English.
- Renamed "What's where" to "What each file is" and rewrote each line in plain language. Added entries for `manifest.json`, `LICENSE`, and `.gitignore` (previously unlisted). Labeled `KICKOFF.md` as "for the AI, not for you."
- Added a new "Tools used" section listing Claude/Cowork, GitHub, Cloudflare Pages, and Namecheap, each with a one-line description and a note about cost or whether it's optional.
- Renamed "Deployment" to "How it gets to the internet" and added the parenthetical "(the folder GitHub stores)" the first time "repo" appears, plus "(uploads a change)" next to "pushes."
- Kept "How this is documented" but added a parenthetical explaining what "diff" means.
- Left "Why document this way" unchanged.

---

## Files touched

- `README.md` — front-door rewrite for new readers (lede, file list, tools list, jargon parentheticals, KICKOFF demoted)
- `sessions/008-readme-front-door.md` — this file
- `JOURNAL.md` — session 008 entry added

## Commands run

```bash
# (run on the preview branch)
git add -A
git commit -m "Session 008: README front door for new readers"
git push
# check preview.like67-com.pages.dev (the README renders on GitHub, not the live site —
# so really: check the README on github.com/SteveRyherd/like67.com on the preview branch)
git checkout main
git merge preview
git push
git checkout preview
```
