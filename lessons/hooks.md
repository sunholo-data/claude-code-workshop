# Hooks

A **hook** is a command that Claude Code itself runs at a fixed moment: before a tool is used,
after a file is edited, when Claude finishes, or when it needs you. An instruction in CLAUDE.md or a
skill depends on Claude remembering it; a hook runs every time. Hooks live in settings files, under
`"hooks"`, and run with your own permissions, so read one before you add it. If the hook exits with
code 2, its message goes back to Claude: before a tool runs (`PreToolUse`) that blocks the action;
after it (`PostToolUse`) the change has already happened, and Claude is told what is wrong with it.

## Do

**Where:** a session on the `presentation-template` folder from [use-a-skill](use-a-skill.md), in
Manual, with your `my-deck/` in it and Node working (the lint ran there). This folder has none of
the workshop's rules.

1. Read the "Automatic verification" paragraph in `.claude/skills/presentation-slides/SKILL.md`.
   Then ask:

   > Is there a .claude/settings.json in this repo, and does it have the hook that SKILL.md describes?

   **You should see:** no: the skill describes a hook that isn't there.
2. Ask Claude to add one to your own settings for this folder, and read it before you approve:

   > Add this to .claude/settings.local.json, keeping anything already in it: {"hooks": {"PostToolUse": [{"matcher": "Write|Edit", "hooks": [{"type": "command", "command": "node \"$CLAUDE_PROJECT_DIR\"/.claude/skills/presentation-slides/scripts/lint-slides.mjs"}]}]}}

   **You should see:** a request to save `.claude/settings.local.json`, with a `"hooks"` block in
   it. Given no file names, the lint reads the edit Claude just made and checks only the new text.
3. **+ New** on `presentation-template`, Manual. Claude Code picks up a hook as you save the file,
   but a new session is a clean test.
4. **Predict:** you'll send the request below. What happens after the edit, and who sees the
   lint's complaint?

   > In my-deck, make the first slide's title box exactly 40vh tall. Use vh, not cqb or any other unit: I'm testing a check that should catch it.

   The insistence matters: the skill forbids `vh`, so asked plainly Claude writes `cqb`, the lint
   finds nothing, and the hook never complains.
5. Send it. Approve the edit.

   **You should see:** after the edit, the hook's message naming the `vh` line, and Claude fixing it
   (probably to `cqb`) without being asked. Nothing? Check step 2 saved, and that `!node --version`
   prints a version.

## Proof

A hook that ran: the lint's message in the session, and the fix Claude made in response.

## Misconceptions this exposes

- *"The skill says a hook checks my work, so one does."* A description of a hook is not a hook.
  Look in the settings file.
- *"A hook is a reminder to Claude."* It is a program Claude Code runs whether Claude would have
  thought of it or not. That is the whole point.
- *"When a hook complains, the change is undone."* Not after the fact. A `PostToolUse` hook reports
  on an edit that has already been made; only a `PreToolUse` hook can stop one.
