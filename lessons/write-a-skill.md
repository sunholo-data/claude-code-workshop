# Write your own skill

The best first skill is something you already do every week, the same way, and explain to people
more often than you'd like: a weekly summary, turning meeting notes into actions, checking a
document against a checklist. Do it once with Claude the ordinary way, then turn that conversation,
corrections included, into a skill. The test is not whether it works for you. It is whether a
colleague can run it without asking you anything.

## Do

**Where:** a new folder, `skill-work`, next to the workshop folder: your own, local, not on
GitHub. Make it from a session on the `claude-code-workshop` folder:

> Make a folder called skill-work next to this workshop folder, make it a git repository, and copy the permissions block from settings/starter.json into skill-work/.claude/settings.json. Commit.

Then **+ New** on `skill-work`, in Manual.

1. Pick a task you do at least weekly and can describe in about five steps. Use material your
   group's data rule allows, or a made-up stand-in of the same shape: ask Claude to make one.
2. Do the task once with Claude, the ordinary way. Note every time you had to correct it.
3. Turn it into a skill:

   > Turn what we just did into a project skill at .claude/skills/<your-github-username>-<short-name>/SKILL.md, with name set to the same as the folder. Include the corrections I made.

   **You should see:** one new `SKILL.md`. Read it before you approve it.
4. Check the description. Is it in the words you'd use when you need this, and does it say when the
   skill should **not** be used? If not, ask Claude to rewrite it in your words.
5. If the output has a fixed format, ask for a template in the skill's `resources/` folder. If a
   step is mechanical, such as counting, renaming or reformatting, ask for a script in `scripts/`
   instead of an instruction.
6. **Predict:** a colleague asks for the task in their own words. What will they get, and at which
   step will they need to ask you something?
7. Test it yourself as a stranger would: **+ New** for a fresh session on `skill-work`, ask for the
   task in different words from the description, and don't help. Fix what you had to explain.
   Then commit:

   > Commit the skill folder.

8. Bring it to the next session. There it goes into the team's repository by pull request
   ([share-skill-pr](share-skill-pr.md)), and a colleague runs it as the review: that's the
   colleague test.

## Proof

A colleague runs your skill and gets the right result without asking you.

## Misconceptions this exposes

- *"A skill is just a saved prompt."* It is a prompt, a rule for when to use it, and the files it
  carries, kept in git so that changes to it are visible and reviewed.
- *"It works for me, so it works."* What you know leaks in without you noticing. The colleague test
  is the only one that finds it.
- *"More instructions make a better skill."* A short body with the detail moved into `resources/`
  is easier to follow and to fix. Anthropic's guidance is to keep `SKILL.md` under 500 lines.
