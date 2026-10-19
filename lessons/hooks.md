# Hooks

A **hook** is a command that Claude Code itself runs at a fixed moment: before a tool is used,
after a file is edited, when Claude finishes, or when it needs you. An instruction in CLAUDE.md or a
skill depends on Claude remembering it; a hook runs every time. Hooks live in settings files, under
`"hooks"`, and run with your own permissions, so read one before you add it. If the hook exits with
code 2, its message goes back to Claude: before a tool runs (`PreToolUse`) that blocks the action;
after it (`PostToolUse`) the change has already happened, and Claude is told what is wrong with it.

## Do

1. Open a session on your `presentation-template` folder from [use-a-skill](use-a-skill.md). Read
   the "Automatic verification" paragraph in `.claude/skills/presentation-slides/SKILL.md`. Then ask:
   *"Is there a `.claude/settings.json` in this repo, and does it have that hook?"*
2. It doesn't. Ask Claude to add this to `.claude/settings.local.json` (keep any rules already
   there), and read it before you approve:
   ```json
   {
     "hooks": {
       "PostToolUse": [
         {
           "matcher": "Write|Edit",
           "hooks": [{ "type": "command",
             "command": "node \"$CLAUDE_PROJECT_DIR\"/.claude/skills/presentation-slides/scripts/lint-slides.mjs" }]
         }
       ]
     }
   }
   ```
   Given no file names, the lint reads the edit Claude just made and checks only the new text.
3. Start a new session so the hook loads.
4. **Predict:** you ask *"In my-deck, make the first slide's title box 40vh tall."* What happens
   after the edit, and who sees the lint's complaint?
5. Ask. Watch for the hook's message in the session, and what Claude does next.

## Proof

A hook that ran: the lint's message in the session, and the fix Claude made in response.

## Misconceptions this exposes

- *"The skill says a hook checks my work, so one does."* A description of a hook is not a hook.
  Look in the settings file.
- *"A hook is a reminder to Claude."* It is a program Claude Code runs whether Claude would have
  thought of it or not. That is the whole point.
- *"When a hook complains, the change is undone."* Not after the fact. A `PostToolUse` hook reports
  on an edit that has already been made; only a `PreToolUse` hook can stop one.
