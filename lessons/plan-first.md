# Plan before acting

For anything bigger than a one-line fix, agree the approach before any file changes. In **Plan**
mode Claude reads what it needs and writes a plan, but edits nothing. You change the plan until
it's right, then approve it and switch to **Manual** or **Accept edits** to let it work.

## Do

**Where:** a session on the `claude-code-workshop` folder, in **Plan**.

1. Set the mode button to **Plan**.
2. **Predict:** you'll send the prompt below. What will the plan contain? Will it pick up the open
   question about email addresses in search terms on its own?

   > Add a section to samples/tagging-plan.md describing how we'd track the search event, including what must not be recorded.

3. Send it.

   **You should see:** Claude reading the file, then a plan. No edit and no save prompt: Plan
   changes nothing.
4. Read the plan. Change at least one thing, then ask for the revised plan:

   > Also cover who signs off the event, and keep the new section under ten lines. Show me the revised plan.

5. When the plan says what you want, approve it. Of the options offered, choose the one that keeps
   you approving each edit: it may be labelled **Yes, manually approve edits**. Don't choose the
   one that switches to **Auto** or auto-accepts edits.

   **You should see:** a save prompt for the edit, before anything is saved. If the mode button
   says **Auto** or **Accept edits**, set it to **Manual**. Check the result against the plan, not
   against your memory of it.
6. Put `samples/` back as it was, so later exercises start from the original files:

   > Put the samples folder back exactly as it was in the last commit, with git restore samples/.

   **You should see:** a request to run `git restore samples/` (approve it), then no changes in
   `samples/`.

## Proof

A plan you changed before approving it, and the file that followed it.

## Misconceptions this exposes

- *"Plan mode is slower."* Changing a plan is one sentence. Unpicking edits across several files
  is not.
- *"The plan is Claude's decision."* It is a proposal. The point of this mode is that you edit it.
- *"Once approved, it will follow the plan exactly."* Usually, but check the result against the
  plan, not against your memory of it.
