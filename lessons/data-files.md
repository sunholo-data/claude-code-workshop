# Spreadsheets and data files

In a chat window you paste a table in and get an answer back, and there is nothing to rerun. In the
Code tab, Claude can write a small **script** that reads the file and does the arithmetic. The
script stays in the folder: you can rerun it when the data changes, read the line that decides what
counts, and hand it to a colleague who wants to check. The practice file is
`samples/daily-sessions.csv`, four weeks of made-up daily figures for a website.

## Do

**Where:** first a session on the `claude-code-workshop` folder, in Manual, to make a folder
called `data-practice` next to it. Then a **+ New** session on `data-practice`, in Manual. It has
no rules of its own, so Manual asks before every command and edit.

1. In the workshop session, send:

   > Make a folder called data-practice next to this workshop folder, not inside it, and copy samples/daily-sessions.csv into it.

   **You should see:** one or two prompts (approve), then `data-practice` with one file in it.
2. **+ New**, the folder button, **Open folder…**, choose `data-practice`, and set **Manual**.
   **You should see:** the folder button says `data-practice`.
3. Ask Claude to describe the file before analysing it:

   > Describe daily-sessions.csv: its columns, how many rows, the date range, and anything that looks odd.

4. **Predict:** you ask *"What is purchases per session on weekdays versus weekends?"* Will Claude
   work it out in its head, or write a script?
5. Send:

   > What is purchases per session on weekdays versus weekends? Write a script in scripts/ that I can rerun, and tell me the command to run it.

   **You should see:** a new file in `scripts/`, the answer, and a command. If the language it wants
   isn't installed, it will say so and offer to check what you have or install it. Read each
   command before you approve it.
6. Open the script. Find the line that decides which days count as the weekend.
7. Run it yourself: send the command Claude gave you, with a `!` in front.

   **You should see:** the same numbers Claude reported.
8. Open `daily-sessions.csv` in `data-practice`, change one number of purchases, save, and run the
   command again. Did the result move the way you expected?
9. Ask for the output as a small table file next to the script, so the numbers have a source:

   > Make the script also write its results to scripts/results.csv.

10. To record it, go back to the session on `claude-code-workshop` (in the sidebar, or **+ New**
    on that folder) and tell the guide *"I've done data-files"*: `progress.md` lives there, not in
    `data-practice`.

## Proof

A script in the folder that reproduces the numbers: you run it and get the same answer Claude
reported.

## Misconceptions this exposes

- *"Claude reads the numbers the way I do."* Doing sums in its head over many rows is where mistakes
  creep in. A script is exact, and you can read it.
- *"The script is Claude's business."* It is the record of how the number was made, and the part
  you would show a colleague.
- *"Odd data is Claude's to fix."* What to do with a gap or a spike is your decision. Ask it to flag
  them, not to quietly drop or smooth them.
