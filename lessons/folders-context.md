# The folder is the context

Claude can look at anything in the folder you opened, but it doesn't read everything up front. It
reads what seems relevant, and you can make sure it reads the right things by typing `@` and a
file name, which pulls that file into your message. Knowing what it has read is how you judge an
answer.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual.

1. In the message box, type `@` and then `tagging`, and pick `samples/tagging-plan.md` from the
   list. Then type `@` and `daily`, and pick `samples/daily-sessions.csv`.

   **You should see:** both file names in the message box.
2. **Predict:** after the two files, you'll ask the question below. Which part can Claude answer
   from these two files, and which part can't it? What will it do with the part it can't?

   > Why did newsletter signups drop to zero, and what explains the jump in sessions on 19 September?

3. Type that question after the two file names, and send it.

   **You should see:** an answer that finds the rename in the tagging plan. Check what it says
   about 19 September.
4. Then ask:

   > Which files did you read to answer that? What would you need to explain the 19th?

## Proof

An answer to a question that needed both files you @-mentioned, and you can say which part came
from which file.

## Misconceptions this exposes

- *"It can see my whole computer."* It works in the folder you opened. Reaching outside it needs
  your permission.
- *"It read everything in the folder."* It reads what it decides is relevant; `@` makes sure.
- *"If it doesn't know, it will say so."* Sometimes it guesses a reason that sounds plausible.
  Nothing in either file explains the 19th; notice whether it said that or made something up.
