# Chat versus agent

In a chat window you paste text in, copy the answer out, and you are the one who changes the file.
In the Code tab Claude opens the file, changes it, and saves it; it can also run commands. That
moves your job from copying to directing and checking. This lesson makes the difference visible
with one small edit.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual: the one where you typed
**start the workshop**. If you closed it: **+ New**, the folder button, **Open folder…**, choose
`claude-code-workshop`, and set the mode to **Manual**.

1. Open `samples/tagging-plan.md` yourself, in Finder or File Explorer, and skim it. It is a
   made-up plan for a made-up shop.
2. **Predict:** you send the prompt in step 3. What will Claude do first: answer from memory, or
   read the file? What will it ask you before saving anything?
3. Send:

   > In samples/tagging-plan.md, mark the search event as Live and add a row to the change log for today.

   **You should see:** Claude reading the file, then a proposed change in red and green, and a
   request to save it. Accept it. It asked nothing? Check the mode button says **Manual**.
4. Open the file again yourself. Is the change exactly what you asked for, and nothing else?
5. Compare: how would you have done this in a chat window? Count the copy-and-paste steps.

You'll put `samples/` back as it was at the end of
[permissions-review](permissions-review.md), so leave the change for now.

## Proof

Claude edited `samples/tagging-plan.md`, and you opened it afterwards and said what changed.

## Misconceptions this exposes

- *"It will reply with the new text for me to paste."* It changes the file on disk. The reply is
  a report of what it did, which is why you check the file and not only the reply.
- *"It already knows what's in my files."* It reads them when it needs to, in this session. You can
  watch it do so.
- *"If the answer sounds right, the file is right."* Open the file.
- *"A chat with connectors does the same."* A chat can use connectors too, so it can look things
  up. What's new here is that Claude works on your computer: it writes files, runs commands in the
  terminal and leaves scripts you can run again tomorrow.
