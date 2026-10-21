# Sessions and context

Everything in a session (your messages, the files Claude read, every command and its output)
sits in its working memory, the context. It has a limit. When it fills, Claude summarises the
conversation and carries on, and detail is lost. Long sessions that wandered across several tasks
get worse: old instructions linger and new ones compete with them. A fresh session with a short,
good brief is often the fastest fix.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual, then two **+ New**
sessions on the same folder.

1. Look back at one of your earlier sessions today, in the sidebar. How many different things did
   you ask for in it?
2. **Predict:** you start a new session and ask *"carry on with the tagging plan"*. What will
   Claude know about what you did before: nothing, the files, or your earlier conversation?
3. **+ New**, open `claude-code-workshop`, Manual, and send exactly:

   > carry on with the tagging plan

   **You should see:** Claude reading files to work out what you mean, or asking. It has the folder,
   its `CLAUDE.md`, and any notes it saved for itself, but not your earlier conversation.
4. Now write a one-paragraph brief instead: what the task is, which files matter (with `@`), what
   is already done, and what "done" looks like. For example:

   > I'm adding a section on the search event to @samples/tagging-plan.md. Nothing is written yet. It should say what we record, what we must not record (email addresses typed into search), and who signs it off, in under ten lines. Show me a plan first.

   **+ New** again, same folder, and send your brief.
5. Know the other tool: typing `/compact` asks Claude to summarise the current session now and
   keep going, which frees room without starting over.

## Proof

A task restarted in a new session from your one-paragraph brief.

## Misconceptions this exposes

- *"It remembers yesterday."* A new session doesn't have your earlier conversation. It starts with
  the folder, any standing instructions (that's the next tier, CLAUDE.md), and its own auto
  memory: short notes Claude chose to keep from earlier sessions on this folder. Not what you said.
- *"Longer conversations give it more to go on."* Past a point they give it more to get confused
  by.
- *"A new session loses my work."* The files are still there. Only the conversation is gone.
