# Session 003 — License, hosting, and DNS

**Date:** 2026-04-29
**Goal:** Add a LICENSE file, pick a hosting provider, and get like67.com live on a custom domain.

## Prompts and actions

### 1. Framing the session

> We've got a mockup, we've got documentation, and we've got a github repo. So, we should push the mockup to github, with a license, and then we should figure out who we're using for hosting, that way we can setup DNS. I've already purchased a domain through namecheap, although we probably should have talked about alternatives. If later we make a tutorial, it would be worth mentioning godaddy and dynadot.

Created the session stub at `sessions/003-license-hosting-dns.md`. Reviewed prior session context: licensing had been proposed (CC BY-NC 4.0) but deferred; hosting had been loosely discussed (DigitalOcean) but not decided. Both get resolved this session.

Note for tutorial readers: domain registrar alternatives worth mentioning include GoDaddy and Dynadot. Namecheap is a solid choice; the main thing that matters is where you point the nameservers, not where the domain is registered.

### 2. LICENSE file

Created `LICENSE` at the repo root with CC BY-NC 4.0 terms — permits sharing and remixing for learning, prohibits commercial use, requires attribution. Matches the intent from Session 002: "I don't want someone to copy the code verbatim, but I don't mind them using this as a learning tool."

### 3. First push — git identity warning

> [main 1ae7467] Session 003: add CC BY-NC 4.0 license
> Committer: Stephen Ryherd <steve@Steves-2022-MacBook-Air.local>
> Your name and email address were configured automatically based on your username and hostname.

Git auto-detected an identity from the machine hostname rather than using a configured name and email. This is normal on a fresh machine and is worth flagging for anyone following along — git won't refuse to commit, but the authorship on GitHub will look wrong until you fix it. The fix is two commands:

```bash
git config --global user.name "Steve Ryherd"
git config --global user.email "steveryherd@gmail.com"
```

Then amend the already-made commit to rewrite the author:

```bash
git commit --amend --reset-author
```

### 4. Force push after amend

Amending a commit rewrites its SHA, so the local branch and the remote are now diverged — a regular `git push` is rejected. This is expected behavior, not an error. The fix:

```bash
git push --force-with-lease
```

`--force-with-lease` is safer than bare `--force`: it aborts if anyone else pushed to the branch since your last fetch. Same result for a solo project, better habit in general.

### 5. Hosting decision

> I think that CloudFlare might be the way to go.

Evaluated four options — GitHub Pages, Netlify, Cloudflare Pages, DigitalOcean App Platform — against the needs of a single-file static joke site with a custom domain. Landed on **Cloudflare Pages**: free tier, deploys automatically on every `git push` to `main`, globally CDN-distributed, and the nameserver move to Cloudflare consolidates DNS and hosting in one dashboard.

User already had a Cloudflare account from a prior project (`conversational.work`). Free tier supports unlimited sites, so no conflict.

### 6. Cloudflare Pages setup — Workers vs. Pages wrong turn

During setup, the deploy command field appeared as required with a default of `npx wrangler deploy`. That's the **Workers** flow (Cloudflare's serverless compute product), not Pages. The correct path:

Workers & Pages → Create application → **Pages** tab → Connect to Git

In the Pages flow, all build/deploy fields are optional and can be left blank for a plain HTML site. Cloudflare finds `index.html` at the repo root automatically.

### 7. Auto-deploy confirmed

Cloudflare Pages sets up a GitHub webhook on connect. Every push to `main` triggers a new deploy. Build history in the dashboard shows each deployment with timestamp and commit SHA.

### 8. Site is live

> It looks like the page is now up, at least from what I can see on my machine/network.

like67.com is live on Cloudflare Pages with DNS served through Cloudflare. SSL handled automatically.

Side note on the stack: Namecheap registration + Cloudflare nameservers is a common and stable split — no urgency to change it. Transferring the domain to Cloudflare eventually makes sense (they register at cost, likely cheaper at renewal), but the current setup works indefinitely.

## Files touched

- `LICENSE` (created — CC BY-NC 4.0)
- `sessions/003-license-hosting-dns.md` (this file)

## Commands run

Commit the license and session stub:

```bash
cd ~/Documents/Claude/Projects/Like67
git add LICENSE sessions/003-license-hosting-dns.md
git commit -m "Session 003: add CC BY-NC 4.0 license"
git push
```

Fix git identity (run once, applies globally):

```bash
git config --global user.name "Steve Ryherd"
git config --global user.email "steveryherd@gmail.com"
```

Rewrite the author on the last commit:

```bash
git commit --amend --reset-author
```

Push after the amend (force required because the SHA changed):

```bash
git push --force-with-lease
```
