# Permissions and reviewing changes

The selector next to the send button sets how much Claude may do without asking. **Manual** asks
before every file edit and command, and shows you the change first. **Accept edits** saves file
edits without asking but still asks before most commands. **Plan** changes nothing and proposes
an approach. **Auto** runs without routine prompts while a background check blocks risky actions.
Whatever the mode, a change you didn't want is yours to refuse.

## Do

1. Set the mode to **Manual**.
2. Ask: *"Tidy up samples/tagging-plan.md."* That is deliberately vague.
3. **Predict:** what will "tidy" mean to Claude? Which lines will it touch?
4. Read the diff it shows before deciding: red is removed, green is added. Look for anything you
   didn't ask for, such as a reworded open question or a changed date.
5. Click **Reject** on at least one change, and say out loud why.
6. Claude will ask how to proceed. Tell it precisely what you do want, and accept that.
7. Switch to **Accept edits**, ask for one more small change, then click the `+N -N` indicator
   that appears to review it after the fact.

## Proof

One change rejected and re-asked, with the reason said aloud.

## Misconceptions this exposes

- *"Accepting is a formality."* The diff is the one moment you see exactly what will change.
  Reading it is the job.
- *"Rejecting means starting again."* Claude keeps the conversation and asks what you want
  instead.
- *"Auto means it does whatever it likes."* It still blocks actions a classifier judges risky,
  but it won't ask about routine ones, so you review afterwards rather than before.
