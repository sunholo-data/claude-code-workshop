# Git and a GitHub account

*In the workshop, the facilitator walks the room through this from the slides. This page is for doing it beforehand, or afterwards on your own.*

Git keeps a history of a folder, so any change Claude makes can be seen and undone. GitHub is
where the team's shared work lives. The Code tab does **not** include git, so it is the one thing
you install yourself. Do this before the day.

## Do

**Where:** a session on your `claude-test` folder from [install](install.md), in Manual.

1. **Predict:** is git already on your computer? Most Macs have it, or offer to fetch it; most
   Windows PCs don't.
2. In the message box, type this and send it. The `!` means *run this myself*: the command runs
   straight away, without Claude and without asking, and the result appears in the conversation.

   ```
   !git --version
   ```

   ![!git --version and its output](../images/setup/git-version.png)

   **You should see:** `git version` and a number. Then skip to step 5.
3. If it said `command not found` or nothing useful:
   - **Mac:** git comes with Apple's developer tools. Asking for git when they're missing makes
     macOS offer to install them in a pop-up: click **Install** and wait a few minutes. No pop-up?
     Send `!xcode-select --install`.
   - **Windows:** install **Git for Windows** from git-scm.com/downloads/win, accepting the
     defaults. Quit Claude Desktop and open it again afterwards, so it finds git.
4. Send `!git --version` again.

   **You should see:** `git version` and a number. Still not found? Bring the message to the
   facilitator's helper.
5. If you don't have a GitHub account, make one at **github.com/signup**. Use the email you'll
   use for work, and turn on two-factor sign-in when it offers.

   **You should see:** your profile at github.com/<your-username> when you're signed in.
6. Send your GitHub username (not your password) to the facilitator, the way they asked for it.

## The GitHub check

Run this before any step that pushes ([clone-branch](clone-branch.md), [room-pr](room-pr.md),
[share-skill-pr](share-skill-pr.md)), and again whenever a push fails. In a session on the
repository you'll push to, send each line with `!` and read what comes back:

| Send | Good | If not |
|---|---|---|
| `!git remote -v` | a `github.com/…` address for the repository you mean to push to | Nothing printed, or a path on your laptop: this folder isn't a clone. You're probably in a folder made with `git init`, such as `rules-practice`: **+ New** and choose the clone. |
| `!git config user.email` | your email | Nothing: ask Claude to set your git name and email (the email on your GitHub account). |
| `!gh auth status` | `Logged in to github.com account <you>` | `command not found`: install GitHub CLI from cli.github.com. Not logged in: in the terminal pane, `gh auth login` then `gh auth setup-git`. |
| `!gh repo view --json viewerPermission` | `WRITE`, `MAINTAIN` or `ADMIN` | `READ`: you can't push here yet. The facilitator adds you; then accept the invitation by email or at github.com/notifications, and check again. |

Or ask Claude: *"Run the GitHub check from lessons/git-installed.md, one command at a time, and
tell me what to fix."* Signing in stays yours, in the terminal pane; `gh auth status` hides the
token, so its output is safe in the conversation.

You could also ask Claude to check for git and explain what it finds. The difference: with `!`
you run the command; without it, Claude decides what to run and asks you first.

## Proof

`!git --version` in the Code tab prints a version, and the facilitator has your GitHub username.

## Misconceptions this exposes

- *"Git and GitHub are the same thing."* Git is the tool on your laptop and works with no account
  at all. GitHub is a website that stores copies of git repositories so people can share them.
- *"Commands need a terminal."* A `!` in the message box runs one for you, and Claude can see the
  result. Most of the day you will ask Claude to run commands and read them, not type them.
- *"`!` is fine for everything."* Its output lands in the conversation, which Claude reads. Signing
  in to anything stays out of it: that happens in the terminal pane or a browser.
