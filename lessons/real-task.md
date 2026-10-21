# One real task, end to end

The capstone. Take the small, real piece of your own work you brought an idea for, and do it in
the new way: a clear request, the right files, a plan if it's more than a few steps, git as the
safety net, and a check you trust. Then show the room. Your group's data rule decides what
material you may use; if your real task needs something it doesn't allow, use a made-up stand-in
of the same shape.

## Do

**Where:** first a session on the `claude-code-workshop` folder, in Manual, to make a folder called
`real-task` next to it with the workshop's starter rules. Then a **+ New** session on `real-task`,
in Manual. Leave time to check the result, not just to get one.

1. **Choose the task.** It counts if it's any of these:
   - something you do every week, the same way;
   - a one-off you'll have to do again for the next client or project (a script, a spec, a check);
   - a question you keep asking AI, that could become standing instructions or a skill.

   No idea? Pick one of these, or ask Claude to *"interview me: three questions about my week,
   then propose a task we can finish in 45 minutes"*:
   - check your own company's website in the Browser pane: read the dataLayer, list the tags it
     sent, and write a QA file you could rerun after a release;
   - make up a non-standard dataLayer, then have Claude write and test a script that converts it to
     a standard GA4 ecommerce event;
   - make up five business requirements, and have Claude propose KPIs and the events each needs;
   - with an MCP server you connected today, write a one-page comparison with a source for every row.

   **Then check it against your group's data rule, now, before anything goes in.** Read the rule
   (in a workshop session: *"Show me the data_policy line in overlay/overlay.yaml, word for
   word"*). Client material, a client's spec, or a client's site, when the rule says no client
   data? Use a made-up stand-in of the same shape, or your own company's material instead.
2. Make the folder. A new folder has no rules of its own, so this copies the starter ones in:

   > Make a folder called real-task next to this workshop folder, not inside it. Make it a git repository, copy the permissions block from settings/starter.json into real-task/.claude/settings.json, and commit.

   **You should see:** `real-task` with a `.claude/settings.json` and one commit.
3. **+ New**, the folder button, **Open folder…**, choose `real-task`, and set **Manual**. If it
   asks whether you trust the folder, say yes: that's what lets its rules load. Put in only the
   files the task needs and the rule allows: copy them into `real-task` in Finder or File
   Explorer, or ask Claude for the made-up stand-in.
4. Write your request as a short brief: what you want, which files (`@`), and what "done" looks
   like. If it has more than a couple of steps, switch to **Plan** first. The shape:

   > I want <the result>. Use @<file> and @<file>. Done means <what you'll check>. Show me a plan first.

   Read the plan before you accept it: this is where your expertise matters most. Change anything
   you disagree with now, not after.
5. **Predict:** before you send it, write one line on what you expect Claude to do, and one on
   where you think it will go wrong.
6. Run it. Ask for files and scripts, not answers in the chat: they're what you can run again.
   When something works:

   > Commit this with a message saying what changed.

   Reject what you don't want, or ask *"undo the last commit's change"* as in
   [git-safety-net](git-safety-net.md).
7. **Check it** against something you trust: open the files, recount a number, compare with the
   original, or ask Claude to show its evidence and check that yourself.
8. Prepare three sentences for the room: what you asked, what it did, how you checked it. Include
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
