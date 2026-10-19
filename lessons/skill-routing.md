# Many skills, one entry point

With five skills, good descriptions are enough. With thirty skills from two groups, they start to
overlap: two skills both claim "weekly report", one fires when you meant the other, or neither does.
Claude has every skill's description in front of it on every turn and picks by reading them, so
the fix is in the descriptions, and in the shape of the set. Overlapping skills that do the same
job get **merged**. Skills that do different jobs get descriptions that **separate** them, including
when *not* to use each. When people don't know what exists, one **entry** skill can ask what they
need and point to the right one.

## Do

1. In your session on the team's skills repository, ask: *"List every skill with its description.
   Which pairs overlap? For each pair, give me one request that could reasonably trigger either."*
2. Choose one pair. **Predict:** for each of Claude's example requests, which skill will fire?
3. Try each request in a fresh session, then ask *"Which skill did you use, and why?"*
4. Decide. Same job: merge them into one skill with the better steps and one description.
   Different jobs: rewrite both descriptions to say what each is for, and add *"Not for <X>; use
   <other skill>."*
5. Optional: write an entry skill that lists the team's skills by the situation they're for.
   Specialist skills you only want run by name can be kept out of Claude's own choosing with
   `disable-model-invocation: true` in their frontmatter, so the entry skill does the routing.
6. Make the change on a branch and open a pull request, as in [share-skill-pr](share-skill-pr.md).
   Put the test requests, and which skill each should pick, in the description.

## Proof

Two overlapping skills merged, or their descriptions separated, with the test requests that now
pick the right one.

## Misconceptions this exposes

- *"More skills make Claude more capable."* Every description sits in its context every turn, and
  each overlap makes the choice harder.
- *"The skill's name decides when it's used."* The description decides. The name is for calling it
  directly.
- *"An entry skill has to contain everything."* It only routes. The detail stays in the skills it
  points to.
