# Get the workshop onto your laptop

*In the workshop, the facilitator walks the room through this from the slides. This page is for doing it beforehand, or afterwards on your own.*

The workshop is a folder of files on GitHub. To use it, you need a copy on your laptop and a Code
tab session opened on that copy. You already have the tools: Claude can make the copy for you.
Do this before the day, after `install` and `git-installed`.

## Do

**Where:** first a session on your `claude-test` folder from [install](install.md), in Manual, to
make the copy. Then a **+ New** session on the copy, `claude-code-workshop`, in Manual.

1. In the Code tab, open a session on `claude-test` and check the mode button says **Manual**.
2. **Predict:** you ask Claude to copy the workshop from GitHub. Which command will it want to run,
   and will it ask you first?
3. Send:

   > Clone https://github.com/sunholo-data/claude-code-workshop into this folder, then tell me how to start the workshop.

4. Claude shows you the command (`git clone …`) and asks before running it. Read it, then allow it.

   ![Claude asking to run git clone](../images/setup/git-clone-permission.png)

   The big button may say **Always allow**: that saves a rule, so this command never asks again in
   this folder. Look at the arrow beside it before choosing. Which you pick is your first trust
   decision of the day. Reading approvals is the habit the whole day builds.

   **You should see:** `Cloning into 'claude-code-workshop'…`, then a short answer: start a new
   session on the workshop folder. Asking for the one thing you want next, rather than "what's in
   it?", gets a short answer.
5. Start a new session yourself: **+ New** at the top left. Click the folder button under the
   message box: it still says `claude-test`. Choose **Open folder…**, go into `claude-test`, and
   pick `claude-code-workshop`. Set the mode to **Manual**.

   **You should see:** the folder button says `claude-code-workshop`.
6. **Predict:** what would it mean to trust a folder you hadn't read?
7. You'll see **This workspace isn't trusted**. A folder you downloaded can carry its own Claude
   settings, so Claude asks before using them. Send:

   > start the workshop

   and choose **Trust workspace**: that's what lets the course's guide, rules and settings load.
   If the banner shows but the question never comes, quit Claude Desktop and open it again, then
   go back to this session.

   This folder also lists one MCP server, `google-developer-knowledge`, in its `.mcp.json`. If you
   are asked whether to use it, allow it: you'll use it in block 6, and it does nothing until you
   add a key there. A notice that `GOOGLE_DK_API_KEY` is missing is expected for the same reason;
   ignore it until then.
8. The guide reads the course and offers you somewhere to start. The first time, it asks to create
   `progress.md`, your own record of what you've done. Allow it.

   **You should see:** a short list of where you can start, and `progress.md` in the folder.

### If git isn't working yet

On the GitHub page, click the green **Code** button, then **Download ZIP**. Unzip it and select the
unzipped folder in step 5. Block 2 works the same way up to [trust-ladder](trust-ladder.md), which
needs git, and so does everything after it. Before then, get git working
([git-installed](git-installed.md)), redo step 3, and ask Claude to copy your `progress.md` across
to the new folder.

## Proof

The guide answered **start the workshop** from a session opened on the workshop folder, and
`progress.md` exists in that folder.

## Misconceptions this exposes

- *"Claude is inside GitHub."* Claude works on files on your laptop. GitHub is where the shared
  copy lives; cloning brings a copy down.
- *"One session can see everything."* A session sees the folder you chose. That's why step 5 opens
  a new session on the workshop folder, rather than carrying on in `claude-test`.
