# Subagents and parallel sessions

Long side-tasks fill the conversation with search results and file contents you'll never look at
again, and a full conversation gets worse ([context-hygiene](context-hygiene.md)). A **subagent** is
a helper Claude starts with a fresh context of its own: it reads and searches, then hands back only
a summary. Claude has some built in, such as **Explore**, which searches without changing anything.
A **second session** (**+ New session**) is the other way to split work: a separate conversation
entirely, which you can run alongside the first. Tick the **worktree** option and it gets its own
copy of the files, so two sessions editing at once don't collide.

## Do

1. In a session on this workshop folder, ask: *"Use a subagent to find every place in this repo
   that mentions an API key. Return a list of file and line, with one sentence each. Don't paste
   file contents back."*
2. **Predict:** of everything the subagent reads, how much will end up in your conversation?
3. Run it. Compare what came back with how much it must have read.
4. Ask a follow-up that needs a detail the subagent saw but didn't report. What does the main
   session do?
5. Start a **+ New session** on the same folder and give it a different side question. Note that
   neither session knows about the other.
6. Bring that answer back yourself: ask the second session to write it to a file, then `@` the file
   in the first.

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
