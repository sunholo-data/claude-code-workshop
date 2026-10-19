# Spreadsheets and data files

In a chat window you paste a table in and get an answer back, and there is nothing to rerun. In the
Code tab, Claude can write a small **script** that reads the file and does the arithmetic. The
script stays in the folder: you can rerun it when the data changes, read the line that decides what
counts, and hand it to a colleague who wants to check. The practice file is
`samples/daily-sessions.csv`, four weeks of made-up daily figures for a website.

## Do

1. Make a practice folder, copy `samples/daily-sessions.csv` into it, and start a **+ New session**
   on that folder.
2. Ask Claude to **describe** the file before analysing it: its columns, how many rows, the date
   range, and anything that looks odd.
3. **Predict:** you ask *"What is purchases per session on weekdays versus weekends?"* Will Claude
   work it out in its head, or write a script?
4. Ask it, adding: *"Write a script in `scripts/` that I can rerun, and tell me the command to run
   it."* If the language it wants isn't installed, it can check what you have, or install what it
   needs. Read each command before you approve it.
5. Open the script. Find the line that decides which days count as the weekend.
6. Run it yourself with the command Claude gave you, in the terminal pane (**Ctrl+`**).
7. Change one number in the CSV, run it again, and check the result moved the way you expected.
8. Ask for the output as a small table file next to the script, so the numbers have a source.

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
