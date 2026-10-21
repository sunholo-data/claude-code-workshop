# Contribute a skill by pull request

Nobody pushes straight to the main branch of the team's skills repository. You put your skill on a
branch and open a **pull request**: a request to merge, which the group's named reviewers (the
overlay's `reviewers`) read, run and approve. Once it is merged, everyone who pulls gets the same
version. Both groups use one copy of each skill rather than each keeping a slightly different one,
and every change to it has a name and a reason attached.

## Do

1. Run [the GitHub check](git-installed.md#the-github-check) in your session on the team
   repository: it's a different repository from the workshop, so your access to it is checked
   separately. Then ask Claude for a branch called
   `skill/<your-github-username>-<skill-name>`.
2. Copy your skill folder from [write-a-skill](write-a-skill.md) into `.claude/skills/`. Check that
   its name doesn't clash with an existing skill, and that its description doesn't overlap one. If it
   does, see [skill-routing](skill-routing.md).
3. Commit, push, and ask Claude to open a pull request. This needs the GitHub CLI, `gh`; without it,
   open the pull request on GitHub in the browser. In the description, write what the skill does, a
   request to test it with, and what a correct result looks like.
4. **Predict:** what will your reviewer ask you to change?
5. Review a pull request from the **other** group: switch to their branch, start a new session, run
   their test request, and leave at least one comment on GitHub about what happened.
6. Answer your own review. Push the fix to the same branch; the pull request updates itself.
7. Once a reviewer merges it, someone in the other group pulls and uses your skill.

## Proof

Your skill merged, and a colleague in the other group used it.

## Misconceptions this exposes

- *"Review means checking the spelling."* A reviewer runs the skill. Most of what they find is in
  the description and in what the skill assumes you already know.
- *"Merged means everyone has it."* Everyone who pulls has it. Until then they have the old version.
- *"Once the pull request is open, it's fixed."* Every push to the branch updates it. The review is
  a conversation, not a verdict.
