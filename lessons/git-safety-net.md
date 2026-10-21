# Git as undo

Git takes snapshots of a folder, called commits. With them, any change Claude makes can be seen
line by line and taken back, which makes it much safer to say yes. You don't need to learn git
commands: ask Claude in plain words, and read the commands it proposes before approving them.

## Do

**Where:** first a session on the `claude-code-workshop` folder, in Manual, to make a folder
called `workshop-practice` next to it. Then a **+ New** session on `workshop-practice`, in Manual.

1. Check git knows who you are. Send:

   ```
   !git config user.email
   ```

   **You should see:** your email. Nothing? Git won't ask: the first commit would stop with
   *"Author identity unknown"*, or on a Mac go through under a made-up name. Set it first:

   > Set my git name to <your name> and email to <the email on your GitHub account>, for every repository.

2. Make `workshop-practice`:

   > Copy the files in samples/ to a new folder called workshop-practice next to this workshop folder, not inside it. Make it a git repository and commit those files.

   **You should see:** a prompt for each command (read each one before approving), then a commit
   with `2 files changed`.
3. **+ New**, the folder button, **Open folder…**, choose `workshop-practice`, and set **Manual**.
4. Make two small changes, committing after each:

   > In tagging-plan.md, change the Owner line to "the analytics team". Commit this with a message saying what changed.

   > Add an open question to tagging-plan.md: "Do we track zero-result searches?" Commit this with a message saying what changed.

   **You should see:** an edit to approve, then a commit, each time.
5. Look at the record:

   > Show me the history, and what changed in the last commit.

   **You should see:** three commits, newest first, and the last one's change in red and green.
6. **Predict:** you ask *"undo the last commit's change"*. What happens to the file? What happens
   to the history: is the commit deleted, or is a new one added?
7. Try it:

   > Undo the last commit's change.

   **You should see:** a `git revert` to approve (or a `git reset`, which asks: ask for a revert
   instead, so the history keeps both). Open `tagging-plan.md`: the open question is gone.
8. Ask for the history again.

   > Show me the history.

   **You should see:** four commits, the newest saying it reverts the one before.

## Proof

At least three commits in the log, one of which undoes an earlier change.

## Misconceptions this exposes

- *"Undo means the mistake is erased."* The safe way, a revert, adds a new commit that reverses
  the old one. The history keeps both, which is the point.
- *"Git saves automatically."* Only when you commit. Changes since the last commit can't be
  recovered by git.
- *"Commit messages are for programmers."* They're how you, next month, find the change that
  broke something. Ask for ones that say what and why.
