# living-blue plugin

Skills for running the Living Blue community website (Ghost 6, theme
`living-blue`). Setup instructions for the site owner are in the
[repository README](../../README.md).

In Claude Code:

    /plugin install living-blue --marketplace michael-william/living-blue-claude

| Skill | Use it for |
|---|---|
| `site-guide` | How-to questions about this specific site; what it can and can't do |
| `event-helper` | Drafting events in the site's `#event` + excerpt-date format |
| `newsletter-helper` | Drafting newsletter issues from notes; explaining how to send |
| `design-advisor` | Reviewing pages and sorting suggestions into self-serve vs developer |
| `site-checkup` | A read-only health check that ends in a short to-do list |

## Connector tools (the "Living Blue" custom connector)

`site_overview`, `list_posts`, `upcoming_events`, `get_post`, `create_draft`,
`update_draft`, `upload_image`, `newsletter_stats`, `get_page`,
`send_to_developer`.

The connector is deliberately limited: it creates and edits **drafts only**,
never publishes, sends, or deletes, and exposes member **counts** only. The
skills repeat these limits so Claude explains them correctly.

Without the connector the skills still answer questions, but can't read the
site or create drafts.
