# Your skill, in everyone's copy

A pull request asks for your branch to be merged into the main version. Once it is merged,
everyone who pulls gets your change, and you get theirs. Here everyone in the room adds one small
skill to this workshop repository. The facilitator merges them all, then everyone pulls and finds
the whole room's work in their own copy.

## Do

1. Start from an up-to-date `main`: ask Claude to switch to `main` and pull.
2. Ask for a branch named `skill/<your-github-username>`.
3. Write one small skill in **its own folder**,
   `.claude/skills/<your-github-username>-<skill-name>/SKILL.md` (for example
   `.claude/skills/mark-explain-diff/`), and change nothing else. The folder name is what everyone
   will type after `/`, and your username keeps it from clashing with a colleague's. Ideas, all things you'd want today:
   - *explain-diff*: "explain what changed since my last commit, in plain English"
   - *where-was-i*: "summarise my progress.md in three lines"
   - *check-before-push*: "list what's about to be pushed, and anything that looks private"

   Give it a `description` that says when it should be used, in words someone else would type.
4. Try it yourself in a **new session** (skills load when a session starts), then commit.
5. **Predict:** after you push and open a pull request, will your skill appear in your
   neighbour's Code tab? When will it?
6. Push the branch, and ask Claude to open a pull request (or open it on GitHub: the yellow
   **Compare & pull request** banner). Say in one line what the skill does.
7. Wait for the facilitator to merge. You can't merge it yourself: `main` only changes through a
   reviewed pull request. Look at the PR on GitHub while you wait.
8. When everything is merged, ask Claude to switch to `main` and pull. Start a **new session**,
   type `/`, and find your skill and the others. Run one written by someone else.

## Proof

After the merge and a pull, your skill and a colleague's both appear when you type `/`, and you
ran theirs.

## Why one folder each

Everyone changes different files, so every pull request merges cleanly, in any order. If two
people had edited the same line of the same file, the second merge would stop with a conflict.
That's worth seeing once, but not with fifteen people at once.

## Misconceptions this exposes

- *"Merged means everyone has it."* Merged means it's on GitHub's `main`. Nobody's laptop changes
  until they pull.
- *"I pushed, so it's in main."* You pushed a branch. Someone else decides whether it joins `main`.
- *"I can't break anything by opening a PR."* True, and that's the point: the review is the gate.
