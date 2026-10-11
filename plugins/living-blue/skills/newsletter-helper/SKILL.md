---
name: newsletter-helper
description: Draft newsletter issues and announcements for the Living Blue website. Use when the site owner wants to write a newsletter, monthly update, recap, announcement, or thank-you post, turn her notes or meeting minutes into a post, or check how past newsletters performed.
---

# Newsletter helper

You turn the site owner's notes into a ready-to-review **draft** newsletter on
the Living Blue site. She reads it, sends herself a test, and sends it to
members from Ghost Admin. **You never send anything.**

## 1. Gather

Ask for (only what's missing):
- What it should cover: her notes, minutes, or a few bullet points are plenty
- Anything to thank people for or announce
- Whether it's for **everyone** or **members only**

Then call `upcoming_events` so the newsletter can include a "Coming up" section
with real dates and links. Call `list_posts` with `kind: newsletters` to see the
previous issue's title and tone if helpful.

## 2. Write

**Voice:** warm, neighborly, and direct, like a note from a friend who keeps the
group organized. Short paragraphs. Plain words. Signed by the group (e.g. "See
you soon, the Living Blue steering committee") unless she says otherwise.

**Structure** (adapt to the content; drop sections that don't apply):

1. Greeting and one-paragraph overview
2. The main news, under short `<h2>` headings
3. **Coming up**: the next few events from `upcoming_events`, each as a list
   item with date and a link to its page
4. How to help / get involved (only real asks she mentioned)
5. Sign-off

**Title** doubles as the email subject: specific and inviting, e.g.
"October newsletter: the final stretch". Add a one-sentence **excerpt** that
previews the issue.

**Facts:** use only what she gave you or what the site shows. This is a
political community group: don't add claims, statistics, dates, or names from
your own knowledge. Where something needs checking, write `[check: …]` and point
it out to her.

## 3. Draft it

`create_draft` with `kind: "newsletter"`, the title, excerpt, and HTML body
(`<p>`, `<h2>`, `<ul>`, `<blockquote>`, `<a>`, `<strong>`). Set
`members_only: true` if she asked. Upload any image with `upload_image` first.

Show her a short summary of what you drafted, then the review link
(`edit_in_ghost`).

## 4. Tell her how to send it (she does this)

1. Open the draft and read it through.
2. **Preview → Email tab → Send test email** to herself. (Check spam: email
   from the site may land there until the developer finishes the email setup.)
3. When happy: **Publish → Publish and email → choose recipients → confirm**.
   Sending can't be undone.
4. To put it on the website without emailing: **Publish only**.

## Edits

Drafts: `update_draft`. Already published or sent: the connector can't change
them; she edits in Ghost Admin (edits change the website, not emails already
sent).

## How did past newsletters do?

`newsletter_stats` gives recipients, deliveries, opens and link clicks for
emailed issues. Explain simply: clicks are the most reliable signal; open
counts may read 0 until the email setup is finished, and even then are
approximate (some email apps block or pre-load images).
