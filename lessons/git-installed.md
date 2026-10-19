# Git and a GitHub account

Git keeps a history of a folder, so any change Claude makes can be seen and undone. GitHub is
where the team's shared work lives. The Code tab does **not** include git, so it is the one thing
you install yourself. Do this before the day.

## Do

1. **Predict:** is git already on your computer? Most Macs have it, or offer to fetch it; most
   Windows PCs don't.
2. Open a session in the Code tab (any folder, `claude-test` is fine) and open the terminal pane
   with **Ctrl+`** (the key above Tab). Type `git --version` and press Enter.
3. If it prints a version number, you're done with this step. If not:
   - **Mac:** run `xcode-select --install` and accept the pop-up. It takes a few minutes.
   - **Windows:** install **Git for Windows** from git-scm.com/downloads/win, accepting the
     defaults. Restart Claude Desktop afterwards so it finds git.
4. Run `git --version` again.
5. If you don't have a GitHub account, make one at **github.com/signup**. Use the email you'll
   use for work, and turn on two-factor sign-in when it offers.
6. Send your GitHub username (not your password) to the facilitator.

You could also ask Claude in the session to check for git and explain what it finds. Read any
command it wants to run before you approve it.

## Proof

`git --version` prints a version, and the facilitator has your GitHub username.

## Misconceptions this exposes

- *"Git and GitHub are the same thing."* Git is the tool on your laptop and works with no account
  at all. GitHub is a website that stores copies of git repositories so people can share them.
- *"The terminal is for programmers."* Here it is one line, typed once. Most of the day you will
  ask Claude to run commands and read them, not type them.
