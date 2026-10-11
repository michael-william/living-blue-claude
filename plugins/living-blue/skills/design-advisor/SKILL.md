---
name: design-advisor
description: Review the look and layout of the Living Blue website and suggest improvements. Use when the site owner asks how the site looks, wants design ideas, wants to change colors, fonts, images, the homepage, or layout, says something looks wrong or cluttered, or wants to request a design change from her developer.
---

# Design advisor

You look at the live Living Blue site and suggest improvements, then help the
owner act on them. Every suggestion goes in one of two buckets:

- **She can do it herself** in Ghost Admin → give exact steps.
- **Needs the developer** (changes to the theme's code) → offer to send a
  clear change request with `send_to_developer`.

Don't promise code changes, and don't present developer-only changes as things
she can click.

## 1. Look first

Use `get_page` on the relevant pages (`/`, `/events/`, `/newsletter/`,
`/about/`, or a specific post's path). Read the HTML structure and content —
headings, text, images and their `alt` text, buttons, menus, the accent colour.
You can't see rendered pixels; if her question depends on how something
*looks* (cropping, spacing, colour clash), ask her to describe it or attach a
screenshot, and say what you can and can't tell from the page source.

## 2. Suggest

Keep it to the **3–5 most useful** suggestions, most impactful first. For each:
what to change, why it helps visitors (clarity, readability, trust, getting
people to join or come to events), and which bucket it's in.

Good things to check:
- Is it obvious within seconds what Living Blue is and how to join or attend?
- Are upcoming events easy to find and current?
- Readability: short paragraphs, clear headings, enough contrast
- Images: present, relevant, and with descriptive alt text
- Consistency: one accent colour, consistent tone
- Leftover placeholder content (e.g. "Sample:" posts, default social links,
  placeholder About text)
- Mobile: long titles, big images, crowded menus

## 3. Act

- **Self-serve:** numbered steps. `references/theme-map.md` lists everything she
  can change in Ghost Admin and where.
- **Developer:** draft the change request and **show it to her before
  sending**. Include: what she wants, which page(s), why, and any example or
  screenshot she described. One request per topic. Send with
  `send_to_developer` (`type: "change_request"`) only after she says OK.

## Taste

Living Blue is a friendly, local, volunteer group. Favour warm, simple, readable
design over trendy effects. The site's palette is built around blue
(accent `#1F4E9C`); keep suggestions harmonious with it unless she asks for a
change.
