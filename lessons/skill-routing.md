# Many skills, one entry point

With five skills, good descriptions are enough. With thirty skills from two groups, they start to
overlap: two skills both claim "weekly report", one fires when you meant the other, or neither does.
Claude has every skill's description in front of it on every turn and picks by reading them, so
the fix is in the descriptions, and in the shape of the set. Overlapping skills that do the same
job get **merged**. Skills that do different jobs get descriptions that **separate** them, including
when *not* to use each. When people don't know what exists, one **entry** skill can ask what they
need and point to the right one.

## Do

**Where:** a session on the team skills repository's folder from
[shared-skills-repo](shared-skills-repo.md), in Manual, then **+ New** sessions on the same folder.

1. Start from what's on GitHub, and list the skills:

   > Switch to main and pull. Then list every skill in .claude/skills/ with its description. Which pairs overlap? For each pair, give me one request that could reasonably trigger either.

   **You should see:** a list, and one or more pairs with an example request each. No overlaps?
   Pick the two closest skills and use those.
2. Choose one pair. **Predict:** for each of Claude's example requests, which skill will fire?
3. Try each request in a fresh session (**+ New** on the same folder), then ask:

   > Which skill did you use, and why?

4. Decide, back in the first session, on a branch:

   > Make a branch called routing/<your-github-username> and switch to it.

   Same job? Merge them:

   > Merge <skill A> and <skill B> into one skill called <skill A>, keeping the better steps from each, with one description. Delete the other folder.

   Different jobs? Separate them:

   > Rewrite the descriptions of <skill A> and <skill B> so each says what it is for, and add to each "Not for <the other's job>; use <the other skill>."

5. Optional: write an entry skill that lists the team's skills by the situation each is for, and
   tells the person which `/name` to type. It can't run them for you if they have
   `disable-model-invocation: true` in their frontmatter: that setting means only a person can
   start the skill, by typing its name, so Claude (and so an entry skill) can't. Use it for
   specialist skills nobody should get by accident.
6. Test again in a fresh session, then commit, push and open a pull request, as in
   [share-skill-pr](share-skill-pr.md):

   > Commit the changed skill folders. Push the branch and open a pull request into main with gh. In the body, list each test request and which skill it should pick.

   **You should see:** prompts for the push and `gh pr create`, then a link.

## Proof

Two overlapping skills merged, or their descriptions separated, with the test requests that now
pick the right one.

## Misconceptions this exposes

- *"More skills make Claude more capable."* Every description sits in its context every turn, and
  each overlap makes the choice harder.
- *"The skill's name decides when it's used."* The description decides. The name is for calling it
  directly.
- *"An entry skill has to contain everything."* It only routes. The detail stays in the skills it
  points to, and for a skill only a person may start, routing means telling them what to type.
