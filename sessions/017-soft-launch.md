# Session 017 — Soft launch

**Date:** 2026-05-04
**Goal:** Stage and execute the soft launch across Show HN, Bluesky, LinkedIn, and r/internetisbeautiful (+ crosspost). Per `ROADMAP.md` Phase 3, this is the moment the artifact stops being private and starts trying to spread. The angle is the placard's story, not the meme.
**Status:** *In progress.*

## Plan

- **Wed May 6, 8:30 AM ET** — Show HN goes live; Bluesky + LinkedIn fire ~30 min later to amplify the first hour
- **Sat May 9, 9:00 AM ET** — r/internetisbeautiful + crosspost to r/coolwebsites
- Drafts staged below as copy-paste blocks; human runs the actual submissions

## Prompts and actions

### 1. Calling the audible to launch

> Alright, magic time. I think that we're ready to "launch". Read through where we are based on the code, the roadmap, etc. Now if we're going to launch, devise a plan, be clear about each step and each goal. If accounts are needed, we can register. Ideally I can also give you some access to Chrome to initiate user creation process, although I can manually do the actual registering/posting where needed to follow terms of service and avoid bot posting.

Read `README.md`, `JOURNAL.md`, `ROADMAP.md`, the latest session (016), and the project context. Confirmed Phase 1 + Phase 2 (sessions 010–016) shipped; the roadmap had soft launch slotted as session 019 after a glossary (017) and template+gallery (018), but Steve called the audible to launch now. Asked four clarifying questions: which channels, which accounts already exist, when to actually post, and how thorough the pre-launch site sweep should be.

### 2. Channel selection

> [Selected: Reddit account already exists; doesn't know what Show HN is; "pick the optimal slot this week"; "quick spot-check"]

Explained Show HN — what Hacker News is, what "Show HN" specifically means, why it's an unusually good fit for an educational artifact, and that a brand-new account works but takes a small ranking penalty. Asked the focused follow-up: include HN or skip; X/Twitter vs. Bluesky/Mastodon/LinkedIn; which subreddits.

> [Selected: include HN, use Bluesky + LinkedIn, r/internetisbeautiful with a crosspost.]

Locked in the channel set: Show HN, Bluesky, LinkedIn, r/internetisbeautiful + crosspost to r/coolwebsites.

### 3. Pre-launch spot-check

Switched to live `like67.com` in Chrome. Animations firing, "How was this made? →" corner link present, mobile/desktop layout intact. Verified `og:` and `twitter:` meta tags in `index.html` (lines 8–17). Checked `opengraph.xyz/url/like67.com` — OG card renders, dark background, "like 6… 7" headline visible. One cosmetic note: opengraph.xyz flags the OG title as 36 chars vs. their 50–60 recommendation; not blocking. Cloudflare Web Analytics is auto-injected (no source-file footprint, by design — see session 010).

### 4. Launch slot decision

> SteveRyherd works, I have a bluesky, I think it's also SteveRyherd. We can go ahead and draft. Not sure which day you would want to time for actual launch.

Recommended **Wednesday May 6, 8:30 AM ET** for HN as the headline event. Reasoning: Tuesday is statistically HN's best day but tonight is Monday — drafting under deadline is a worse trade than sleeping on the copy. Wednesday gets us Tuesday for refinement and the wider US-waking + EU-still-up window. Bluesky thread + LinkedIn fire ~30 min after HN to amplify the first hour. Reddit (IIB + r/coolwebsites crosspost) goes Saturday May 9 morning so the project gets a second peak instead of burning all four channels in one day.

### 5. Stub + draft execution

Created this session file as the stub. Opened `news.ycombinator.com/login` in Chrome for Steve to register the `SteveRyherd` username (no email required). Drafted all five launch posts directly into this session file (Show HN with seeded first comment, r/internetisbeautiful with seeded comment, r/coolwebsites crosspost copy, Bluesky four-skeet thread with character counts noted, LinkedIn long-form post). Drafted the response playbook with nine pre-written replies for predictable launch-day questions.

## Launch copy (drafts)

Each block below is copy-paste ready. Titles obey each platform's posted rules and conventions (HN: no marketing lang; IIB: must describe the page, no editorializing; etc.).

### 1. Show HN — Wed May 6, ~8:30 AM ET

Submit at `news.ycombinator.com/submit`. Show HN posts have their own ranking shelf and convention.

**Title (78 chars):**

```
Show HN: Like67.com – a meme site I built in an afternoon, all prompts in the repo
```

**URL field:**

```
https://like67.com
```

**Text field (HN auto-shows the URL above the text, so don't repeat it):**

```
A single-purpose joke page for the moment when someone says "like 6… 7." That's
the whole site.

I didn't write any code. I built the entire thing — HTML, animations, PWA install,
share image, custom domain, the lot — in one afternoon by typing into a chat with
an AI. Every prompt that produced every line of the site is committed to the repo
verbatim, in order, as the actual record of how it got made:

  Repo:     https://github.com/SteveRyherd/like67.com
  Tutorial: https://like67.com/how-this-was-made-in-6-7-hours/

The point isn't the meme. The point is that this is now a thing a curious 10-year-
old can do. The tutorial is two-column on purpose — plain English on the left, the
actual tools/commands/prompts on the right. The repo is the artifact.

Happy to answer anything about the build, the choices, or the workflow.
```

**Seeded first comment (post immediately after the submission lands, as the OP):**

```
OP here. A couple of things that didn't fit the title:

1. There is no "the AI did 90% and I cleaned up the rest" disclaimer hiding in
   here. I never opened a code editor on this project. The full conversation
   history is in /sessions/, one file per work session, prompt -> action format.
   If something in the codebase looks weird, the prompt that produced it is
   findable.

2. The hosting (Cloudflare Pages), domain (Namecheap), and analytics
   (Cloudflare Web Analytics) total ~$10/year. The build is replicable for the
   price of a domain.

3. Source of the placard / why this exists, in plain English:
   https://github.com/SteveRyherd/like67.com/blob/main/STORY.md
```

---

### 2. r/internetisbeautiful — Sat May 9, ~9:00 AM ET

Submit at `reddit.com/r/internetisbeautiful/submit`. IIB rules: title must describe what's on the page, no first-person, no editorializing, no "check out", no superlatives. Mods are strict. Use the link-post type, not text-post.

**Title (63 chars):**

```
Like67.com — a single-page tribute to the "six seven" meme
```

**URL field:**

```
https://like67.com
```

(IIB is link-post only; no body text. If a comment slot is available, post the seeded comment below from your own account once the submission is live.)

**Seeded first comment (your own account, immediately after submission):**

```
For context: the entire site was built in one afternoon by typing into a chat
with an AI. Every prompt is committed to the repo so the build is fully open:
  https://github.com/SteveRyherd/like67.com
  https://like67.com/how-this-was-made-in-6-7-hours/  (tutorial)
```

---

### 3. r/coolwebsites — Sat May 9, ~9:15 AM ET (15 min after IIB)

Crosspost via Reddit's native crosspost button on the IIB submission. If crosspost is restricted, submit fresh:

**Title:**

```
Like67.com — a single-page tribute to the "six seven" meme, built in an afternoon by chatting with an AI
```

**URL field:**

```
https://like67.com
```

---

### 4. Bluesky — Wed May 6, ~9:00 AM ET (30 min after HN)

Posted as a thread from `@steveryherd.bsky.social` (or whatever your handle is — confirm before posting). Bluesky cap is 300 chars per post.

**Post 1 (the hook — 246 chars):**

```
The first time I edited a website, I was 9. My friend Justin and I right-clicked,
saved the MSN homepage, and started changing it. We didn't know if we were
editing it for everyone or just us. We didn't really care. It felt enormous.

Then the internet got big, and that feeling went away.
```

**Post 2 (Geocities / GameFAQs / MDH — 295 chars):**

```
Geocities. GameFAQs (I was user #1694, "Steve"). The Million Dollar Homepage.
The whole era when one person, alone, could make a thing that mattered to
everyone who showed up. Then three or four companies absorbed most of the
internet, and being a maker on it started to feel like it required a team.
```

**Post 3 (the reveal — 285 chars):**

```
Last week I built like67.com — a single-page brainrot site for when someone
says "like 6… 7." Whole thing in one afternoon. I didn't write a line of code.
I just typed into a chat with an AI: "make this," "fix that," "now add
animations." Every single prompt is committed to the repo.
```

**Post 4 (the thesis + link — 257 chars):**

```
The point isn't the meme. The point is that this is something a curious
10-year-old can now do. The leveling of the playing field isn't a metaphor —
it's a chat window. Your idea is enough to start.

The site:    like67.com
How it was made: like67.com/how-this-was-made-in-6-7-hours/
```

---

### 5. LinkedIn — Wed May 6, ~9:00 AM ET (single post, posted right after HN)

Long-form post. LinkedIn rewards posts that read like a story. The opening line is what shows in the feed before "see more" — make it earn the click.

```
The first website I ever edited, I was nine years old, and I didn't actually know
what a website was.

My friend Justin showed me you could right-click, save a page, and then change
it. We spent an afternoon editing the MSN homepage on his dad's computer. We
genuinely didn't know if we were changing it for everyone or just for us. We
didn't care. It felt enormous.

That feeling — that one person could just make a thing on the internet, and it
might matter — built whole eras of the web. Geocities. GameFAQs. The Million
Dollar Homepage. Then the internet got smooth, and it got owned, and "make a
thing" started to require money or a team or years of skills.

Last week I made a website called like67.com.

It's a joke. A single page for the brainrot moment when someone says "like
6… 7." (If you have kids over the age of about seven, you know.) The whole
thing — HTML, animations, share-card image, install-as-an-app for phones,
custom domain, hosting — was built in a single afternoon. I did not write a
line of code. I just typed into a chat with an AI: describe what I wanted,
describe what was wrong, describe what I wanted next. Every prompt I sent is
committed to the public repo, in order, as the actual record of how it got made.

The reason I'm sharing it is not the joke. It's this:

The thing my nine-year-old self felt — that you could just make something on
the internet — is back. Talking to an AI is the new "View Source." A curious
kid with an idea and an afternoon can now ship a real, live website to a real
domain. No gatekeeper. No team. No fundraising round.

That is, I think, the most underrated story of this moment in technology.

I built a tutorial alongside the site that walks through the whole build in
plain English, written for a kid as much as a developer:
👉 like67.com/how-this-was-made-in-6-7-hours/

The site itself: 👉 like67.com

If you have a kid in your life who's curious about how the internet works —
this is for them. Show them. The barrier to entry just collapsed.

#AI #BuildingInPublic #Education #IndieWeb
```

## Mom Test — pre-launch sanity check on the LinkedIn draft

Send the LinkedIn draft to 1–3 trusted readers tonight or Tuesday so you've got at least one outside read before Wednesday morning. The HN, Bluesky, IIB, and crosspost copy are platform-shaped enough that they don't really need this — but the LinkedIn post is long-form, professional-network-facing, and lifts directly from `STORY.md`, so it's the one most worth a second pair of eyes.

### Picking the readers

Aim for *different* readers, not similar ones. The fastest way to dilute the test is to send it to three friends who all think the same things you think. Two solid picks:

1. **One person who would never use the word "AI" in conversation.** Parent, neighbor, in-law, non-technical coworker. They'll catch jargon you've gone blind to.
2. **One person whose LinkedIn presence you respect.** Someone whose own posts you read without wincing. They'll catch the "is this cringe on this specific platform" question.

Optional third: **a developer or builder.** They'll catch any technical claim that's overstated.

### The ask (DM-friendly, ~150 words)

```
Hey — quick favor. I'm about to post this on LinkedIn on Wednesday morning
and I want to make sure it doesn't read weird before it goes live.

Two questions, that's all:

  1. Does the opening line make you want to keep reading, or does it land
     as "humble-brag founder post"?
  2. Anywhere in the body that sounds preachy, or that you'd skip past?

Don't proofread it. Don't try to improve it. I just need a gut read on
those two things. 60 seconds is plenty — first reaction is what I want.

Draft below. Thank you 🙏

──

[paste the LinkedIn draft from this session file here]
```

Why those two questions specifically: opening lines are the LinkedIn equivalent of a cold open, and "preachy" is the failure mode for any post built around an "AI is changing everything" thesis. If both come back clean, ship it. If either gets a wince, the fix is usually a one-line surgical edit, not a rewrite.

### If you don't get a response by Tuesday night

Fire cold Wednesday morning anyway. The project's edit history is public; if a phrase ages badly, you can revise the LinkedIn post (LinkedIn allows post-publish edits) without breaking anything. The cost of waiting another week is bigger than the cost of one slightly-clunky line.

## Response playbook

Pre-written replies for the questions most likely to come up. Think of these as starting points; tone-match the platform on the day. None of these are auto-replies — only post them when an actual question matches.

### "Did you really not write any code?"

```
Correct. There is no hidden code editor in this story. I drove the whole project
by typing into a chat — describing what I wanted built, what was broken, what to
change. The AI wrote, edited, and ran every line. The /sessions/ folder in the
repo has the full conversation, prompt by prompt, in the order it happened. If
something looks wrong in the code, the prompt that produced it is findable.
```

### "What about the icons / OG image / scripts you generated? That's still code."

```
Fair. The OG share image was generated by a Python + Pillow script the AI wrote
on the fly (session 011 in the repo). I ran it; I didn't write it. Same for the
PWA icons (session 007). I'm counting "I didn't write code" as "I didn't compose
the source files myself" — which is the part that used to be the gatekeeper for
non-developers.
```

### "Why CC BY-NC and not MIT / public domain?"

```
The site is meant as an educational artifact. CC BY-NC lets anyone learn from
it, fork it, remix it, teach with it — but it stops someone from selling
"like67-clones for hire" on Fiverr without my involvement. If a teacher wants
to use it in a class, they're explicitly welcome.
```

### "What is COPPA / why does it matter here?"

```
COPPA is the US law that restricts data collection from kids under 13. The
site has zero login, zero forms, no third-party trackers, and uses
Cloudflare's cookie-free analytics. That's deliberate — the implied audience
is kids, and I want it to be a place a parent can hand over without thinking.
```

### "Who is Audrey Burns?" (the easter egg)

```
A real kid. Long-press anywhere on the page for ~600ms and you'll see "for
Audrey Burns 🏀" pop up. She loves basketball and the six-seven meme. The
site is, in a small way, for her.
```

### "What does 'brainrot' mean / what's the six-seven meme?"

```
"Brainrot" is Gen Alpha slang for short-form-video humor that adults find
incomprehensible. "Six seven" is a phrase from a viral TikTok / song that kids
have been saying constantly for months. The site is a single-purpose page for
the moment when one of them yells it. That moment is its only function.
```

### "How much did this cost to build?"

```
~$10/year for the domain (Namecheap). Hosting (Cloudflare Pages), HTTPS,
analytics, and the GitHub repo are all on free tiers. The AI subscription I
already had. The build itself was ~6-7 hours of focused chat over an afternoon.
```

### "Could a kid actually do this?"

```
That's the thesis. The tutorial at /how-this-was-made-in-6-7-hours/ is written
two-column — plain English on the left, the actual tools/commands/prompts on
the right. The hard part isn't the technical work anymore; it's knowing the
chat is willing to do it. That's what the project is trying to demonstrate.
```

### "Which AI did you use?"

```
Claude (Anthropic), specifically the Cowork desktop app, which gives the AI
read/write access to a project folder. The same workflow would work in
ChatGPT, Gemini, or any chat that can produce files — the prompts in the
repo are not Claude-specific.
```

### "What's next?"

```
A glossary, a fork-able template ("make your own joke site"), and eventually
a curated sponsor mechanic in the spirit of Million Dollar Homepage —
moderated to stay COPPA-clean. Roadmap is in the repo.
```

## Files touched

- `sessions/017-soft-launch.md` (created — stub + plan + drafts + playbook)
- `JOURNAL.md` (session 017 entry appended)
- `sessions/README.md` (017 added to index)
- `ROADMAP.md` (Phase 3 status updated — 017 reframed from "glossary" to "soft launch"; original 019 absorbed)

## Commands run

```bash
git add -A
git commit -m "Session 017: soft launch — staged copy and response playbook"
git push
# verify on preview.like67-com.pages.dev (this session is docs-only — no live-site changes), then:
git checkout main
git merge preview
git push
git checkout preview
```

## Launch-day commands (Wed May 6)

Open these in Chrome about 5 minutes before 8:30 AM ET. Each opens a fresh submission form already preloaded with the URL where supported.

```
https://news.ycombinator.com/submit
https://bsky.app/
https://www.linkedin.com/feed/?shareActive=true
```

Then on Sat May 9, ~9:00 AM ET:

```
https://www.reddit.com/r/internetisbeautiful/submit
https://www.reddit.com/r/coolwebsites/submit
```
