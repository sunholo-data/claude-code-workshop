# What else settings can do

**Optional.** Permission rules are one key in the settings files. The same files decide which mode
and model a session starts in, what language Claude answers in, which folders outside this one it
may use, and more. The skill here is less the keys than the files: which one a setting belongs in.

| File | Whose | Shared? |
|---|---|---|
| `.claude/settings.json` in a project | the team's, for that project | yes, committed with the project |
| `.claude/settings.local.json` in a project | yours, for that project | no, kept out of git |
| `~/.claude/settings.json` | yours, for every project | no, it's on your laptop |

When the same setting is in two files, the more personal one wins: local over the team's, the
team's over your own everywhere-file. Lists, such as permission rules, add up instead.

Settings worth knowing:

| Setting | What it does |
|---|---|
| `permissions.defaultMode` | The mode a new session starts in: `default` is Manual; also `acceptEdits`, `plan`, `auto` |
| `model`, `effortLevel` | The model and effort a new session starts with |
| `language` | Claude answers in this language, for example `"french"` |
| `env` | Variables every session gets, such as an API key |
| `permissions.additionalDirectories` | Folders outside this one that Claude may work in |
| `enabledMcpjsonServers` | Which servers in the project's `.mcp.json` load without asking |
| `attribution` | The co-author line Claude adds to commits and pull requests |
| `hooks` | Your own commands, run at set points: see [hooks](hooks.md) |

The full list is at `code.claude.com/docs/en/settings`. The Desktop app reads the same files.
Its own **Settings → Claude Code** screen holds app things, such as the worktree folder; the
`/config` menu you may see mentioned online is for the terminal only.

## Do

1. **Predict:** which file does each of these belong in? *Every new folder starts in Manual. Your
   API key. Claude answers in French. Claude may read the team's shared folder of briefs.*
2. Ask Claude which file each one belongs in, and why. Compare with your prediction. The key is
   the one with a fixed answer: `settings.local.json`, as in [add-mcp](add-mcp.md).
3. Ask Claude to set `permissions.defaultMode` to `default` in your `~/.claude/settings.json`. That
   file is outside this project, so it asks before saving: read the change, then approve.
4. Make an empty folder and start a new session on it. Which mode does the selector show?
5. Now pick **Accept edits** in the selector and start another session on the same folder. Which
   mode does it start in this time, and what does that tell you about the selector?
6. Ask Claude what else settings can change, and choose one that would help your own work (a
   default model, the language it answers in, a folder outside this one). Put it in the file you
   think it belongs in, start a new session, and check it worked.

## Proof

One setting you added, the file you chose and why, and a new session where you saw it work.

## Misconceptions this exposes

- *"The team's file applies the moment I clone."* Its allow rules, extra folders and most `env`
  values wait until you trust the folder: that's the prompt you met at setup. Its ask and deny
  rules apply straight away.
- *"Edit a setting and the running session follows."* Most settings reload as you save. The model
  is read when a session starts, so a new one is the reliable check.
- *"The setting always wins."* In the Desktop app, a mode you pick in the selector is remembered
  for that folder and beats `defaultMode` there (except Plan, which lasts one session).
- *"Settings and CLAUDE.md do the same job."* CLAUDE.md is advice Claude reads. Settings are
  applied by Claude Code, whatever Claude decides.
