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

1. Read [settings/README.md](../settings/README.md): one line per rule, saying which rung it puts the
   action on and why.
2. **Predict:** with these rules, which of these will just happen, which will ask, and which will
   be refused? *Commit a change. Push it. Delete a file. Read a file called `.env`.*
3. Build a fresh practice folder that has something for every rule to act on. In a session on
   the workshop folder, ask Claude:

   > Make a folder called rules-practice next to this one. Copy samples/ into it, make it a git repository and commit. Next to it, make an empty repository with git init --bare rules-practice-remote.git and add it to rules-practice as origin, so there is somewhere to push without GitHub. In rules-practice, write a .env file with the one line API_KEY=not-a-real-key and add .env to .gitignore. Last, copy the permissions block from settings/starter.json into rules-practice/.claude/settings.json and commit that.

   Read the result before you approve it. The order matters: once the rules are in, Claude can't
   even create a `.env`, because a deny on reading a file also blocks writing it.
4. Start a **+ New session** on `rules-practice`, in **Auto**. If it asks whether you trust the
   folder, say yes: until you do, the file's allow rules wait. Then ask, one at a time: *add a line to
   tagging-plan.md and commit it*, *push it*, *delete tagging-plan.md*, *show me
   what's in .env*. Compare with your prediction.
5. Switch to **Manual** and ask for something that isn't in the rules, such as *"move
   daily-sessions.csv into a data folder"*. When it asks, choose **Always allow**. Then open
   `rules-practice/.claude/settings.local.json` yourself, in Finder or an editor, not by asking
   Claude: reading that file is on the deny list. Find the rule you just promoted and decide whether
   it belongs in the team's file or only in yours.
6. Add one rule of your own for something in your real work that should always ask, and say why.

## Proof

The settings file in use, one rule you promoted yourself, and the push or the delete you saw it stop.

## Misconceptions this exposes

- *"Writing 'never push without asking' in CLAUDE.md does the same job."* CLAUDE.md shapes what
  Claude tries to do. Permission rules are enforced by Claude Code whatever the model decides.
- *"A narrow allow can make an exception to a broad ask or deny."* It can't. Deny and ask are
  checked first, which is why `git checkout` asks even though moving between branches is safe:
  use `git switch` for that.
- *"A deny rule makes something impossible."* It stops the command as Claude writes it. For
  anything that truly must not happen, take the access away too. If Claude reaches `.env` some
  other way, such as a shell command, in step 4, you've seen this happen.
