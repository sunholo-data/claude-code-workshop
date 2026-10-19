# CLAUDE.md — standing instructions

A file called `CLAUDE.md` in the folder is read at the start of every session, so anything you
write there applies without being repeated. This workshop already has one; open it and see what
it tells Claude. For your own experiments use `CLAUDE.local.md` next to it: it is read the same
way and is meant for personal rules, so you don't change the shared file.

## Do

1. **Before.** In a session on this folder, ask: *"What happened to newsletter signups in
   samples/daily-sessions.csv? Give the dates."* Note how it writes dates, and whether it says
   what it read.
2. Create `CLAUDE.local.md` in the workshop folder (ask Claude to, or do it yourself) with one
   rule, for example:
   `- Write dates as "15 Sept 2026", never 2026-09-15. End every answer with "Read:" and the files you read.`
3. **Predict:** you ask the same question again in the same session. Will the rule apply?
4. Try it. Then start a **+ New session** and ask again. What changed, and why?
5. Make the rule worse on purpose (vague, like *"be clear about dates"*) and see what survives.
6. Don't commit `CLAUDE.local.md`; it's yours. Delete the rule or keep it, your choice.

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
