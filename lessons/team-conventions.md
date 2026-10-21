# Team conventions and data handling

CLAUDE.md is one person's rules for one folder. A team needs the same rules everywhere, written
once, starting with the one that matters most: what may and may not be given to a model. This
block is done together as a group. The result is a file, `CONVENTIONS.md`, that every project's
CLAUDE.md points to.

## Do

**Where:** the whole group together, with the facilitator's shared document open (they send the
link). Then each person in a session on the `claude-code-workshop` folder, in Manual.

1. Read your group's data rule, word for word:

   > Show me the data_policy line in overlay/overlay.yaml and everything in overlay/CLAUDE.md, word for word. Don't summarise.

   **You should see:** the rule, quoted. *"There's no overlay folder"*? Ask the facilitator for the
   rule in writing before going on.
2. **Predict:** on your own, before anyone talks, write down one kind of material you think is
   fine to give Claude and one you think isn't. Then compare as a group. Where did you disagree?
3. Together, in the shared document, write under these headings, in this order:
   - **Data handling:** the group's rule, pasted word for word; what's allowed; what isn't; who to
     ask when unsure (a name).
   - **Our lines:** empty for now.
4. Each person adds one line of their own under **Our lines**: a habit, a check, a naming rule,
   anything you'd want a colleague's Claude to follow.
5. When everyone's line is in, select the whole document, copy it, and paste it after this prompt:

   > Save the text below as CONVENTIONS.md in this folder, exactly as written. Don't commit it.

   **You should see:** a request to create `CONVENTIONS.md` (approve). It stays out of your commits:
   in the follow-up it moves into the team's own repository.
6. Point your own sessions at it. This goes in your personal file, not the shared `CLAUDE.md`:

   > Add the line "Follow CONVENTIONS.md." to CLAUDE.local.md in this folder. Create the file if it doesn't exist.

7. **+ New** for a fresh session on the same folder, and ask:

   > What may and may not you do with client material in this folder, and where is that written?

   **You should see:** the rule from `CONVENTIONS.md`, with the file named. If it answers from
   general knowledge instead, check step 6 saved, and that this is a new session.

## Proof

Your line in the team's conventions file, and you can say where the data rule is written.

## Misconceptions this exposes

- *"Data rules are IT's problem."* The choice of what goes into a session is made by whoever types
  it, every time.
- *"If Claude can open a file, I'm allowed to give it."* Access is not permission. The rule
  decides, not the folder.
- *"Writing it down once is enough."* Conventions get things wrong. Bring one back from your
  homework.
