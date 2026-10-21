# Permissions and reviewing changes

The selector next to the send button sets how much Claude may do without asking. **Manual** asks
before every file edit and every command that changes something, and shows you the change first;
reading files and read-only commands such as `ls`, `grep` or `git status` run without asking. **Accept edits** saves file
edits without asking but still asks before most commands. **Plan** changes nothing and proposes
an approach. **Auto** runs without routine prompts while a background check blocks risky actions.
Whatever the mode, a change you didn't want is yours to refuse.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual.

1. Check the mode button under the message box says **Manual**.
2. **Predict:** you'll send the deliberately vague prompt below. What will "tidy" mean to Claude?
   Which lines will it touch?

   > Tidy up samples/tagging-plan.md.

3. Send it. Read the diff before deciding: red is removed, green is added. Look for anything you
   didn't ask for, such as a reworded open question or a changed date.

   **You should see:** a proposed change and a request to save it. Nothing to review because it
   saved straight away? The mode isn't Manual: set it and ask again. Claude lists a few options
   and asks which you want, instead of editing? That's a fair answer to a vague request: pick one,
   and it will propose the change.
4. Click **Reject** on at least one change, and say out loud why.

   **You should see:** Claude asking how to proceed. Tell it precisely what you do want, such as:

   > Only fix the formatting of the table. Don't change any wording or dates.

   and accept that.
5. Switch the mode to **Accept edits** and send:

   > In samples/tagging-plan.md, change "Last reviewed" to today's date.

   **You should see:** the file saved without a prompt, and a `+N -N` indicator. Click it to review
   the change after the fact.
6. Put `samples/` back as it was, so later exercises start from the original files. Switch back
   to **Manual** and send:

   > Put the samples folder back exactly as it was in the last commit, with git restore samples/.

   **You should see:** a request to run `git restore samples/` (it's an ask rule: approve it),
   then no changes in `samples/`. Check with `!git status`.

## Proof

One change rejected and re-asked, with the reason said aloud.

## Misconceptions this exposes

- *"Accepting is a formality."* The diff is the one moment you see exactly what will change.
  Reading it is the job.
- *"Rejecting means starting again."* Claude keeps the conversation and asks what you want
  instead.
- *"Auto means it does whatever it likes."* It still blocks actions a classifier judges risky,
  but it won't ask about routine ones, so you review afterwards rather than before.
