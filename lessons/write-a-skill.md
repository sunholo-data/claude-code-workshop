# Write your own skill

The best first skill is something you already do every week, the same way, and explain to people
more often than you'd like: a weekly summary, turning meeting notes into actions, checking a
document against a checklist. Do it once with Claude the ordinary way, then turn that conversation,
corrections included, into a skill. The test is not whether it works for you. It is whether a
colleague can run it without asking you anything.

## Do

1. Pick a task you do at least weekly and can describe in about five steps. Use material your
   group's data rule allows, or a made-up stand-in of the same shape.
2. In a repository of your own (the practice repository from [clone-branch](clone-branch.md) is
   fine), do the task once with Claude. Note every time you had to correct it.
3. Ask: *"Turn what we just did into a project skill at `.claude/skills/<short-name>/SKILL.md`.
   Include the corrections I made."* Read the result before accepting it.
4. Check the description. Is it in the words you'd use when you need this, and does it say when the
   skill should **not** be used?
5. If the output has a fixed format, put a template in `resources/`. If a step is mechanical, such
   as counting, renaming or reformatting, ask for a script in `scripts/` instead of an instruction.
6. **Predict:** a colleague opens this folder and asks for the task in their own words. What will
   they get, and at which step will they need to ask you something?
7. Commit and push. Have a colleague clone the repository, start a new session on it, and ask for
   the task. Say nothing; watch.
8. Fix what they stumbled on. It is usually the description, an input nobody told them to supply, or
   something only you knew.

## Proof

A colleague runs your skill and gets the right result without asking you.

## Misconceptions this exposes

- *"A skill is just a saved prompt."* It is a prompt, a rule for when to use it, and the files it
  carries, kept in git so that changes to it are visible and reviewed.
- *"It works for me, so it works."* What you know leaks in without you noticing. The colleague test
  is the only one that finds it.
- *"More instructions make a better skill."* A short body with the detail moved into `resources/`
  is easier to follow and to fix. Anthropic's guidance is to keep `SKILL.md` under 500 lines.
