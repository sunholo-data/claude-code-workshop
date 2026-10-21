# Running without you

In the Code tab, **Scheduled** (in the sidebar, or under its **More** menu) runs a task on a
schedule. A **local** task runs on your computer with your files and tools, but only while the app
is open and the computer is awake. A **cloud** task (Anthropic's docs used to call these routines)
runs even when your computer is off, but starts from a fresh copy of a GitHub repository, without
your local files. Either way, the hard part is not the schedule. It is what has to be true before
anything should run with nobody watching:

- it has run correctly **by hand**, several times, with no corrections from you;
- it ends with a **check that can fail**, tried on a small test set whose right answers you know;
- its **permissions** were decided in advance, not granted at 3am by whoever happens to click;
- **someone is told when it fails**, and knows what to do. A notification that it ran is not one
  that it worked.

## Do

**Where:** your `skill-work` folder from [write-a-skill](write-a-skill.md), first in a **+ New**
session in Manual, then in the **Scheduled** page of the sidebar.

1. Run your skill by hand three times, each in a **+ New** session on `skill-work`. If you
   corrected it, it isn't ready. (Done [bigquery-mcp](bigquery-mcp.md)? Its report works too.)
2. Add a check to the skill's instructions:

   > Add a last step to my skill: finish by checking <what a wrong result looks like>, and write the result to runs/<today's date>.md with PASS or FAIL as the first line and one sentence on why. Commit.

3. **Predict:** the first scheduled run needs a permission you haven't given. What happens, and who
   finds out?
4. Click **Scheduled** in the sidebar, then **New task** (if a menu opens, choose **Set up
   manually**). Fill in the name and the instructions, for example *"Run /<your skill>"*. Open
   **Advanced settings** and turn on **Only on this computer**, then choose `skill-work` as the
   **Local folder** and **Manual** as the permission mode. Set the frequency to **Daily** for now,
   and **Create**.

   **You should see:** the task's page, with **Run now**. The labels may differ slightly between
   versions of the app.
5. Click **Run now** and watch. In Manual, a run stops at each permission prompt until you answer:
   choose "always allow" only for what you're happy for it to do every time, forever.

   **You should see:** a new `runs/` file with PASS or FAIL. What you allowed is listed on the task's
   page under **Always allowed**.
6. **Edit** the task and set the frequency to **Hourly**. Keep the app open and the computer awake,
   and come back to **Scheduled** after the hour.
7. Answer in one sentence: if this failed on a day you were away, who would notice, and how?

## Proof

A scheduled run's output: the file it wrote, with its PASS or FAIL line, from a run you didn't
start yourself.

## Misconceptions this exposes

- *"Scheduled means it happens on time."* A local task is skipped while the computer sleeps, and
  runs once to catch up when it wakes, so a 9am task can run at 11pm. Write the instructions for
  that.
- *"It worked while I watched, so it'll work alone."* Alone, a missing permission stalls the run
  until someone answers, and an approval given too freely is used every time.
- *"No news is good news."* Silence can mean it didn't run at all. Decide where failure shows up.
