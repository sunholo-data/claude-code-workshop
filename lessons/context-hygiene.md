# Sessions and context

Everything in a session (your messages, the files Claude read, every command and its output)
sits in its working memory, the context. It has a limit. When it fills, Claude summarises the
conversation and carries on, and detail is lost. Long sessions that wandered across several tasks
get worse: old instructions linger and new ones compete with them. A fresh session with a short,
good brief is often the fastest fix.

## Do

1. Look back at one of your earlier sessions today. How many different things did you ask for in
   it?
2. **Predict:** you start a new session and ask *"carry on with the tagging plan"*. What will
   Claude know about what you did before?
3. Try it: **+ New session**, same folder, send exactly that. What happens?
4. Now write a one-paragraph brief instead: what the task is, which files matter (with `@`), what
   is already done, and what "done" looks like. Start another new session and send it.
5. Know the other tool: typing `/compact` asks Claude to summarise the current session now and
   keep going, which frees room without starting over.

## Proof

A task restarted in a new session from your one-paragraph brief.

## Misconceptions this exposes

- *"It remembers yesterday."* Each session starts empty apart from the folder and any standing
  instructions (that's the next tier, CLAUDE.md).
- *"Longer conversations give it more to go on."* Past a point they give it more to get confused
  by.
- *"A new session loses my work."* The files are still there. Only the conversation is gone.
