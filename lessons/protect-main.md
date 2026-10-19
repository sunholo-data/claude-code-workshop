# A review before anything is shared

The team's skills repository has one version everyone uses: its `main` branch. Anything merged
there reaches every colleague's next session. So `main` changes only through a pull request that a
named person has reviewed. This is the same ladder as before, applied to the team: a new skill
is **proposing** until a reviewer approves it, and only then does it reach everyone.

## Do

1. **Predict:** if you push a change straight to `main`, who sees it, and when?
2. In the team repository on GitHub, open **Settings → Rules** (or **Branches** on some plans) and
   look at what protects `main`. If nothing does, ask whoever owns the repository to add a rule:
   *require a pull request before merging*, with *at least one approval*.
3. Add a `CODEOWNERS` file (in `.github/`) naming the reviewers, so GitHub asks them
   automatically. Ask Claude to write it from your group's list of reviewers.
4. Open a small pull request of your own, for example a clearer description for one skill. Try to
   merge it before anyone has approved it. What happens?
5. Have the named reviewer approve it, then merge.

## Proof

A pull request that could not be merged until a named reviewer approved it.

## Misconceptions this exposes

- *"A rule in the README saying 'get a review' is enough."* It is a habit, not a guard. A branch
  rule is enforced by GitHub.
- *"Every GitHub plan can enforce this."* Check yours: on GitHub's free plan, branch rules are not
  enforced on private repositories. There, the review is the team's habit and `CODEOWNERS` only
  requests it.
- *"The reviewer checks the spelling."* The reviewer decides whether this becomes how the whole
  team works. That is the owner of the standard's decision, not a proofread.
