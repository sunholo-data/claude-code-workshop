# Starter settings

`starter.json` is a first set of permission rules for a team that is new to Claude Code. It is
derived from a working practitioner's own settings, cut down for people who are not developers.
This workshop's own `.claude/settings.json` uses these rules too, sets new sessions to start in
**Manual** (`"defaultMode": "default"`), and asks before anyone edits the course files. In the
Desktop app, a mode you pick in the selector is remembered for the folder and beats `defaultMode`
there. Copy the `permissions` block into the team repository's `.claude/settings.json` (shared, committed)
and keep personal additions in `.claude/settings.local.json`. `starter.json` leaves the mode alone; add
`"defaultMode": "default"` to the block if the team wants every session to start in Manual
(see [settings-tour](../lessons/settings-tour.md)).

Rules are checked **deny, then ask, then allow**: the first match wins, so an allow rule can never
open up something a deny or ask rule covers.

## Why each rule sits where it does

| | Rule | Rung | Why |
|---|---|---|---|
| allow | `git add`, `git commit` | automated | Local and undoable. A commit is a save point, not a publication. |
| allow | `git switch`, `git fetch`, `git pull` | automated | Moving between branches and fetching others' work changes nothing anyone else sees. |
| allow | `mkdir`; Google's documentation sites and the Developer Knowledge MCP tools | automated | Read-only or trivially reversible. |
| ask | **`git push`** | proposing, as a ceiling | Pushing publishes: after it, other people see the change. The author of these rules approves every push by hand and has never promoted it. |
| ask | `git checkout`, `git restore`, `git reset`, `git rebase`, `git clean`, `git stash`, `git rm` | proposing | Each can throw away work that isn't committed yet (`git checkout .` discards every change you haven't staged). Use `git switch` to change branch; it is allowed. |
| ask | `rm` | proposing | Deleting is the classic irreversible mistake. |
| ask | `curl` | proposing | It can send data anywhere. Teams with a data-handling rule want to see each one. |
| ask | `gh pr merge` | proposing | Merging is the review decision; it stays with a person. |
| deny | reading `.env` files, `~/.ssh` and `.claude/settings.local.json` | held | Credentials never go to a model. Your API keys live in `settings.local.json`; you edit it, Claude doesn't read it. |
| deny | changing who has access to a Google Cloud project | held | The one change that is hard to notice and expensive to undo. |
| deny | BigQuery's `execute_sql` tool, when the server is added as `bigquery` in `.mcp.json` | held | Google's BigQuery MCP server has a separate `execute_sql_readonly` tool that refuses anything but `SELECT`. Denying the other one leaves Claude only that. A BigQuery **connector** added in claude.ai gets a different tool name, so this rule doesn't reach it; there, read-only comes from Google, through a read-only grant on the dataset. |

**Not needed:** `ls`, `cat`, `grep`, `head`, `find` and read-only `git` (`status`, `diff`, `log`)
already run without asking in every mode, so they need no allow rule.

**Ask rules hold even in Auto mode.** That is the point of them: Auto lets routine work through,
and every rule in the ask list still stops and asks you. Deny rules block in every mode.

**Rules are a guard rail, not a lock.** A rule matches the command as Claude writes it; the same
program run another way can slip past it. For anything that truly must not happen, take the
access away as well: a credential that isn't on the laptop can't leak.

## Differences from the source settings

The source allows `curl` and asks only for `rm -r` and `rm -rf`. For a team starting out, both are
tightened to ask. The source also allows many developer tools (`go`, `make`, `npm`) that a
non-developer team doesn't need.

Source of the rule syntax: code.claude.com/docs/en/permissions (checked 19 Oct 2026).
