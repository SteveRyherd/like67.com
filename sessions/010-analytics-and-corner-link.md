# Session 010 — Analytics and corner-link rewrite

**Date:** 2026-04-30
**Goal:** First Phase 1 build session. Wire up Cloudflare Web Analytics (cookie-free, COPPA-safe) so the maintainer can finally see whether anything is working, and replace the bottom-right GitHub icon with inviting copy that invites a click.

---

## Prompts and actions

### 1. Kickoff

> Let's do session 010. I'm ready to turn on some analytics on Cloudflare. Process the normal suggestions as well as the previous session to pick up where we've left off.

Read `README.md`, `JOURNAL.md`, `sessions/README.md`, `sessions/009-strategy-and-roadmap.md`, and `ROADMAP.md`. Confirmed session 010's scope per the roadmap: Cloudflare Web Analytics + corner-link rewrite. Created the session stub at `sessions/010-analytics-and-corner-link.md`.

### 2. Corner-link rewrite

Picked "How was this made? →" over "Make your own →" — it points at the *artifact* (the story), which fits the placard work coming in session 012. "Make your own" works better once the template exists in Phase 2.

Replaced the `.gh-link` GitHub icon in `index.html` with a `.corner-link` text element. Styled it to match the typography of the existing fullscreen and home-screen hints — same `system-ui` font, same 11px size, same `letter-spacing: 0.05em`, same `rgba(255,255,255,0.3)` resting opacity, same brighten-to-`0.85` on hover. All three bottom-corner labels now read as one family.

### 3. Cloudflare Web Analytics — setup walkthrough

Surfaced the dashboard steps for the human: sign in to Cloudflare, **Analytics & Logs → Web Analytics**, **Add a site** with `like67.com`, ask for **Manual setup** so the snippet is visible in the repo (educational-artifact angle: a reader can see what's being tracked), then paste the `<script>` back so it could be added before `</body>`.

### 4. Auto-inject instead of manual

> I wasn't given a choice, it did "automatic setup". It went right to Automatic setup. Looks like it's auto injecting that script for us.

Cloudflare auto-detects Pages projects and skips the manual-snippet flow. Accepted auto-inject — it works, every Pages route gets the beacon, and Cloudflare can update the script without a repo change. Documented the small trade-off: the analytics tag isn't visible in `index.html`, so a reader of the source doesn't see what's being tracked. If we ever want that visibility, the Web Analytics site settings have a toggle to switch from "automatic by Cloudflare Pages" to manual.

No code change for analytics this round — turning it on in the dashboard was the entire delivery. Beacon appears at `https://static.cloudflareinsights.com/beacon.min.js` once Cloudflare finishes propagating.

---

## Files touched

- `index.html` — `.gh-link` (with the inline GitHub SVG) replaced with a `.corner-link` text anchor reading "How was this made? →". Hover and resting colors carried over from the icon.
- `sessions/010-analytics-and-corner-link.md` — this file.
- `JOURNAL.md` — session 010 entry added.

## Commands run

The only environment-changing step this session was enabling Web Analytics in the Cloudflare dashboard (no command, just the UI). The analytics tag is auto-injected by Cloudflare Pages, so there's no script to add to the repo.

```bash
# (run on the preview branch)
git add -A
git commit -m "Session 010: Corner link rewrite; Cloudflare Web Analytics enabled"
git push
# check preview.like67-com.pages.dev for the new corner link, then:
git checkout main
git merge preview
git push
git checkout preview
```
