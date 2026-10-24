# Living Blue: Claude helper

This adds a set of helpers to **Claude** so it can help you run the Living Blue
website: answer "how do I…?" questions, write drafts of events and newsletters,
suggest design improvements, and check the site for loose ends.

## What you need

- The **Claude desktop app** (or claude.ai in a browser), signed in
- A **Pro** plan or higher (plugins aren't available on the free plan)
- The **connector address** your developer sent you privately. It's a long web
  address. Treat it like a password: don't share or post it.

## Setup (about 5 minutes, once)

### 1. Add the Living Blue helpers

1. In Claude, click **Customize** in the left sidebar.
2. Open the **Plugins** tab.
3. Click **Add**, then **Add marketplace**, then **Add from a repository**.
4. Paste this and confirm:
   `michael-william/living-blue-claude`
5. Go to the **Discover** tab, find **living-blue**, and click **Add**.

### 2. Connect Claude to the website

1. Still in **Customize**, open **Connectors**.
2. Click **Add custom connector**.
3. Name: `Living Blue`
4. URL: paste the connector address from your developer.
5. Click **Add**. If Claude asks about permissions, allow it.

### 3. Try it

Start a new chat and ask:

- *"Give me an overview of the Living Blue site."*
- *"Add the monthly meeting on Tuesday, November 17 at 7 PM at the Main Library, Room B."*
- *"Write this month's newsletter from these notes: …"*
- *"Do a checkup of the site."*
- *"How could the homepage look better?"*
- *"How do I make a post members-only?"*

## Changing the site's design yourself (optional)

Besides the chat helpers above, you can change the site's layout and style
yourself: Claude edits the design on a **test site** and you see each change
there within seconds. When you're happy, your change goes to your developer
for review, and the real site updates after they approve it.

This uses the **Code** tab of the Claude app on your computer and a free
GitHub account. To set it up, open the **Code** tab and send:

> *Set me up as a Living Blue site editor by following
> https://github.com/michael-william/living-blue-claude/blob/main/SETUP-EDITOR.md*

Claude does the rest and tells you what to click.

## What Claude will and won't do

**Will:**
- Explain how to do things on the site, step by step
- Write **drafts** of events, newsletters and posts for you to review
- Copy images into the site's image library for your drafts
- Show how many members you have and how newsletters performed (numbers only)
- Look at the site and suggest improvements
- Send your developer a change request or a help request, **after showing it
  to you first**

**Won't:**
- Change the **real** site's design. Design changes happen on the test site,
  and your developer approves them before they go live.
- **Publish** anything. You review drafts and click Publish yourself.
- **Send newsletters.** You click Send in Ghost after a test email.
- **Delete** anything.
- See members' names or email addresses.

So nothing reaches the public or anyone's inbox unless you choose to send it.

## If something goes wrong

- **"Claude says it can't reach the site"**: check the connector is switched
  on (the tools/connectors button in the chat box), or ask your developer.
- **Anything else**: ask Claude to *"send a help request to my developer"*.
  It will write up what happened and show it to you before sending.

## Updates

When your developer improves the helpers, the updates come through this same
plugin. If a new feature doesn't appear, open **Customize → Plugins** and
check for updates.

---

*For the developer:* the skills are in `plugins/living-blue/skills/`. The
connector is a separate, draft-only MCP server running alongside the Ghost
site. Its address contains a secret and is **never** committed here.
