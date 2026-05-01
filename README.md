# like67.com

**[Start with the story →](./STORY.md)**

The site is a joke — a brainrot page for the moment when someone says "like 6... 7." The *repo* (this folder on GitHub) is the story of how it was made: every prompt, every change, kept in the open.

**Why this exists:** [`STORY.md`](./STORY.md)
**How it was built, session by session:** [`JOURNAL.md`](./JOURNAL.md)

**The site is live at [like67.com](https://like67.com).** The whole thing — code, domain, hosting, every feature — was built in a single afternoon (April 29, 2026). The code was written entirely by an AI; the human did the prompting and ran the commands that touch the outside world.

> **The mission:** AI can be a tool that helps kids and the general public level the playing field with their ideas. This site is the demo. The repo is the proof.

## What each file is

- `STORY.md` — **start here.** The first-person origin essay: why this exists, in plain English.
- `JOURNAL.md` — a dated log of every work session, with links to the full transcripts. Read this top to bottom for the arc.
- `ROADMAP.md` — what comes next: three phases from foundation to tutorial to amplification.
- `index.html` — the actual website. Open it in a browser and you've got the whole site.
- `sessions/` — the raw conversations with the AI, one file per session. This is where the actual making lives.
- `assets/` — pictures and icons used by the page.
- `manifest.json` — tells phones how to save the site as an app.
- `LICENSE` — the legal note (CC BY-NC 4.0 — fine to learn from, not for commercial use).
- `KICKOFF.md` — a paste-ready prompt for AI assistants. For the AI, not for you.
- `.gitignore` — bookkeeping; tells git which files to ignore.

## Tools used

- **Claude / Claude Cowork** — the AI assistant that wrote the code. Cowork is a desktop app that gives the AI direct read/write access to a project folder, so prompts can become real file changes. Requires a Claude account.
- **GitHub** — stores the code and the full history of every change. Free; the page you're reading right now is GitHub.
- **Cloudflare Pages** — puts the website on the internet and re-publishes it automatically every time code is pushed. Free.
- **Namecheap** — where the domain `like67.com` was registered. About $10/year, and optional — Cloudflare gives every project a free `*.pages.dev` URL automatically.

## How it gets to the internet

Cloudflare Pages watches this GitHub repo and rebuilds the site every time anyone pushes (uploads a change).

- `main` branch → **production** at [like67.com](https://like67.com)
- Any other branch → an auto-generated preview URL at `[branch-name].like67-com.pages.dev`

So the workflow is: make changes on a branch like `preview`, push to GitHub, check `preview.like67-com.pages.dev` on a real device, then merge into `main` to ship. Production updates about a minute later.

"Deploy" in the session logs just means `git push`. No buttons to click.

## How this is documented

Two rules keep the record clean:

- **The AI writes files.** Whatever code or content lands in the repo, the AI wrote it. The diff (what git records as changed) IS the documentation of what changed.
- **The human runs commands that touch the outside world.** `git`, domain setup, deploys — these land in the session log as copy-pasteable blocks with a sentence or two of plain-English explanation.

That split is also the reading experience: prompts that produced files, plus commands you could run yourself, with no fog in between.
