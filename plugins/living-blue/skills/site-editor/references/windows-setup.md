# Setting up site editing on Windows (once, about 20 minutes)

Walk her through one step at a time and wait for "done" before the next. Where
a step is a command, run it for her in Claude Code rather than asking her to
type it. Ask her developer for help at any point.

## What she needs from the developer first

- An **invitation** to the `michael-william/living-blue` repository on GitHub
  (sent to her GitHub account, see step 2).
- Her **dev-sync token**: a long code that lets her computer update the test
  site. Treat it like a password.
- The **test site password** (staging.livingblueintv.com asks for it).
- Confirmation that her email address is **allowed on the test site** (the
  developer adds her as a test-site member so sign-in links reach her inbox).

## 1. Install Git for Windows

Claude Code on Windows needs it.

1. Go to https://git-scm.com/download/win and download the installer.
2. Run it and click **Next** through every screen; the defaults are right.

## 2. GitHub account

1. If she doesn't have one: https://github.com/signup. Pick a username she'll
   remember and send it to the developer.
2. When the invitation email arrives ("invited you to collaborate on
   michael-william/living-blue"), click **Accept invitation**.

## 3. Open Claude Code

1. In the Claude app, open the **Code** tab.
2. Choose a folder to work in, e.g. **Documents**. (Claude Code may ask for
   permission to use it; allow.)

## 4. Let Claude finish the setup

From here, Claude runs the commands. In order:

1. **GitHub's command-line tool**, used to send changes for review:

       winget install --id GitHub.cli -e --accept-source-agreements --accept-package-agreements

   Then restart the Code tab (close and reopen the session) so it's found.
2. **Sign in to GitHub**:

       gh auth login --hostname github.com --git-protocol https --web
       gh auth setup-git

   It shows a one-time code and opens the browser. She pastes the code and
   clicks **Authorize**.
3. **Download the site's code** into the chosen folder and open it:

       gh repo clone michael-william/living-blue
       cd living-blue

   Then tell her to open the new **living-blue** folder in the Code tab (pick it
   as the session's folder), so the site's own instructions and safety checks
   load. Continue there.
4. **Name on her changes** (shown to the developer):

       git config user.name "<her name>"
       git config user.email "<her email>"

5. **Save the dev-sync token.** Ask her to paste the token from the developer
   into the chat, then:

       mkdir -p ~/.living-blue && printf '%s' '<token>' > ~/.living-blue/devsync-token

   Check it works: `tools/lb-dev status` should print `"active":false` (or who
   is editing). "bad or missing token" means it was copied wrong.

## 5. First try

1. Open https://staging.livingblueintv.com in her browser and enter the test
   site password. Keep that tab open.
2. Ask Claude something small, like *"make the 'Upcoming events' heading say
   'What's coming up'"*. Claude starts a change, edits, and tells her to
   refresh. She should see it within a few seconds.
3. Then say *"never mind, throw that change away"*: Claude runs
   `tools/lb-dev end`, switches back to `main` and deletes the practice change.

Setup is done. Each time after this: open the Code tab in the **living-blue**
folder and say what she'd like to change.
