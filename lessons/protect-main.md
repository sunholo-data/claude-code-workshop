# A review before anything is shared

The team's skills repository has one version everyone uses: its `main` branch. Anything merged
there reaches every colleague's next session. So `main` changes only through a pull request that a
named person has reviewed. This is the same ladder as before, applied to the team: a new skill
is **proposing** until a reviewer approves it, and only then does it reach everyone.

## Do

**Where:** a session on the team skills repository's folder from
[shared-skills-repo](shared-skills-repo.md), in Manual, and the repository's page on github.com.
Step 3 needs whoever has **Admin** on the repository.

1. **Predict:** if you push a change straight to `main`, who sees it, and when?
2. Name the reviewers in a `CODEOWNERS` file, so GitHub asks them automatically. It has to be on
   `main` before the rule can use it, so it goes in by pull request:

   > Switch to main and pull. Make a branch called codeowners. Write .github/CODEOWNERS with one line: * @<reviewer's GitHub username> @<another reviewer's GitHub username>. Commit it, push the branch, and open a pull request into main with gh.

   The reviewers are the overlay's `reviewers`; ask the facilitator for their usernames.

   **You should see:** one new file, prompts for the push and `gh pr create`, then a link. The
   reviewers need Write access to the repository, or GitHub ignores the line. A reviewer merges it.
3. The repository's admin protects `main`: on GitHub, **Settings → Branches**, then add a branch
   protection rule for `main` (the button may be labelled **Add classic branch protection rule**;
   **Settings → Rules → Rulesets** does the same job). Tick:
   - **Require a pull request before merging**, then **Require approvals** (1)
   - **Require review from Code Owners**
   - **Do not allow bypassing the above settings**, so admins are held to it too

   **You should see:** the rule listed for `main`. A banner saying it won't be enforced? See the
   note below.
4. Someone who is **not** a code owner opens a small pull request, for example a clearer
   description for one skill:

   > Make a branch called tidy/<your-github-username>, improve the description of one skill, commit, push, and open a pull request into main with gh.

   Then, on the pull request's page, try to merge it.

   **You should see:** merging blocked, with *Review required* and the code owner named. (Authors
   can't approve their own pull requests, which is why a code owner can't do this step alone.)
5. The named reviewer approves it on GitHub. **You should see:** the merge button becomes
   available. Merge.

**Private repository on GitHub Free?** GitHub doesn't enforce branch rules there; the rule saves
but the merge button stays live. The protection is then a habit, and the proof is the pull request
showing the code owner's review requested and their approval before the merge. The organisation
needs GitHub Team (or the repository must be public) for the rule to bind.

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
