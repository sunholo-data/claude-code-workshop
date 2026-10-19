# Checking the work

Claude sounds the same whether it is right or wrong. Two habits make the difference. First, ask for
**evidence you can check**: the file and line, the command and its output, the rows a number came
from. Second, check against **something you trust that Claude didn't produce**: a recount, a total
you already know, the original document, or a small set of test cases with known answers. Asking
*"are you sure?"* is not a check; it re-reads its own work.

## Do

1. In this workshop folder, ask: *"From @samples/daily-sessions.csv, what were the total sessions
   and the average newsletter signups per day?"*
2. **Predict:** will both numbers be right? Is there anything in the data that should change how
   you read them?
3. Ask Claude to show its evidence: the calculation it did, and which rows it used.
4. Check one number yourself, in a spreadsheet or by hand on the first week.
5. Ask: *"Is there anything in this data that makes either number misleading?"* Then look at the file
   yourself. Did Claude find what you found?
6. Write down one check you'd want every time this report is made. Ask Claude to turn it into a
   script that prints PASS or FAIL.
7. Make it fail on purpose: run it on a copy of the file with one row broken. Only a check that can
   fail is worth keeping.

## Proof

A check that caught something, and one sentence on what it caught.

## Misconceptions this exposes

- *"It showed its working, so it's right."* Working can be plausible and still wrong. Check one
  step against something independent.
- *"A correct calculation means a correct answer."* The sum can be exact while the data underneath
  is broken. Some checks are about the data, not the arithmetic.
- *"A check that passes is good news."* Only if it could have failed. Test the check before you
  trust it.
