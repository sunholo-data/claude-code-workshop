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
| `permissions.defaultMode` | The mode a new session starts in: `default` is Manual; also `acceptEdits`, `plan`, `auto`. `auto` works only from your own `~/.claude/settings.json` |
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

**Where:** a session on the `claude-code-workshop` folder, in Manual, then **+ New** sessions on a
new, empty folder called `settings-test` next to it.

1. **Predict:** which file does each of these belong in? *Every new folder starts in Manual. Your
   API key. Claude answers in French. Claude may read the team's shared folder of briefs.*
2. Ask:

   > Which settings file does each of these belong in, and why: every new folder starts in Manual; my API key; Claude answers in French; Claude may read the team's shared folder of briefs.

   Compare with your prediction. The key is the one with a fixed answer: `settings.local.json`, as
   in [add-mcp](add-mcp.md).
3. Set a start mode you'll be able to see. Manual may already be what a new session starts in, so
   use Accept edits:

   > Set permissions.defaultMode to acceptEdits in my ~/.claude/settings.json, keeping everything else in it. Then make an empty folder called settings-test next to this workshop folder.

   **You should see:** a prompt to save `~/.claude/settings.json`: it's outside this project, so it
   asks. Read the change, then approve.
4. **+ New**, the folder button, **Open folder…**, choose `settings-test`.

   **You should see:** the mode button says **Accept edits**. Still Manual? Quit Claude Desktop,
   open it again, and start a new session on `settings-test`.
5. Now pick **Manual** in the selector, then **+ New** on `settings-test` again. Which mode does it
   start in this time, and what does that tell you about the selector?

   **You should see:** **Manual**: the mode you picked is remembered for this folder and beats
   `defaultMode` there.
6. Take it out again, so new folders don't save edits without asking. Back in the workshop session:

   > Remove permissions.defaultMode from my ~/.claude/settings.json, keeping everything else.

7. Choose one setting that would help your own work (a default model, the language it answers in,
   a folder outside this one), and ask:

   > Add <the setting> to <the file you chose>, and tell me how to check it worked.

   Start a new session and check it.

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
