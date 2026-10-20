# Clone, branch, push

To work on something shared, you **clone** it (a full copy on your laptop, with its history), make
a **branch** (your own line of changes, so the main version is untouched), and **push** the branch
back to GitHub where others can see it. In a facilitated group you can push branches to this
repository, but not to its `main`: that only changes through a pull request the facilitator merges.

## Do

1. You already cloned this workshop repository. That clone is today's practice repository: work in
   a session on it.
2. **Sign-in check.** Ask Claude: *"Can git push to GitHub from here? Don't push anything; just
   check how it would sign in."* On Windows, Git for Windows opens a browser window when it needs
   you. On a Mac it usually can't ask: install **GitHub CLI** from cli.github.com, then in the
   terminal pane (**Ctrl+`**) type `gh auth login`, choose the browser option, and afterwards
   `gh auth setup-git`. Use the terminal pane, not `!`: sign-in asks you questions, and anything
   run with `!` lands in the conversation. Never paste a password or token into the chat.
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

## Proof

Your branch visible on GitHub, with your commit on it, and GitHub's refusal when you pushed to `main`.

## Misconceptions this exposes

- *"Pushing changes everyone's copy."* It adds your branch to GitHub. Nothing reaches the main
  branch until someone merges it, and nobody's laptop changes until they pull.
- *"Cloning is downloading."* A download is a snapshot. A clone keeps the history and knows where
  it came from, so you can push back and pull updates.
- *"Claude can sign in for me."* It shouldn't, and you shouldn't give it the means to. Sign-in is
  yours.
