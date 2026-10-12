# Living Blue: how-to reference

Step-by-step instructions for common tasks in Ghost Admin
(`<site address>/ghost/`). When a menu path below doesn't match what she sees,
fall back to: **Settings (gear, bottom left) → type the setting name in the
search box.**

## Events

Events are managed on the website itself, not in Ghost Admin. You need to be
signed in to the site as a member with the **Organizer** label.

**Make someone an organizer** (including yourself): Ghost Admin → **Members** →
open the person (add yourself as a member first if needed) → **Labels** → type
`Organizer` → **Save**.

**Add an event**: on the site, **Events → Manage events** (or go to
`/events/manage/`). Fill in the title, date, times, place and details, choose
**Published** (or **Draft** to finish later) and click **Add event**.

**Change or cancel an event**: on **Manage events**, click **Edit**, or
**Cancel event**. A cancelled event stays on the list, marked cancelled, so
people who signed up see it. **Delete** only appears while nobody has signed up.

**See who's coming**: on **Manage events**, click the "… people going" line
under an event. **Email everyone who signed up** opens an email to all of them.

An event moves to "Past events" when it ends (3 hours after the start if no
end time is given, or at the end of the day for all-day events).

## Newsletters

**Write and send a newsletter**
1. **Posts → New post**, write it.
2. Optional: tag `Newsletter`.
3. **Send yourself a test first**: **Preview** (top right) → **Email** tab →
   **Send test email**. Check spam if it doesn't arrive.
4. **Publish** → choose **Publish and email** → pick who receives it → confirm.

Sending can't be undone, so the test email matters.

**Post on the site without emailing**: **Publish → Publish only**.

## Members-only content

Post settings → **Post access** → *Members only*. Visitors see a prompt to join
instead of the content.

## Homepage and look

- **Headline on the homepage banner**: Settings → search "Design" (Design & branding) →
  **Customize** → **Homepage** → *Hero headline*.
- **Text under the headline**: Settings → **Title & description** → *Site
  description*.
- **Banner background image**: Settings → **Design** → Customize → **Brand** →
  *Publication cover*.
- **Logo, site icon, accent colour**: Settings → Design → Customize → **Brand**.
- **Fonts**: Design → Customize → *Title font* / *Body font* (Modern sans-serif
  or Elegant serif).
- **Header layout**: Design → Customize → *Navigation layout*.

## Menus

Settings → search "Navigation".
- **Primary** = the top menu (Home, Events, Newsletter). Visitors who aren't signed in don't see it.
- **Secondary** = the footer menu.
Signed-in members automatically don't see "Sign up" links.

## Social links in the footer

Settings → search "Social accounts" → set the group's Facebook / X pages, or
clear them to hide the icons.

## About page

**Pages → About** → edit → **Update**.

## Staff (people who can manage the site)

Settings → search "Staff" → **Invite people** → enter email → choose a role:
- **Administrator**: everything, including settings.
- **Editor**: write, edit and publish anyone's posts; invite authors.
- **Author**: write and publish their own posts.
- **Contributor**: write drafts only; someone else publishes.

## Members

**Members** (left sidebar) shows everyone who joined. From there she can add a
member by hand, search, or export a list. (The Claude connector intentionally
sees only counts.)

## Comments

Members can comment at the bottom of posts. To turn comments off or limit
them: Settings → search "Comments".

## Not set up yet

- **Paid dues** (needs Stripe; a group decision).
- **Visitor statistics** (planned: Cloudflare Web Analytics). Newsletter stats
  (sent, clicks) already work in Ghost; open counts will start working once the
  developer finishes the email setup.
