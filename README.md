# like67.com

The site is a joke. The rest of this folder is the *story* of how it got made — every prompt, every change, kept in the open. Want to see how? Start with [`JOURNAL.md`](./JOURNAL.md) and read top to bottom.

**The site is live at [like67.com](https://like67.com).** When someone says "like 6... 7," you pull up the page.

The whole site — code, domain, hosting, every feature — was built across seven sessions on a single afternoon (April 29, 2026). The code was written entirely by an AI; the human did the prompting and ran the commands that touch the outside world (git, hosting, the domain).

## What each file is

- `index.html` — the actual website. Open it in a browser and you've got the whole site.
- `assets/` — pictures and icons used by the page.
- `manifest.json` — tells phones how to save the site as an app.
- `JOURNAL.md` — a dated log of every work session, with links to the full transcripts. Read this top to bottom for the story arc.
- `sessions/` — the raw conversations with the AI, one file per session. This is where the actual making lives.
- `LICENSE` — the legal note (CC BY-NC 4.0 — fine to learn from, not for commercial use).
- `KICKOFF.md` — a paste-ready prompt for AI assistants. Skip this one; it's for the AI, not for you.
- `.gitignore` — bookkeeping; tells git which files to ignore.

## Tools used

- **Claude / Claude Cowork** — the AI assistant that wrote the code. Cowork is a desktop app that gives the AI direct read/write access to a project folder, so prompts can become real file changes. Requires a Claude account.
- **GitHub** — stores the code and the full history of every change. Free; the page you're reading right now is GitHub.
- **Cloudflare Pages** — puts the website on the internet and re-publishes it automatically every time code is pushed. Free.
- **Namecheap** — where the domain `like67.com` was registered. About $10/year, and optional — Cloudflare gives every project a free `*.pages.dev` URL automatically.

## How it gets to the internet

Cloudflare Pages watches this GitHub repo (the folder GitHub stores) and rebuilds the site every time anyone pushes (uploads a change).

- `main` branch → **production** at [like67.com](https://like67.com)
- Any other branch → an auto-generated preview URL at `[branch-name].like67-com.pages.dev`

So the workflow is: make changes on a branch like `preview`, push to GitHub, check `preview.like67-com.pages.dev` on a real device, then merge into `main` to ship. Production updates about a minute later.

"Deploy" in the session logs just means `git push`. No buttons to click.

## How this is documented

Two rules keep the record clean:

- **The AI writes files.** Whatever code or content lands in the repo, the AI wrote it. The diff (what git records as changed) IS the documentation of what changed.
- **The human runs commands that touch the outside world.** `git`, domain setup, deploys — these land in the session log as copy-pasteable blocks with a sentence or two of plain-English explanation.

That split is also the reading experience: prompts that produced files, plus commands you could run yourself, with no fog in between.

## Why document this way

Most projects show you the finished thing. This one shows you the *making*: the prompts that produced each piece, the commands that were run, the dead ends. Read it like someone else's notebook — not to copy, but to see what the work actually looks like.
