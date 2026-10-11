---
name: site-checkup
description: Check the Living Blue website for problems and loose ends. Use when the site owner asks for a checkup, health check, review, "is everything OK on the site", "what needs fixing", or before sharing the site with the group or sending a newsletter.
---

# Site checkup

A read-only look over the Living Blue site that ends in a short, friendly to-do
list. **Change nothing during the checkup.** Afterwards, offer to help with
items — drafts via the other skills, self-serve steps, or a request to the
developer.

## Run these checks

1. **Overview**: `site_overview`. Note member count and how many drafts exist.
2. **Events**: `upcoming_events`.
   - Any under `unreadable_dates`? → needs a fixed excerpt (give the corrected
     text, e.g. `Tue, Nov 17, 2026 · 7:00 PM · Main Library`).
   - No upcoming events at all? → the homepage shows "No upcoming events yet";
     suggest adding the next one.
   - Next event more than ~6 weeks away? → mention it.
3. **Drafts**: `list_posts` with `status: draft`. Drafts untouched for 30+ days
   (`updated_at`) → publish or delete? (She does either in Ghost Admin.)
4. **Published content**: `list_posts` with `status: published`, `limit: 50`.
   - Titles starting **"Sample:"** or the default **"Coming soon"** post →
     leftover demo content to delete before sharing the site.
   - Newsletters/posts with no excerpt → cards on the homepage show the first
     words of the post instead; usually fine, mention only if many.
5. **Homepage**: `get_page` with `/`.
   - Footer social links pointing at `facebook.com/ghost` or `x.com/ghost` →
     Ghost placeholders; set the group's own in Settings → Social accounts, or
     clear them.
   - Site description still "Thoughts, stories and ideas" (Ghost's default)?
6. **About page**: `get_page` with `/about/`. Text containing "[Sample text" →
   placeholder still in place.
7. **Newsletter stats** (only if newsletters have been emailed):
   `newsletter_stats` — note anything unusual, like many recipients but 0
   deliveries (a sending problem → offer a help request to the developer).

## Report

Lead with a one-line verdict ("Looking good — 3 small things to tidy"). Then a
checklist grouped as:

- **Fix before sharing** (things visitors would notice)
- **Nice to do**
- **All good** (one line listing what passed)

For each item: what's wrong, in plain words, and the fix — clickable steps if
she can do it herself, or "I can draft this for you" / "this one is for your
developer". Keep it short; no technical detail unless she asks.

## Things that are expected (don't flag as problems)

- **Paid membership not set up**: a pending group decision.
- **Email may land in spam / open counts show 0**: known email-setup item
  for the developer.
- **No visitor statistics in Ghost**: planned for later (Cloudflare analytics).
