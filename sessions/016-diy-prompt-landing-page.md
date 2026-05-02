# Session 016 — DIY prompt and "how it was made" landing page

**Date:** 2026-05-02
**Goal:** Distill the full build into a copyable AI prompt for beginners, then ship it as a proper landing page that layers depth for different readers.

## Prompts and actions

### 1. Designing the super-prompt

> If we wanted to consolidate every single one of the sessions we've had so far and turn it into a tutorial or streamlined experience for a beginner. What kind of "prompt" could we give to an absolute complete amateur to paste into an AI to walk them through creating a website? If we wrote a tutorial on how to make our own page, they'd need to get to an LLM, but then if our prompt was carefully crafted to tell the LLM how to behave to walk them through everything from file creation, to dns, and domain registration, and even if their LLM supports writing to system or doing browser actions for them, asking them for permissions to do this for them and automating the process.

Reviewed all sixteen sessions to extract the actual build journey. Drafted a standalone prompt covering behavior rules (one step at a time, plain English first, copy-paste-ready commands, capability detection, checkpoints, jargon with definitions), a description of what gets built (single HTML file on Cloudflare Pages with a custom domain), four upfront clarifying questions, and seven named phases: accounts/tools, HTML, git+GitHub, Cloudflare Pages, custom domain+DNS, preview branch, done. Baked in two hard-won lessons from the sessions: the Cloudflare Workers-vs-Pages wrong turn (called out in Phase 4), and the git identity gotcha (moved into Phase 1 where it belongs). Flagged capability detection as the key design insight — the same prompt works in Claude, ChatGPT, Gemini, or anything else because the AI self-reports what it can automate before starting.

### 2. Shipping it as an HTML page

> What about if I wanted to ship that as another HTML page to go along with the tutorial? Basically as a "I don't want to hear the history, I don't want to see your commands, I just want to DIY". Plop it in as a link in the description, the sidebar, etc. Match the styling of the tutorial page, but keep it a separate document.

Created `make-your-own/index.html` matching the tutorial's full design system — CSS variables, topbar, 240px sidebar + main grid, font stacks, color palette. Sidebar listed prompt phases; main column had a "you'll end up with" teal callout, an amber "you don't need anything to start" note, and the prompt in a dark scrollable terminal-style box with a copy button (clipboard API with text-selection fallback, green "Copied!" feedback). Added a `make your own →` link (in the pink link color) to the tutorial's sidebar footer-link block.

### 3. Restructure as a landing page; fix sidebar; beginner-friendly language

> Those [sidebar links] are all jump links, they really should just be a bulleted list rather than links. This is what we should have as the landing page for "how it was made" — if someone wants to dive deeper we can link to the deeper page. On this page "repo on GitHub →" should be "View the code (via github.com)!" or something a little more beginner friendly. This page is going to typically have a 8-13 year old reader. Layer 1 is web page, Layer 2 is distilled AI prompt, Layer 3 is a walkthrough of how we built the site, Layer 4 is links to the saved transcripts from our sessions, Layer 5 is the raw code on github.

Rewrote the page from the ground up to serve as the "how it was made" entry point:

- Topbar: "how it was made" (was "make your own")
- Sidebar phases: removed `<a>` tags entirely, plain `·` bullet list in CSS, no hover states
- Sidebar added a second "Go deeper" section — a linked `layers-list` with the current page highlighted in pink
- Main intro: rewritten for an 8–13 year old, plain language, no jargon, starts with "This whole site was built by typing into a chat with an AI"
- New **layer nav** — a five-row table (numbered 1–5) showing "how far do you want to go?": site → this page (you're here) → full walkthrough → actual conversations → raw code. Each row has a short plain-English description and a link or "you're here" badge
- "Make your own" demoted to a named subsection below the landing page content
- All GitHub links relabeled to "view the code (on github.com)"

### 4. Footer credits

> Code & words © Steve Ryherd, licensed CC BY-NC 4.0 (link). Made with ♥ by Steve Ryherd (link to steveryherd.com) 2026. Let's have that on both the tutorial pages.

Tutorial page already had the license line — added "Made with ♥ by Steve Ryherd 2026" to it. Make-your-own page had a bare one-liner — replaced with a two-line footer matching the tutorial: first line links back to the site/walkthrough/GitHub, second line has the CC BY-NC 4.0 license and the ♥ credit.

## Files touched

- `make-your-own/index.html` (created)
- `how-this-was-made-in-6-7-hours/index.html` (added "make your own →" to sidebar; added "Made with ♥" to footer)
- `sessions/016-diy-prompt-landing-page.md` (this file)
- `JOURNAL.md` (session 016 entry appended)

## Commands run

```bash
git add -A
git commit -m "Session 016: DIY prompt and make-your-own landing page"
git push
# verify at preview.like67-com.pages.dev/make-your-own, then:
git checkout main
git merge preview
git push
git checkout preview
```
