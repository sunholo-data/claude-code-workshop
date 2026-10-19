# Plan before acting

For anything bigger than a one-line fix, agree the approach before any file changes. In **Plan**
mode Claude reads what it needs and writes a plan, but edits nothing. You change the plan until
it's right, then approve it and switch to **Manual** or **Accept edits** to let it work.

## Do

1. Set the mode to **Plan**.
2. Ask: *"Add a section to samples/tagging-plan.md describing how we'd track the search event,
   including what must not be recorded."*
3. **Predict:** what will the plan contain? Will it pick up the open question about email
   addresses in search terms on its own?
4. Read the plan. Change at least one thing by telling Claude, for example *"also cover who signs
   off the event"*, or *"no, keep the section under ten lines"*. Ask for the revised plan.
5. When the plan says what you want, approve it, switch to **Manual**, and let Claude carry it
   out. Check the result against the plan.

## Proof

A plan you changed before approving it, and the file that followed it.

## Misconceptions this exposes

- *"Plan mode is slower."* Changing a plan is one sentence. Unpicking edits across several files
  is not.
- *"The plan is Claude's decision."* It is a proposal. The point of this mode is that you edit it.
- *"Once approved, it will follow the plan exactly."* Usually, but check the result against the
  plan, not against your memory of it.
