# Git as undo

Git takes snapshots of a folder, called commits. With them, any change Claude makes can be seen
line by line and taken back, which makes it much safer to say yes. You don't need to learn git
commands: ask Claude in plain words, and read the commands it proposes before approving them.

## Do

1. Ask Claude: *"Copy the samples folder to a new folder called workshop-practice next to this
   one, and make it a git repository with a first commit."* Read each command before approving.
   The first commit may stop to ask for your name and email; that is git, not Claude.
2. Start a **+ New session** with `workshop-practice` as the folder.
3. Ask for two small changes to `tagging-plan.md`, committing after each: *"commit this with a
   message saying what changed."*
4. Ask: *"Show me the history, and what changed in the last commit."*
5. **Predict:** you ask *"undo the last commit's change"*. What happens to the file? What happens
   to the history: is the commit deleted, or is a new one added?
6. Try it. Open the file, then ask for the history again.

## Proof

At least three commits in the log, one of which undoes an earlier change.

## Misconceptions this exposes

- *"Undo means the mistake is erased."* The safe way, a revert, adds a new commit that reverses
  the old one. The history keeps both, which is the point.
- *"Git saves automatically."* Only when you commit. Changes since the last commit can't be
  recovered by git.
- *"Commit messages are for programmers."* They're how you, next month, find the change that
  broke something. Ask for ones that say what and why.
