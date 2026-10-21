# Subagents and parallel sessions

Long side-tasks fill the conversation with search results and file contents you'll never look at
again, and a full conversation gets worse ([context-hygiene](context-hygiene.md)). A **subagent** is
a helper Claude starts with a fresh context of its own: it reads and searches, then hands back only
a summary. Claude has some built in, such as **Explore**, which searches without changing anything.
A **second session** (**+ New**) is the other way to split work: a separate conversation
entirely, which you can run alongside the first. Turn on **Worktree** in the folder menu under the message box and it gets its own
copy of the files, so two sessions editing at once don't collide.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual, then a **+ New** session on
the same folder.

1. **Predict:** you'll send the request below. Of everything the subagent reads, how much will end
   up in your conversation?

   > Use a subagent to find every place in the lessons/ folder that mentions Plan mode. Return a list of file and line, with one sentence each. Don't paste file contents back.

2. Send it.

   **You should see:** a subagent starting (Explore, or another), then a short list. Compare what
   came back with how much it must have read.
3. Ask a follow-up that needs a detail the subagent saw but didn't report, such as:

   > In the second file on that list, what does the sentence just before the mention say?

   What does the main session do: answer, or go and read the file itself?
4. **+ New** on the same folder and give it a different side question:

   > In samples/daily-sessions.csv, which day had the most purchases?

   Note that neither session knows about the other.
5. Bring that answer back yourself: ask the second session to write it to a file, then `@` the file
   in the first:

   > Write that answer to notes/side-answer.md.

## Proof

A research result returned to the main session, and one sentence on what the subagent kept out of
your conversation.

## Misconceptions this exposes

- *"What the subagent learned is now in the main session."* Only its summary is. Say in the request
  what you need back, because the rest is gone.
- *"The subagent knows what we've been discussing."* It starts fresh. Brief it the way you'd brief a
  colleague who just walked in.
- *"More agents means faster."* Every result they return takes room in your conversation, and two
  sessions editing the same files trip over each other without a worktree.
