# Living Blue: editor setup (instructions for Claude)

> **For the person reading this:** you don't need to do anything here
> yourself. Open the **Code** tab in the Claude desktop app and send:
>
> *Set me up as a Living Blue site editor by following
> https://github.com/michael-william/living-blue-claude/blob/main/SETUP-EDITOR.md*

---

**Claude, you're setting up a non-technical person's computer** so she can edit
the design of the Living Blue website (a community site on Ghost). Her edits
show up on a test site within seconds; when she's happy, they go to the
developer (Michael, GitHub `michael-william`) as a pull request for review.
The site's code lives in the **private** repository
`michael-william/living-blue`. Once it's on her computer, its `CLAUDE.md` tells
you everything about working on it. This page only gets her there.

How to work with her during setup:

- One step at a time. Before each step, one plain sentence saying what it's for.
- Run every command yourself. Ask her only to click, sign in, or paste.
- No jargon. If something fails, fix it quietly if you can; if you can't,
  explain in one sentence and suggest she email Michael.
- Detect the OS first (Windows, macOS) and use the matching commands.
- Don't change anything outside what's listed here.

## 0. What she should already have

Ask her to confirm (don't continue until she does):

1. She has **accepted the GitHub invitation** to `michael-william/living-blue`
   (an email from GitHub). If not, ask her to find it, or tell Michael her
   GitHub username.
2. She has received from Michael, **by text or another private channel**:
   her **dev-sync token** (a long code) and the **test site password**.
   Tell her to keep them handy but **not to paste the test site password
   here**: it goes only into the browser.

## 1. Git

Run `git --version`. If it's missing:

- **Windows:** Claude Code needs Git for Windows anyway, so it's almost
  certainly there. If not, ask her to install it from
  https://git-scm.com/download/win (Next on every screen), then restart this
  session.
- **macOS:** run `xcode-select --install` and ask her to click **Install** in
  the window that appears; wait until she says it finished.

## 2. GitHub CLI and sign-in

Check `gh --version`. If missing:

- **Windows:** `winget install --id GitHub.cli -e --accept-source-agreements --accept-package-agreements`.
  The new command may not be on PATH in this session. Try
  `"/c/Program Files/GitHub CLI/gh.exe" --version` and use that full path
  for the rest of the setup. Otherwise ask her to close and reopen the session
  and send the same request again (this page is safe to re-run; skip finished steps).
- **macOS:** `brew install gh` if Homebrew exists; otherwise download the
  latest `gh_*_macOS_universal.pkg` from https://github.com/cli/cli/releases
  and open it (she clicks through the installer).

Then:

    gh auth status || gh auth login --hostname github.com --git-protocol https --web
    gh auth setup-git

Tell her before running the login: "A short code will appear; your browser
opens GitHub; paste the code there and click Authorize."

Check access: `gh repo view michael-william/living-blue --json name`. If it
fails with "Could not resolve", the invitation isn't accepted yet → step 0.

## 3. Get the site's code

Into her **Documents** folder (`~/Documents`; on Windows the same path works
in Git Bash):

    cd ~/Documents
    [ -d living-blue ] || gh repo clone michael-william/living-blue
    cd living-blue
    git config user.name "<ask her full name>"
    git config user.email "<ask the email she uses for the site>"

## 4. Save her token

Ask her to paste the dev-sync token. Save it, and only it:

    mkdir -p ~/.living-blue
    printf '%s' '<token>' > ~/.living-blue/devsync-token

Then check, from the `living-blue` folder: `tools/lb-dev status`.
- `"active":false` (or someone's name) → working.
- "bad or missing token" → ask her to copy it again from Michael's message.

## 5. Hand over

Tell her, in these words or close:

> All set. From now on, to work on the site:
> 1. Open the **Code** tab and start a **new session**.
> 2. Pick the folder **Documents → living-blue**. Always this folder: that's
>    where Claude learns how the site works and its safety rules.
> 3. Open https://staging.livingblueintv.com in your browser, enter the test
>    site password, then **Sign in** with your email and click the link that
>    arrives (check Spam).
> 4. Tell Claude what you'd like to change, for example *"Start a change:
>    make the 'Upcoming events' heading say 'What's coming up'"*.

Then stop. Don't start editing in this session: it isn't running inside the
`living-blue` folder, so the site's rules and live preview aren't active here.
