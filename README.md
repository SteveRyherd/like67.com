# like67.com

A single-purpose joke site. When someone says "like 6... 7" you pull up the page.

**The site is live at [like67.com](https://like67.com).**

This repo is the site itself plus a transparent record of how it was built — every prompt, every change, kept in the open. If you're reading this trying to figure out how someone makes a thing like this, follow [`JOURNAL.md`](./JOURNAL.md) for the arc, or jump straight into [`sessions/`](./sessions/) for the raw transcripts.

## What's where

- `index.html` — the site
- `assets/` — images, sounds, whatever the joke needs
- `JOURNAL.md` — dated entries, one per work session, with links into the raw transcripts
- `sessions/` — prompt-and-action transcripts of each session with an AI assistant
- `KICKOFF.md` — a paste-ready prompt for starting a new session with an AI assistant; it carries the documentation rules forward so they don't drift

## Deployment

The site is hosted on [Cloudflare Pages](https://pages.cloudflare.com/), which watches this GitHub repo and deploys automatically on every push — no manual deploy step needed.

- **Production** (`main` branch) → [like67.com](https://like67.com)
- **Any other branch** → auto-gets a preview URL at `[branch-name].like67-com.pages.dev`

So the workflow is: make changes on a branch (e.g. `preview`), push to GitHub, check `preview.like67-com.pages.dev` on a real device, then merge to `main` when it looks good. Production updates within about a minute of the merge.

You don't need a Cloudflare account to follow along — just note that the "deploy" step in the session logs is just `git push`.

## How this is documented

Two rules keep the record clean:

- **File changes are made by the AI.** Whatever code or content lands in the repo, the AI wrote it. The diff IS the documentation of what changed.
- **Commands that touch the outside world are run by the human.** `git`, domain setup, deploys — these get written into the session log as copy-pasteable blocks with one or two sentences explaining what they do.

That split is also the experience for a reader: prompts that produced files, plus commands you could run yourself, with no fog in between.

## Why document this way

Most projects show you the finished thing. This one shows you the *making*: the prompts that produced each piece, the commands that were run, the dead ends. Read it the way you'd read someone else's notebook — not to copy it, but to see what the work actually looks like.
