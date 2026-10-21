# One real task, end to end

The capstone. Take the small, real piece of your own work you brought an idea for, and do it in
the new way: a clear request, the right files, a plan if it's more than a few steps, git as the
safety net, and a check you trust. Then show the room. Your group's data rule decides what
material you may use; if your real task needs something it doesn't allow, use a made-up stand-in
of the same shape.

## Do

**Where:** first a session on the `claude-code-workshop` folder, in Manual, to make a folder called
`real-task` next to it with the workshop's starter rules. Then a **+ New** session on `real-task`,
in Manual.

1. Make the folder. A new folder has no rules of its own, so this copies the starter ones in:

   > Make a folder called real-task next to this workshop folder, not inside it. Make it a git repository, copy the permissions block from settings/starter.json into real-task/.claude/settings.json, and commit.

   **You should see:** `real-task` with a `.claude/settings.json` and one commit.
2. **+ New**, the folder button, **Open folder…**, choose `real-task`, and set **Manual**. If it
   asks whether you trust the folder, say yes: that's what lets its rules load. Put in only the
   files the task needs and your group's data rule allows: copy them into `real-task` in Finder or
   File Explorer, or ask Claude for a made-up stand-in of the same shape.
3. Write your request as a short brief: what you want, which files (`@`), and what "done" looks
   like. If it has more than a couple of steps, switch to **Plan** first. The shape:

   > I want <the result>. Use @<file> and @<file>. Done means <what you'll check>. Show me a plan first.

4. **Predict:** before you send it, write one line on what you expect Claude to do, and one on
   where you think it will go wrong.
5. Run it. When something works:

   > Commit this with a message saying what changed.

   Reject what you don't want, or ask *"undo the last commit's change"* as in
   [git-safety-net](git-safety-net.md).
6. **Check it** against something you trust: open the files, recount a number, compare with the
   original, or ask Claude to show its evidence and check that yourself.
7. Prepare three sentences for the room: what you asked, what it did, how you checked it. Include
   where it went wrong, if it did; that's the most useful part for everyone else.

## Proof

Shown to the room: what you asked, what it did, and how you checked it.

## Misconceptions this exposes

- *"If it finished without errors, it's right."* Finishing is not the same as being correct. The
  check is your part of the job.
- *"Real work needs real data."* Often the shape of the data is enough to build and test the
  method; the real run can wait for what the rules allow.
- *"My prediction was wrong, so I did it badly."* The gap between prediction and result is where
  you learn what this tool is.
