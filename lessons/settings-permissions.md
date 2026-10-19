# Settings and allowed commands

Approving the same harmless command twenty times teaches you to click yes without reading. A
settings file lets you decide once instead: an **allow** rule for something that never needs
asking, and a **deny** rule for something that must never happen. Rules are checked deny first,
then ask, then allow, so a deny always wins. There are three files to choose from:
`.claude/settings.json` in a project (committed, shared with everyone), `.claude/settings.local.json`
(you, this project only) and `~/.claude/settings.json` (you, every project). The Code tab reads the
same files as the terminal. The terminal's `/permissions` screen isn't available in the Code tab,
so you edit the file, or ask Claude to.

## Do

1. Open a session on your `presentation-template` folder from [use-a-skill](use-a-skill.md). Run
   the lint once and notice that it asks.
2. Ask Claude to create `.claude/settings.local.json` with one allow rule and one deny rule, and
   read it before you approve:
   ```json
   {
     "permissions": {
       "allow": ["Bash(node .claude/skills/presentation-slides/scripts/lint-slides.mjs *)"],
       "deny": ["Read(./secrets/**)"]
     }
   }
   ```
3. Make a `secrets/` folder with a file inside it holding one made-up line.
4. **Predict:** in a new session, you ask Claude to lint your deck and then to read the file in
   `secrets/`. Which will ask, which will just happen, and which will be refused?
5. Try both. Ask Claude to explain what stopped it.
6. Remove the deny rule, start a new session, and ask again. Then put the rule back.

## Proof

A settings file with one allow and one deny rule, and both seen working.

## Misconceptions this exposes

- *"Writing 'never read the secrets folder' in CLAUDE.md does the same job."* CLAUDE.md shapes what
  Claude tries to do. Permission rules are enforced by Claude Code, whatever the model decides.
- *"A narrow allow can make an exception to a broad deny."* It can't. Deny is checked first.
- *"settings.json and settings.local.json are the same."* One is committed and changes things for
  everyone; the other is yours. Put personal shortcuts in the local one.
