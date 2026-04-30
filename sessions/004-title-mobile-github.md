# Session 004 — Title, mobile layout, GitHub link

**Date:** 2026-04-29
**Goal:** Fix the link-preview title, add Open Graph meta tags, fix iOS viewport clipping, and add a subtle GitHub link.

*In progress.*

## Prompts and actions

### 1. Planning

> We have a live website now. There's features and bug fixes I'd like to go through. First, when sending a link through iPhone, the title of the page is "6 7 meme chaos". I think that we need to come up with a much better title than that. Something that doesn't seem accidentally cringe. Next, I think it may be worth adding a small link to the GitHub page. On an iPhone the "six seven six seven" words are cut off below the screen, and the spiral of colors ends prematurely too at the top of the page. It would also be nice if this was an "installable" website, when saved to the desktop. But I think with app icons and all of that, that might be a separate session. Create a plan for how we should session these changes.

Scoped the session: title + OG tags, GitHub link, and iOS layout bugs all land in 004 since they're single-file HTML changes. PWA / installable deferred to Session 005 (needs icon design decisions first).

### 2. Staging branch + preview.like67.com

> I agree, let's start 004. I trust you to create the changes, it looks like Cloudflare has some sort of way to create staging branches? Maybe we could have a preview.like67.com for testing stuff before pushing?

Cloudflare Pages automatically builds every branch push and assigns it a preview URL at `[branch].[project].pages.dev`. To get `preview.like67.com` pointing at a dedicated branch, the steps are:

1. Create and push a `preview` branch locally.
2. In Cloudflare Pages → your project → Custom domains → Add a custom domain → enter `preview.like67.com` → scope it to the `preview` branch.

Commands to set up the branch (run once):

```bash
cd ~/Documents/Claude/Projects/Like67
git checkout -b preview
git push -u origin preview
```

After that, all session work happens on `preview`, and merging to `main` is what deploys to production.

### 3. Changes to index.html

Four problems fixed in one pass:

**Title:** `6 7 Meme Chaos Animation` → `like 6… 7`  
Self-referential, reads as the joke, not accidentally cringey.

**Open Graph tags:** Added `og:title`, `og:description`, `og:url`, `og:type`, and `twitter:card` so iMessage and social link previews render something intentional.

**iOS viewport clipping:** The root cause is that iOS Safari's `100vh` is calculated against the full document height (before browser chrome collapses), so the stage overflows and body's `overflow: hidden` clips the top of the conic gradient and pushes the chant below the visible area. Fixed by layering `100dvh` (dynamic viewport height, supported iOS 15.4+) over the `100vh` fallbacks on both `body` and `.stage`.

**GitHub badge:** Small fixed icon in the bottom-right corner, low opacity at rest, lights up on hover. Stays out of the way visually but gives curious visitors a path to the source.

## Files touched

- `index.html` (title, meta tags, dvh fix, GitHub badge)
- `sessions/004-title-mobile-github.md` (this file)

## Commands run

Set up the preview branch (run once before pushing this session's changes):

```bash
cd ~/Documents/Claude/Projects/Like67
git checkout -b preview
git push -u origin preview
```

Commit and push session changes to `preview`:

```bash
git add index.html sessions/004-title-mobile-github.md
git commit -m "Session 004: title, OG tags, iOS viewport fix, GitHub badge"
git push
```

When satisfied on `preview.like67.com`, merge to main to deploy:

```bash
git checkout main
git merge preview
git push
git checkout preview
```
