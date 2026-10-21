# Contribute a skill by pull request

Nobody pushes straight to the main branch of the team's skills repository. You put your skill on a
branch and open a **pull request**: a request to merge, which the group's named reviewers (the
overlay's `reviewers`) read, run and approve. Once it is merged, everyone who pulls gets the same
version. Both groups use one copy of each skill rather than each keeping a slightly different one,
and every change to it has a name and a reason attached.

## Do

**Where:** a session on the team repository's folder from [shared-skills-repo](shared-skills-repo.md),
in Manual, with its four checks good. Your skill is in `skill-work` from
[write-a-skill](write-a-skill.md).

1. Start from what's on GitHub, on your own branch:

   > Switch to main and pull, then make a branch called skill/<your-github-username>-<skill-name> and switch to it.

2. Bring your skill in, and check it doesn't collide:

   > Copy my skill folder from ../skill-work/.claude/skills/ into .claude/skills/ here. Then tell me whether its name or its description overlaps any skill already in this folder.

   **You should see:** a request to read outside this folder (approve: it's your own `skill-work`),
   one new folder, and a yes or no on overlaps. An overlap? See [skill-routing](skill-routing.md)
   before going on.
3. Commit, push and open the pull request:

   > Commit only my skill's folder. Push the branch and open a pull request into main with gh. Body: what the skill does, one request to test it with, and what a correct result looks like.

   **You should see:** prompts for the push and for `gh pr create` (approve both), then a link.
4. **Predict:** what will your reviewer ask you to change?
5. Review a pull request from the **other** group, as a colleague meeting their skill for the
   first time:

   > List the open pull requests. Check out number <N> with gh pr checkout.

   Then **+ New** for a fresh session on this folder, send their test request in your own words,
   and don't help. Back in the first session:

   > Leave a comment on pull request <N> saying what happened when I ran it: <what you saw>.

6. Answer your own review: ask Claude to make the change your reviewer asked for, commit it and
   push to the same branch. The pull request updates itself.
7. A reviewer named in the overlay (`reviewers`) merges it. Then someone in the other group
   switches to `main`, pulls, and uses your skill.

## Proof

Your skill merged, and a colleague in the other group used it.

## Misconceptions this exposes

- *"Review means checking the spelling."* A reviewer runs the skill. Most of what they find is in
  the description and in what the skill assumes you already know.
- *"Merged means everyone has it."* Everyone who pulls has it. Until then they have the old version.
- *"Once the pull request is open, it's fixed."* Every push to the branch updates it. The review is
  a conversation, not a verdict.
