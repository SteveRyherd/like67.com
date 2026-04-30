# Session Kickoff Prompt

Paste this at the start of any new session (Claude, or any other capable assistant) to bring the helper up to speed on the like67.com project and how we document it.

---

We're working on **like67.com**, a single-purpose joke website — a "brainrot" page for when someone says "like 6... 7." The repo is at https://github.com/SteveRyherd/like67.com and lives locally at `~/Documents/Claude/Projects/Like67`. **The site is live at https://like67.com.**

## Deployment model

Hosting is on Cloudflare Pages, which auto-deploys on every push:

- `main` branch → **production** at like67.com
- Any other branch → **preview** at `[branch-name].like67-com.pages.dev` (e.g. `preview.like67-com.pages.dev`)

The standard workflow is to make changes on the `preview` branch, verify at the preview URL, then merge to `main` to ship. "Deploy" just means `git push` — Cloudflare handles the rest.

## How this project is documented

Every working session is captured as a transcript in `sessions/`, in **prompt → action** format. The goal is for someone reading the history to see how the site was actually built, prompt by prompt, without being buried in commentary.

Three rules keep the record clean:

1. **You (the assistant) write files.** Code and content changes happen through your file tools. Whatever lands in the repo, the git diff IS the record of what changed.
2. **The human runs environment-changing commands.** `git`, `gh`, deploys, anything that touches state outside the project folder. Surface those as copy-pasteable code blocks with one or two sentences of plain-English explanation, so they read cleanly when folded into the session log.
3. **Read-only inspection is silent.** Listing files, peeking at content, checking what's there — you do that as needed and it does not go in the log.

## Read these first

Before doing anything else, read these files so you have full context:

- `README.md` — top-level intro
- `JOURNAL.md` — running build log, dated entries, links into sessions
- `sessions/README.md` — the format note for transcripts
- The most recent file in `sessions/` — picks up where the last session left off

## At session start

1. Read the files above.
2. Figure out what session number this is — look at the highest-numbered file in `sessions/` and add one.
3. Create a stub at `sessions/NNN-short-slug.md` with the date, stated goal, and a note that it's in progress.
4. All file changes in a session go on the `preview` branch (not `main` directly). If the human hasn't set it up yet, surface the commands to create and check it out.

## At session end

1. Fill in the session transcript: prompts verbatim in blockquotes, actions as terse summaries (what got done, not why).
2. Add a `## Files touched` and a `## Commands run` section at the bottom.
3. Add a one-paragraph entry to `JOURNAL.md` that links back to the new session file.
4. Suggest the git commands the human should run — in this order:
   - Commit the session's changes on `preview` and push
   - Verify on `preview.like67-com.pages.dev` (the human does this step manually)
   - Merge `preview` into `main` and push to ship to production
   - Check back out to `preview` to be ready for the next session

   Example block:
   ```bash
   git add -A
   git commit -m "Session NNN: short description"
   git push
   # check preview.like67-com.pages.dev, then:
   git checkout main
   git merge preview
   git push
   git checkout preview
   ```

## Tone

Light. The site is a joke; the docs aren't, but they don't need to be heavy either. Prompt → action, no philosophical detours, let the reader form their own "whys."
