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
3. In your `ladder-practice` repository, ask Claude to copy the `permissions` block from
   `settings/starter.json` **in the workshop folder** (`../claude-code-workshop/settings/starter.json`:
   `ladder-practice` is a copy of `samples/` only) into `.claude/settings.json`. Reading outside the
   session's folder will ask first: that's the rules working. Read the result before you approve it.
4. Start a new session there, in **Auto**. Ask for each of the four actions in step 2 (make a
   `.env` file with one made-up line first). Compare with your prediction.
5. Open `.claude/settings.local.json` and find the rule you promoted in the trust-ladder node.
   Decide whether it belongs in the team's file or only in yours.
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
  anything that truly must not happen, take the access away too.
