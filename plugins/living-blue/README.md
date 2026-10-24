# living-blue plugin

Skills for running the Living Blue community website (Ghost 6, theme
`living-blue`). Setup instructions for the site owner are in the
[repository README](../../README.md).

In Claude Code:

    /plugin install living-blue --marketplace michael-william/living-blue-claude

| Skill | Use it for |
|---|---|
| `site-guide` | How-to questions about this specific site; what it can and can't do |
| `event-helper` | Adding draft events to the members-only calendar, e.g. from the monthly calendar document |
| `newsletter-helper` | Drafting newsletter issues from notes; explaining how to send |
| `design-advisor` | Reviewing pages and sorting suggestions into settings, theme code, or developer |
| `site-editor` | Editing the theme in Claude Code with live preview on staging, then a PR for review; Windows setup |
| `site-checkup` | A read-only health check that ends in a short to-do list |

## Connector tools (the "Living Blue" custom connector)

`site_overview`, `list_posts`, `list_events`, `create_event`, `update_event`,
`get_post`, `create_draft`, `update_draft`, `upload_image`, `newsletter_stats`,
`get_page`, `send_to_developer`.

`site-editor` doesn't use the connector: it works in Claude Code inside a clone
of the private site repo, whose `CLAUDE.md` and hooks hold the procedure and the
guardrails (see that repo's README, "Live editing on staging").

The connector is deliberately limited: it creates and edits **drafts only**,
never publishes, sends, or deletes, and exposes member **counts** only. The
skills repeat these limits so Claude explains them correctly.

Without the connector the skills still answer questions, but can't read the
site or create drafts.
