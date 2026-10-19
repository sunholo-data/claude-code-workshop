# Running without you

In the Code tab, **Routines** runs a task on a schedule. A **local** routine runs on your machine
with your files and tools, but only while the app is open and the computer is awake. A **remote**
routine runs in the cloud even when your computer is off, but starts from a fresh copy of the
repository, without your local files. Either way, the hard part is not the schedule. It is what has
to be true before anything should run with nobody watching:

- it has run correctly **by hand**, several times, with no corrections from you;
- it ends with a **check that can fail**, tried on a small test set whose right answers you know;
- its **permissions** were decided in advance, not granted at 3am by whoever happens to click;
- **someone is told when it fails**, and knows what to do. A notification that it ran is not one
  that it worked.

## Do

1. Pick your skill from [write-a-skill](write-a-skill.md), or the report from
   [bigquery-mcp](bigquery-mcp.md). Run it by hand three times. If you corrected
   it, it isn't ready.
2. Add a check to the instructions: *"Finish by checking <what a wrong result looks like>. Write
   the result to `runs/<date>.md` with PASS or FAIL as the first line, and say why."*
3. **Predict:** the first scheduled run needs a permission you haven't given. What happens, and who
   finds out?
4. Click **Routines → New routine → Local**. Fill in the name, the instructions, the folder and the
   permission mode, and set the schedule to **Manual**. Click **Run now** and watch: approve with
   "always allow" only what you're happy for it to do every time, forever.
5. Change the schedule to **Hourly** (or ask Claude for any other timing), keep the app open, and
   come back to the **Scheduled** section in the sidebar.
6. Answer in one sentence: if this failed on a day you were away, who would notice, and how?

## Proof

A scheduled run's output: the file it wrote, with its PASS or FAIL line, from a run you didn't
start yourself.

## Misconceptions this exposes

- *"Scheduled means it happens on time."* A local routine is skipped while the computer sleeps and
  catches up once when it wakes, so a 9am task can run at 11pm. Write the instructions for that.
- *"It worked while I watched, so it'll work alone."* Alone, a missing permission stalls the run
  until someone answers, and an approval given too freely is used every time.
- *"No news is good news."* Silence can mean it didn't run at all. Decide where failure shows up.
