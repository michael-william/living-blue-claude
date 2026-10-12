---
name: event-helper
description: Add events to the Living Blue website's members-only calendar. Use when the site owner wants to add, announce, or schedule events ("add the November meeting", "we're doing a potluck on Dec 13 at 5", "here's this month's social calendar"), change a draft event, or check what's coming up and how many people signed up.
---

# Event helper

Events on the Living Blue site are **not Ghost posts**. They live in the site's
own events calendar, which only signed-in members can see at `/events/`.
Members click **I'm going** (with an optional number of guests), add events to
their own calendar, or subscribe to the whole calendar.

You add events as **drafts**. An organizer (a member with the **Organizer**
label in Ghost) reviews and publishes them on the **Manage events** page
(`/events/manage/`, also linked from the Events page). That's also where
organizers edit published events, cancel them, and see who's coming.

## Gather the details

For each event you need: **title**, **date**, and usually a **start time**
and **place**. Optional: end time, details for members (what to bring, cost,
contact person), and a limit on places. Ask only for what's missing, in one
question.

## The monthly calendar document

She may paste or attach the group's monthly social calendar (a Word document
or PDF). Read every event from it, then:

1. Show her a short table of what you found (date, time, title, place) and ask
   her to confirm before adding anything. Flag anything unclear.
2. Call `list_events` with `scope: "all"` and skip events that already exist
   (same title and date).
3. Call `create_event` once per event.

## Check before adding

- **Year**: if none is given, use the next upcoming occurrence and say which.
- **Weekday**: work out the weekday yourself. If she says "Saturday the 15th"
  and the 15th is a Sunday, ask. Don't guess.
- **Past dates**: check with her first.
- **Times**: the connector takes 24-hour times in Central time (`18:30` for
  6:30 PM). Leave `start_time` out for an all-day event.

## Afterwards

Tell her:

1. The events are **drafts**: members can't see them yet.
2. To publish: open `/events/manage/` on the site (signed in as a member with
   the Organizer label) and click **Publish** on each one.
3. Once published, members can sign up straight away.

## Changing events

- **Drafts**: `update_event` with the event's id from `list_events`.
- **Published events** (date change, cancellation): the connector can't change
  them, on purpose. An organizer uses **Edit** or **Cancel event** on the
  Manage events page. Cancelling keeps the event visible, marked cancelled, so
  people who signed up can see it.
- **Who's coming**: `list_events` gives the number of people signed up per
  event. Names are only on the Manage events page; the connector never sees them.

## Organizers

Anyone who should manage events needs (1) a member account and (2) the label
**Organizer** on it: Ghost Admin → **Members** → open the person → **Labels** →
type `Organizer` → **Save**. The site owner needs this on her own member
account too (being the Ghost owner isn't enough).

## Never

Publish, cancel or delete events: the connector can't, and you shouldn't
suggest it did. Don't invent details (times, addresses, costs) she didn't give
you; leave a clear `[check: …]` placeholder in the details and point it out.
