---
name: site-editor
description: Change how the Living Blue website looks or is laid out by editing its theme, seeing each change on the test site (staging) within seconds, then sending it to the developer for review. Use when the site owner wants to change a page's layout, wording built into the design, spacing, card styles, the homepage sections, or anything design-advisor marks as "theme code"; when she asks to "start editing", "work on the test site", "send my changes for review", "I'm done with my change"; or when she needs to set up editing on her Windows computer.
---

# Site editor

The owner can change the site's design herself. She works in **Claude Code**
(the **Code** tab of the Claude app) on her own copy of the site's code. Each
edit shows up on the **test site** a few seconds later. When she's happy, the
change goes to her developer as a **pull request**; the real site changes only
after the developer approves and merges it.

Words to use with her: "the test site" (staging), "your change" (a branch),
"send it for review" (open a pull request). Avoid git jargon unless she asks.

## Where are we?

- **In a regular chat** (no access to her files, no terminal): you can't edit
  the code from here. Explain the flow in two sentences and tell her to open
  the **Code** tab, choose her `living-blue` folder, and ask the same thing
  there. If she hasn't set it up yet, walk her through
  `references/windows-setup.md`.
- **In Claude Code inside the `living-blue` folder:** the repository's
  `CLAUDE.md` has the exact procedure and the hooks enforce the rules. Follow
  it. The summary below is for orientation.
- **In Claude Code but no `living-blue` folder or not set up**: use
  `references/windows-setup.md`.

## The flow (details in the repo's CLAUDE.md)

1. **Is it really code?** Colours, logo, cover image, menus, the homepage
   headline, the About text and social links are **settings on the real site**
   (Ghost Admin), not code; see the design-advisor skill's theme map. Send her
   there instead; it's faster and needs no review.
2. **Start**: a fresh change from `main` (`edit/<topic>`), then
   `tools/lb-dev start` to take the test site.
3. **Edit in small steps.** After each edit the test site updates by itself;
   tell her exactly where to look and wait for her reaction.
4. **Save progress**: commit and push her change now and then, so nothing is
   lost if her computer has a bad day.
5. **Done**: list what the change does, open the pull request with a clear
   description, `tools/lb-dev end`, and tell her the developer will review it.

## Setting expectations

- The test site has **fake** members, posts and events, and its own password.
  After the password she signs in as a member with her own email address; the
  sign-in link arrives in her real inbox (the developer has to allow her
  address once). If no link arrives, offer to email the developer.
- Only **one person** can use the test site at a time. If it's busy, say who
  is using it and suggest trying later.
- Some things **can't be changed here** and need the developer: the events
  calendar's behaviour, RSVPs, sign-up handling, emails, new add-ons or
  packages. Offer to describe what she wants in the pull request, or (in a
  regular chat) send it with `send_to_developer`.
- The real site does **not** change until the developer merges. Never say
  something is "live" when it's only on the test site.

## When things go wrong

- "Staging NOT updated" after an edit: the edit had a mistake that the
  automatic check caught. Fix it before telling her to look; the test site
  keeps showing the last good version meanwhile.
- "Could not reach" the test site: her internet, or the test site is down.
  Try again in a minute; if it persists, offer to email the developer.
- Lost or confused about where she is: run `git status` and
  `tools/lb-dev status`, then explain in one or two sentences.
