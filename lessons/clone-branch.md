# Clone, branch, push

To work on something shared, you **clone** it (a full copy on your laptop, with its history), make
a **branch** (your own line of changes, so the main version is untouched), and **push** the branch
back to GitHub where others can see it. In a facilitated group you can push branches to this
repository, but not to its `main`: that only changes through a pull request the facilitator merges.

## Do

1. You already cloned this workshop repository. That clone is today's practice repository: click
   **+ New** and choose the `claude-code-workshop` folder, **not** a practice folder from an
   earlier exercise. Those were made with `git init` and have nowhere to push to.
2. **Sign-in check** ([the GitHub check](git-installed.md#the-github-check)). Send each line and
   fix anything that isn't good before going on:
   - `!git remote -v`: a `github.com/…/claude-code-workshop` address. Nothing? You're in the wrong
     folder.
   - `!git config user.email`: your email. Nothing? Ask Claude to set your git name and email.
   - `!gh auth status`: `Logged in to github.com account <you>`.
   - `!gh repo view --json viewerPermission`: `WRITE` or better. `READ` means the facilitator
     hasn't added you yet, or you haven't accepted the invitation (email, or
     github.com/notifications).

   `gh` not found, or not logged in? On a Mac git can't ask for your sign-in on its own, so
   GitHub CLI is needed (on Windows too, for this check): install it from cli.github.com, then in the terminal pane (**Ctrl** and the backtick key) type `gh auth login`,
   choose the browser option, and afterwards `gh auth setup-git`. Use the terminal pane, not `!`:
   sign-in asks you questions, and anything run with `!` lands in the conversation. Never paste a
   password or token into the chat.
3. Ask: *"Make a branch called practice/<your-github-username>."*
4. Make one small change (a line in your own `notes/<your-github-username>.md`) and ask Claude to
   commit it.
5. **Predict:** you ask Claude to push the branch. Will it ask you first? Will your change appear
   on the `main` branch on GitHub?
6. Ask it to push. Then open the repository on GitHub, find the branch list, and open yours.
7. Now try the thing you shouldn't be able to do: ask Claude to push your commit straight to
   `main`. Read what GitHub says back.

**Not in a facilitated group?** You won't have permission to push here. Ask Claude to fork the
repository to your own GitHub account (`gh repo fork --remote`) and push your branch to the fork.
That needs the GitHub CLI: on Windows too, install it from cli.github.com and sign in with
`gh auth login` in the terminal pane first.

## Proof

Your branch visible on GitHub, with your commit on it, and GitHub's refusal when you pushed to `main`.

## Misconceptions this exposes

- *"Pushing changes everyone's copy."* It adds your branch to GitHub. Nothing reaches the main
  branch until someone merges it, and nobody's laptop changes until they pull.
- *"Cloning is downloading."* A download is a snapshot. A clone keeps the history and knows where
  it came from, so you can push back and pull updates.
- *"Claude can sign in for me."* It shouldn't, and you shouldn't give it the means to. Sign-in is
  yours.
