# Chat versus agent

In a chat window you paste text in, copy the answer out, and you are the one who changes the file.
In the Code tab Claude opens the file, changes it, and saves it; it can also run commands. That
moves your job from copying to directing and checking. This lesson makes the difference visible
with one small edit.

## Do

1. Open this workshop folder in the Code tab (**This computer**, **Select folder**). Keep the mode on
   **Manual**.
2. Open `samples/tagging-plan.md` yourself and skim it. It is a made-up plan for a made-up shop.
3. **Predict:** you ask *"In samples/tagging-plan.md, mark the search event as Live and add a
   row to the change log for today."* What will Claude do first: answer from memory, or read the
   file? What will it ask you before saving anything?
4. Send it. Watch the steps it shows: reading, then proposing a change. Accept it.
5. Open the file again yourself. Is the change exactly what you asked for, and nothing else?
6. Compare: how would you have done this in a chat window? Count the copy-and-paste steps.

## Proof

Claude edited `samples/tagging-plan.md`, and you opened it afterwards and said what changed.

## Misconceptions this exposes

- *"It will reply with the new text for me to paste."* It changes the file on disk. The reply is
  a report of what it did, which is why you check the file and not only the reply.
- *"It already knows what's in my files."* It reads them when it needs to, in this session. You can
  watch it do so.
- *"If the answer sounds right, the file is right."* Open the file.
