# like67.com

A single-purpose joke site. When someone says "like 6... 7" you pull up the page.

This repo is the site itself plus a transparent record of how it was built — every prompt, every change, kept in the open. If you're reading this trying to figure out how someone makes a thing like this, follow [`JOURNAL.md`](./JOURNAL.md) for the arc, or jump straight into [`sessions/`](./sessions/) for the raw transcripts.

## What's where

- `index.html` — the site (when it exists)
- `assets/` — images, sounds, whatever the joke needs
- `JOURNAL.md` — dated entries, one per work session, with links into the raw transcripts
- `sessions/` — prompt-and-action transcripts of each session with an AI assistant

## How this is documented

Two rules keep the record clean:

- **File changes are made by the AI.** Whatever code or content lands in the repo, the AI wrote it. The diff IS the documentation of what changed.
- **Commands that touch the outside world are run by the human.** `git`, domain setup, deploys — these get written into the session log as copy-pasteable blocks with one or two sentences explaining what they do.

That split is also the experience for a reader: prompts that produced files, plus commands you could run yourself, with no fog in between.

## Why document this way

Most projects show you the finished thing. This one shows you the *making*: the prompts that produced each piece, the commands that were run, the dead ends. Read it the way you'd read someone else's notebook — not to copy it, but to see what the work actually looks like.
