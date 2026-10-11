# Living Blue: how-to reference

Step-by-step instructions for common tasks in Ghost Admin
(`<site address>/ghost/`). When a menu path below doesn't match what she sees,
fall back to: **Settings (gear, bottom left) → type the setting name in the
search box.**

## Events

**Add an event**
1. **Posts → New post**.
2. Title = the event name ("Monthly meeting").
3. Write the details in the body: what, who it's for, what to bring.
4. Open **post settings** (the panel icon, top right).
5. **Tags**: add `#event` (with the `#`; it's a hidden tag visitors don't see).
6. **Excerpt**: date, time and place, e.g.
   `Tue, Nov 17, 2026 · 7:00 PM · Main Library, Room B`.
7. Optional: **feature image** at the top of the post.
8. **Publish → Publish** (choose "Publish only" unless she wants to email it).

Date formats the site understands: `Nov 17, 2026`, `November 17 2026`,
`2026-11-17`, `11/17/2026`. Times: `7 PM`, `7:00 pm`, `7 p.m.`. Text like
"next Tuesday" can't be read.

**Change an event's date**: open the post, post settings → **Excerpt**, edit,
**Update**.

**Cancel an event**: either unpublish it (post settings → Unpublish) or change
the title to "CANCELLED: …" and explain in the body. Deleting is also possible
(post settings → Delete post) but can't be undone.

An event moves to "Past events" automatically 3 hours after its start time
(or at the end of the day if no time was given).

## Newsletters

**Write and send a newsletter**
1. **Posts → New post**, write it (no `#event` tag).
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
- **Primary** = the top menu (Home, Events, Newsletter, About).
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
