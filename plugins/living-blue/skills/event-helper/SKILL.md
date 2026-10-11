---
name: event-helper
description: Draft events for the Living Blue website. Use when the site owner wants to add, announce, or schedule an event ("add the November meeting", "we're doing a potluck on Dec 13 at 5", "put the phone bank on the site"), change a draft event, or check which events are coming up or have a date problem.
---

# Event helper

Events on the Living Blue site are posts tagged `#event` whose **excerpt**
holds the date, time and place. The website parses that excerpt to sort events
and to show date badges, so getting the format right is the whole job.

## Gather the details

You need: **name**, **date**, **start time** (if any), **place**, and a short
**description**. Ask only for what's missing, in one question. Useful extras:
what to bring, who it's for, whether to RSVP, and an image.

## Check before drafting

- **Year**: if she gives no year, use the next upcoming occurrence of that date
  and say which year you used.
- **Weekday**: work out the weekday for the date yourself and make sure it
  matches what she said. If she says "Saturday the 15th" and the 15th is a
  Sunday, ask which she means. Don't guess.
- **Past dates**: if the date has already passed, check with her before drafting.
- **Duplicates**: call `upcoming_events` (and `list_posts` with `kind: events,
  status: draft` if helpful) to see if this event already exists.

## The excerpt format

Exactly this shape, with ` · ` (space, middle dot, space) between parts:

```
Tue, Nov 17, 2026 · 7:00 PM · Main Library, Room B
```

- Weekday (3 letters), Month (3 letters) Day, Year
- Time as `7:00 PM`; leave the time part out entirely if there isn't one
- Place: short and specific (venue, room, or address)

## Draft it

Call `create_draft` with `kind: "event"`, the title, the excerpt above, and a
body in simple HTML:

- A friendly opening sentence: what it is and why come
- Practical details as a short list (what to bring, parking, accessibility,
  RSVP) — only details she gave you; don't invent any
- If there's an image link, `upload_image` it first and pass the result as
  `feature_image`

The connector refuses an event whose excerpt has no readable date; if that
happens, fix the excerpt and retry.

## Afterwards

Tell her, in this order:

1. It's a **draft**: nobody can see it yet.
2. The link to review it (`edit_in_ghost` from the result).
3. To make it live: **Publish → Publish only** (or **Publish and email** if she
   wants members emailed about it). Remind her that emails can't be unsent.

## Changing events

- **Draft events**: use `update_draft`.
- **Published events**: the connector can't change them (on purpose). Walk her
  through it: open the post in Ghost Admin → post settings → **Excerpt** (for
  date/time/place) or edit the text → **Update**.
- **Checking for problems**: `upcoming_events` lists any events with
  unreadable dates under `unreadable_dates`; offer corrected excerpts for those.

## Never

Publish, email, or delete — the connector can't, and you shouldn't suggest it
did. Don't invent details (times, addresses, speakers) she didn't give you;
leave a clear `[check: …]` placeholder instead and point it out.
