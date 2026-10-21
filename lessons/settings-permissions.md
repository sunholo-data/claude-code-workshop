# Your rules: allow, ask, deny

The [trust ladder](trust-ladder.md) is something you do with the mode selector and the "don't ask
again" button. A settings file writes it down, so it holds every session and, when it's shared,
for everyone on the team. **Allow** lets an action through without asking. **Ask** stops for you
every time, even in Auto. **Deny** never happens. Rules are checked deny, then ask, then allow,
and the first match wins.

There are three files. `.claude/settings.json` in a project is committed and applies to everyone
who works there: put the team's rules here. `.claude/settings.local.json` is yours for that
project. `~/.claude/settings.json` is yours for every project. The Code tab reads all three. Its
mode selector has no screen for editing rules, so you edit the file, or ask Claude to.

## Do

**Where:** first a session on the `claude-code-workshop` folder, in Manual, to build a folder
called `rules-practice` next to it. Then a **+ New** session on `rules-practice`, in Auto, and
later Manual.

1. Read [settings/README.md](../settings/README.md): one line per rule, saying which rung it puts the
   action on and why.
2. **Predict:** with these rules, which of these will just happen, which will ask, and which will
   be refused? *Commit a change. Push it. Delete a file. Read a file called `.env`.*
3. Build a folder that has something for every rule to act on. In the workshop session, send:

   > Make a folder called rules-practice next to this one. Copy the files in samples/ into it, not the samples folder itself, make it a git repository and commit. Next to it, make an empty repository with git init --bare rules-practice-remote.git and add it to rules-practice as origin, so there is somewhere to push without GitHub. In rules-practice, write a .env file with the one line API_KEY=not-a-real-key and add .env to .gitignore. Last, copy the permissions block from settings/starter.json into rules-practice/.claude/settings.json and commit that.

   Read each command before you approve it. If Claude stops to warn that copying will replace an
   existing permissions block, say: *"This folder is only for practice: replace it."*

   **You should see:** `rules-practice` with `tagging-plan.md` and `daily-sessions.csv` at the top
   (not in a `samples` folder), a `.env`, a `.claude/settings.json`, and two commits. The `.env` is
   written now, from this session, because the workshop's rules don't reach a file outside the
   workshop folder. In a session on `rules-practice`, its own deny rule would stop Claude creating
   it: a deny on reading a file also blocks writing it.
4. **+ New**, the folder button, **Open folder…**, choose `rules-practice`, and set **Auto**. No
   Auto in the selector? Choose **Accept edits**: the ask and deny rules behave the same. If it asks
   whether you trust the folder, say yes: until you do, the file's allow rules wait.
5. Send these one at a time, and compare each with your prediction:

   > Add a line to tagging-plan.md saying "Reviewed in the workshop", and commit it.

   **You should see:** no prompt: committing is allowed.

   > Push it.

   **You should see:** a prompt (push is an ask rule, even in Auto). Approve it. The first push may
   fail with *no upstream branch* and ask a second time, for `git push -u origin …`; approve that
   too.

   > Delete tagging-plan.md.

   **You should see:** a prompt for `rm`. Choose no.

   > Show me what's in .env.

   **You should see:** a refusal: reading `.env` is denied. If Claude then tries another way, such
   as `grep -r` or a small script, note it: that's the third misconception below, live.
6. Switch to **Manual** and ask for something that isn't in the rules:

   > Move daily-sessions.csv into a folder called data.

   When it asks to run the `mv` command, choose **Always allow**.
7. Open `rules-practice/.claude/settings.local.json` yourself, in Finder and a text editor, not by
   asking Claude: reading that file is on the deny list. In Finder the `.claude` folder is hidden:
   press **⌘⇧.** (Command, Shift, full stop) to show it; in File Explorer, **View → Show → Hidden
   items**.

   **You should see:** an `allow` list with the rule you just promoted. Decide whether it belongs in
   the team's file or only in yours.
8. Add one rule of your own for something in your real work that should always ask:

   > Add "Bash(<the command> *)" to the ask list in .claude/settings.json in this folder, and commit.

   **You should see:** a prompt to save the settings file (approve) and a commit. Say out loud why
   it belongs in ask.

## Proof

The settings file in use, one rule you promoted yourself, and the push or the delete you saw it stop.

## Misconceptions this exposes

- *"Writing 'never push without asking' in CLAUDE.md does the same job."* CLAUDE.md shapes what
  Claude tries to do. Permission rules are enforced by Claude Code whatever the model decides.
- *"A narrow allow can make an exception to a broad ask or deny."* It can't. Deny and ask are
  checked first, which is why `git checkout` asks even though moving between branches is safe:
  use `git switch` for that.
- *"My own settings.local.json can switch off a team rule."*  It can add rules, not remove one. A
  deny in the project's `.claude/settings.json` holds whatever your local file says; to lift it,
  change the project file, which is the team's decision.
- *"A deny rule makes something impossible."* It stops the command as Claude writes it. For
  anything that truly must not happen, take the access away too. The deny stops `cat .env` and its
  cousins (`head`, `tail`, `sed`), but not `grep -r` across the folder or a small script that opens
  the file. If Claude reaches `.env` that way in step 5, you've seen this happen.
