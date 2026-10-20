# Team conventions and data handling

CLAUDE.md is one person's rules for one folder. A team needs the same rules everywhere, written
once, starting with the one that matters most: what may and may not be given to a model. This
block is done together as a group. The result is a file, `CONVENTIONS.md`, that every project's
CLAUDE.md points to.

## Do

1. If this folder has `overlay/`, read `overlay/CLAUDE.md` and the `data_policy` line in
   `overlay/overlay.yaml`. That is your group's data rule, and it wins. If there's no overlay,
   ask the facilitator for the rule in writing.
2. **Predict:** before anyone writes anything, each person writes down privately one kind of
   material they think is fine to give Claude and one they think isn't. Compare as a group.
   Where did you disagree?
3. Together, write the conventions in the shared document the facilitator opens for the group.
   **Data handling first**: what's allowed, what isn't, and who to ask when unsure. Quote the
   group's data rule rather than paraphrasing it. Then ask Claude to save a copy as
   `CONVENTIONS.md` in this workshop folder. In the follow-up it moves into the team's own
   repository, where everyone's projects can point to it.
4. Then each person adds one line of their own: a habit, a check, a naming rule, anything you'd
   want a colleague's Claude to follow.
5. Add one line to your CLAUDE.md (or `CLAUDE.local.md`): *"Follow CONVENTIONS.md."* Ask Claude,
   in a new session, what it may and may not do with client material. Does the answer match?

## Proof

Your line in the team's conventions file, and you can say where the data rule is written.

## Misconceptions this exposes

- *"Data rules are IT's problem."* The choice of what goes into a session is made by whoever types
  it, every time.
- *"If Claude can open a file, I'm allowed to give it."* Access is not permission. The rule
  decides, not the folder.
- *"Writing it down once is enough."* Conventions get things wrong. Bring one back from your
  homework.
