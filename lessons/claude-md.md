# CLAUDE.md — standing instructions

A file called `CLAUDE.md` in the folder is read at the start of every session, so anything you
write there applies without being repeated. This workshop already has one; open it and see what
it tells Claude. For your own experiments use `CLAUDE.local.md` next to it: it is read the same
way and is meant for personal rules, so you don't change the shared file.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual, then a **+ New** session on
the same folder.

1. **Before.** Send:

   > What happened to newsletter signups in samples/daily-sessions.csv? Give the dates.

   Note how it writes dates, and whether it says what it read.
2. Create `CLAUDE.local.md` yourself, not by asking Claude: if Claude wrote it, the rule would
   already be in this conversation and step 4 would prove nothing.
   - **Mac:** open **TextEdit**, **File → New**, then **Format → Make Plain Text**.
   - **Windows:** open **Notepad**.

   Paste this one line:

   ```
   - Write dates as "15 Sept 2026", never 2026-09-15. End every answer with "Read:" and the files you read.
   ```

   Save it in the `claude-code-workshop` folder as `CLAUDE.local.md` (on a Mac, untick *If no
   extension is provided, use ".txt"*; in Notepad, set **Save as type** to **All files**).

   **You should see:** `CLAUDE.local.md` next to `CLAUDE.md` in the folder, not `CLAUDE.local.md.txt`.
3. **Predict:** you ask the same question again in the same session. Will the rule apply?
4. Try it: send the step 1 prompt again in this session. Then **+ New**, open
   `claude-code-workshop`, Manual, and send it once more.

   **You should see:** most likely, the old style in the first session and the new one in the new
   session: the file is read when a session starts. No change in the new session? Check the file's
   name and that it's in the workshop folder itself.
5. Make the rule worse on purpose. In your editor, replace the line with *"be clear about dates"*,
   save, start another **+ New** session, ask again, and see what survives.
6. Don't commit `CLAUDE.local.md`; it's yours, and git already ignores it. The rule now applies to
   every later session on this folder, the guide's included. Delete the line when you're done with
   it, or keep it if you like answers that say what they read.

## Proof

The same request answered before and after one rule, with the difference visible, and you can
say which rule caused it.

## Misconceptions this exposes

- *"I told it once, so it knows."* A message lasts one session. A line in CLAUDE.md lasts every
  session.
- *"It picks up the change immediately."* The file is read when a session starts; that's why you
  needed a new one.
- *"More rules make it better."* Every line competes for attention. Short, specific, checkable
  rules work; vague ones are ignored politely.
