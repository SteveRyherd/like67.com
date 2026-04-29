# Session 001 — Kickoff and Strategy

**Date:** 2026-04-29
**Goal:** Decide how this project will be documented, then scaffold the repo.

## Context

like67.com is a single-purpose joke site — flashing imagery for when someone says "like 6... 7." Domain registered through Namecheap (found via namefiddle.com). The repo will live at `github.com/SteveRyherd/like67.com`. An initial HTML draft was already produced in a separate ChatGPT conversation; that will be captured as Session 000.

## Prompts and actions

### 1. Setting the documentation goal

> I am currently buying the website domain through namecheap.com, I found the domain like67.com through namefiddle.com.
>
> I am going to host this project on github.com for everyone to see, the final url for that should be github.com/steveryherd/like67.com.
>
> I have tools already on this computer for git, being a mac, but I may want future prompts or files that are saved to talk about that.
>
> Currently we are working in a claude cowork environment. I would like to document every single prompt / session with claude to the project. Whether manually or automatically, I want the end-user to be able to transparently see what we've done to create this project. I could do this as a video, documenting the process, but I would rather capture the essence of the way that I originally learned to code, through a little more exploration.
>
> Please think about the overall idea behind the documentation, and come up with a strategy. You may ask me questions to clarify what's already been done.
>
> I have slightly cheated and already generated the HTML with ChatGPT to preview the project, but I'm willing to reproduce this later or to copy that session in for logging.

Proposed a layered documentation approach: raw session transcripts in `sessions/`, a running build journal at the top level, and a `README.md` for the story arc. Floated four capture mechanisms (fully manual, structured manual, semi-automatic via the assistant dumping the transcript at session end, fully automatic), and recommended the semi-automatic option. Suggested the existing ChatGPT prototype be captured as Session 000 rather than reproduced. Asked four clarifying questions: what the site actually is, whether documentation should surface on the live site, how much reasoning to keep in transcripts, and whether the ChatGPT session was saved.

### 2. Answers and constraints

> Let's do option 3 for transcripts.
> I will paste the chatgpt transcript manually, into that file.
> I don't really need a whole HTML page for it, although later I am will to pivot.
> The GitHub page will really be the star. There are some things that we're not walking a user through though, for instance registering for Github, registering for Namecheap. As those have been done for me for years. We may want to have a section of documentation for how/why those tools are useful, what they do for development, etc. I guess outside of having transcripts, we could later use that knowledge to make a "tutorial" of how to create your own single purpose site.
>
> Like67.com is purely a "brainrot" page, it's flashing imagery designed to be a joke for when someone says "like 6 - 7", you pull up the page. At the bottom we'll include a link to "how it was made" and or the github page, and allow people to discover.
>
> Prompt->Action -- I want people to be able to simply read through how it worked, I don't want them to feel overwhelmed with "why", but also I want them to be able to think through their own "whys" when it comes to replicating the action. This isn't about mirroring me, it's about discovery.
>
> For session 0, I do have the ChatGPT session saved somewhere, I could copy/paste or otherwise export to this project.

Decisions locked in:

- Transcripts captured semi-automatically by the assistant at session end.
- Session 000 is the ChatGPT prototype; user will paste it in.
- Format is prompt → action; the assistant's reasoning is trimmed so the read stays clean.
- The GitHub repo is the primary destination. The live site will only carry a small "how it was made" link.
- A future "make your own single-purpose site" tutorial is parked as a possibility.

Proposed a concrete repo structure and a session-log template, then asked the user to point Cowork at a folder so we could work in real files.

### 3. Workflow split for documentation

> We're using Claude Cowork, which uses the concept of projects, the sandbox you have here is a real folder on my system, you can walk me through terminal commands to create a GitHub repository and I will copy/paste to run them.
>
> We're using ~/Documents/Claude/Projects/Like67
>
> If you need an absolute path just let me know. I have tried to give Claude access to file system. I typically also wouldn't care if it ran trusted commands, but for documentation purposes I'm not sure that's the best strategy.

Established the project's core documentation rule:

- **AI writes files** — code and content changes are captured by git diffs.
- **Human runs environment-changing commands** — git, domain setup, deploys; these are written into the session log as copy-pasteable blocks with brief explanations.
- **AI's read-only inspection is invisible** — listing files, peeking at content, etc. doesn't go in the log.

Mounted the project folder at `/Users/steve/Documents/Claude/Projects/Like67` into the Cowork session.

### 4. Scaffold

Created the initial repo skeleton (folder was empty):

- `README.md` — top-level intro and reading order
- `JOURNAL.md` — dated, summarized build log
- `sessions/README.md` — format note for transcripts
- `sessions/000-chatgpt-html-preview.md` — placeholder for the ChatGPT session
- `sessions/001-kickoff-and-strategy.md` — this file (a stub during the session, finalized at the end)
- `.gitignore` — sensible Mac/editor defaults

`index.html` and `assets/` were deliberately not created. They belong to Session 002.

### 5. Initial git setup

> I've ran those commands, "done" -- everything created succesfully and https://github.com/SteveRyherd/like67.com is properly showing the readme and files

User initialized the local repo, committed the scaffold, and created the public GitHub repo via `gh`. Repo live at https://github.com/SteveRyherd/like67.com.

### 6. A kickoff prompt for future sessions

> We should probably also create a project "description" that I can copy-paste that reminds us and kicks off the LLM sessions with our documentation strategy and structure? I can copy paste that, and then I will start a new session to continue the project from there. (After you compose a reply, it may be worth amending the transcript to add this part of the conversation).

Created `KICKOFF.md` at the project root — a paste-ready prompt that summarizes the project, lays out the three documentation rules, lists the files an assistant should read first, and describes what to do at session start and session end. Linked from `README.md`. This transcript was amended to include the present exchange.

## Outcome

- Documentation strategy decided and written into `README.md`: prompt → action transcripts in `sessions/`, summary in `JOURNAL.md`, AI writes files, human runs environment commands.
- Repo scaffolded locally and pushed to GitHub.
- `KICKOFF.md` created so future sessions can be primed with the documentation rules in one paste.
- Session 000 placeholder is waiting for the ChatGPT transcript to be pasted in.
- Future tutorial spinoff ("make your own single-purpose site") parked for later.
- Next session: start building `index.html`.

## Files touched

- `.gitignore` (created)
- `README.md` (created)
- `JOURNAL.md` (created)
- `sessions/README.md` (created)
- `sessions/000-chatgpt-html-preview.md` (created)
- `sessions/001-kickoff-and-strategy.md` (created — this file)
- `KICKOFF.md` (created — paste-ready session-start prompt)
- `README.md` (edited — added `KICKOFF.md` to the "What's where" list)

## Commands run

Step into the project folder and initialize a git repo on the `main` branch:

```bash
cd ~/Documents/Claude/Projects/Like67
git init -b main
```

Stage all scaffolded files and make the first commit:

```bash
git add .
git commit -m "Initial scaffold: README, JOURNAL, sessions skeleton"
```

Create the public GitHub repo, wire it up as the `origin` remote, and push (GitHub CLI):

```bash
gh repo create like67.com --public --source=. --remote=origin --push
```
