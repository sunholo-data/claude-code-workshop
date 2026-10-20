# Agenda and what each block needs

A six-hour day plus a follow-up session a week later. Times assume 09:00–15:00 with a
30-minute lunch at 12:00 and short breaks on the hour. Every block runs the same way: a demo of at
most ten minutes, hands-on, then the room compares what happened. Node ids refer to
[`tree/tree.yaml`](../tree/tree.yaml).

## How each block runs (online)

The day is seven blocks (`blocks` in the tree). Each one runs the same way:

1. **Slides**, shared on screen. The block's last slide carries a strip, generated from the tree:
   *Finish* (its core boxes), *Done early* (its stretch boxes), and, where there is one, a
   **group prediction**: everyone types an answer in the meeting chat before you run it live.
2. **Hands-on.** Everyone works in their own Code tab, with the guide. Stuck people go to the help
   channel or a side room with a helper.
3. **Regroup** when the board's room view shows most of the group has finished the block (its
   *Regroup signal* row highlights a block once half have). Compare in the chat, then the next
   block's slides.

Block 1 opens with the "Who's here" slide: name and role, what you used AI for last week, what
you'd like it to do, and the email you sign in to Claude with (for the board invite, if it hasn't
gone out yet).

## Core, stretch, homework, advanced

Every node in the tree has a `band`, separate from its tier, saying when it's expected:

<!-- bands:begin -->
| Band | When | Nodes |
|---|---|---|
| **core** | The minimum standard: everyone, on the day, in step with the blocks | `install`, `git-installed`, `get-workshop`, `chat-vs-agent`, `folders-context`, `permissions-review`, `trust-ladder`, `claude-md`, `team-conventions`, `settings-permissions`, `git-safety-net`, `clone-branch`, `use-a-skill`, `room-pr`, `connectors`, `add-mcp`, `real-task` |
| **stretch** | On the day, for whoever finishes a block's core first | `plan-first`, `models`, `context-hygiene`, `settings-tour`, `skill-anatomy`, `verify-output`, `data-files`, `page-tags` |
| **homework** | Everyone, before the follow-up (after any unfinished core) | `write-a-skill`, `own-api-key`, `bigquery-mcp` |
| **follow-up** | Together, in the follow-up | `shared-skills-repo`, `share-skill-pr`, `protect-main`, `skill-routing` |
| **advanced** | Extra routes, for anyone who wants more; never expected | `hooks`, `subagents`, `scheduled`, `local-mcp`, `plugin-marketplace` |
<!-- bands:end -->

The core's estimates add up to more than the day's hands-on time; it fits only because several
nodes run as whole-room blocks. Run each block in step (demo, everyone does the core node), and let
stretch absorb whoever finishes first. The board's room view counts who has reached the core.

## Before the day

| Who | What | Status |
|---|---|---|
| Each participant | Claude Desktop installed and signed in with a paid plan. The rest of setup (`install`, `git-installed`, `get-workshop`) is done together in block 1 | |
| Each participant | A GitHub account. Their GitHub username and the email they sign in to Claude with, sent to the facilitator | |
| Each participant | On Windows: Git for Windows installed. On a Mac, block 1 installs git if it's missing | |
| Each participant | The self-assessment: every node's *I can…* answered yes / partly / no | |
| Each participant | One small, real task they'd like help with. An idea is enough | |
| Organiser | A GitHub organisation, and an empty team skills repository in it (used in the follow-up) | |
| Organiser | The group's data rule in writing: what may and may not go to a model | |
| Facilitator | One Developer Knowledge API key per person, restricted to that API, in a project dedicated to the course so they can all be revoked together | |
| Facilitator | The group overlay in `overlay/` | |
| Facilitator | One connector everyone has on and the group's data rule allows, for the `connectors` box (a calendar or a shared drive folder are typical) | |
| Facilitator | Everyone invited to the progress board **by email** from its Share menu, as **Editor**, with link sharing **turned off**. Anyone outside your organisation can save progress only as an email-invited Editor, and only while the board has no public link. Each invitation opened once | |
| Facilitator | Everyone's GitHub username added to this repository with **Write** access, invitations accepted before the day. `main` is protected by a ruleset: pull requests only, and only admins can merge | |
| Facilitator | For the homework: a GA4 export in BigQuery (a copy of Google's public sample is enough); a **Web application** OAuth client with redirect `https://claude.ai/api/mcp/auth_callback`, consent screen External in testing with participants as test users; each participant (or their domain) granted MCP Tool User and BigQuery Job User on the project and Data Viewer on that one dataset only; a per-user daily query quota. Send the client ID and secret privately. Test it first with an account holding only those grants, in a chat and in the Code tab | Connectors load when the Desktop app starts: after adding one, quit and reopen it |
| Facilitator | A dry run on a clean account, Mac and Windows: Code tab, a skill from a cloned repo, `.mcp.json` with the key from `settings.local.json`, a push refused on `main` | Checked in the Desktop app on 20 Oct: `/mcp` and **+ → Plugins** exist; the mode sticks per folder; connectors and the Trust workspace question sometimes need the app restarted |

## The day

<!-- day:begin -->
| Time | Block | Core; stretch | What it needs |
|---|---|---|---|
| 09:00 | **1 · Setup.** Who's here, in the chat. Then setup together from the shared screen: the Code tab in Manual, git, the workshop cloned, and the guide started in a new session on it. | `install`, `git-installed`, `get-workshop` | Everyone's Claude sign-in email (board invite) and GitHub username (Write access), collected before the day; a helper for installs in a side room |
| 09:30 | **2 · Chat to agent.** Files, the folder as context, permissions and diffs; then trust is earned per action: the same task in Manual, Accept edits and Auto. | `chat-vs-agent`, `folders-context`, `permissions-review`, `trust-ladder`; stretch: `plan-first`, `models`, `context-hygiene`, `data-files` | `samples/`, a practice folder with nothing confidential |
| 10:45 | **3 · Rules.** CLAUDE.md before and after; the group writes its conventions together, data handling first; then the settings that enforce them: allow, ask, deny. | `claude-md`, `team-conventions`, `settings-permissions`; stretch: `settings-tour` | A shared document for the conventions; the group's data rule; `settings/starter.json` |
| 11:30 | **4 · Git.** Commit, see what changed, go back; branch and push to this repository, and watch GitHub refuse a push to `main`. | `git-safety-net`, `clone-branch` | Write access to this repository for everyone; GitHub sign-in working on each laptop (the GitHub CLI on Macs) |
| 12:00 | *Lunch* | | |
| 12:30 | **5 · Skills.** Clone `presentation-template` and build a short deck with its skill. Then one pull request each: a small skill in its own folder. The facilitator merges them all on screen; everyone pulls, types `/`, and runs a colleague's skill. | `use-a-skill`, `room-pr`; stretch: `skill-anatomy` | github.com/sunholo-data/presentation-template; the facilitator signed in to GitHub to merge |
| 13:30 | **6 · Connect.** Pasting an export versus connecting the source; add Google Developer Knowledge with a lent key. | `connectors`, `add-mcp`; stretch: `page-tags` | One connector everyone has on and the data rule allows; the lent API keys, handed to each person privately; `.mcp.json` in this repo; for the stretch box, a web page everyone may check (the group's own site) |
| 14:15 | **7 · One real task.** One real task each, shown to the group: what you asked, what it did, how you checked it. Self-assessment again; homework. | `real-task`; stretch: `verify-output` | The task ideas from the Who's here slide |
<!-- day:end -->

## Homework

- First, any core node you didn't finish on the day.
- Finish your own skill (`write-a-skill`).
- Connect the BigQuery connector and query the GA4 sample read-only (`bigquery-mcp`). Bring the
  error if it doesn't work. Optional: run a GA4 server yourself (`local-mcp`).
- Make your own Developer Knowledge key (`own-api-key`).
- Optional: one advanced box of your choice.
- Bring one thing the conventions got wrong.

## The follow-up

The first half finishes the tree as a team; the second half belongs to the group's own decisions,
which a generic course can't script.

| Block | Nodes | Needs |
|---|---|---|
| Homework back: what broke connecting BigQuery, fixed together; one GA4 question answered as a group | `bigquery-mcp` | Error messages people brought; the connector working on the facilitator's laptop |
| Everyone installs the team skills repository and pulls a change someone else made | `shared-skills-repo` | The repository on the group's own GitHub organisation; everyone with access |
| Each group contributes a skill by pull request; the other group reviews and uses it | `share-skill-pr`, `protect-main` | Named reviewers; a branch rule on `main` if the plan allows it |
| Many skills, one entry point: overlaps found and fixed | `skill-routing` | At least four skills in the repository |
| *Break* | | |
| The group's open decisions, and where its AI work will run | — | The group's own material |

Optional for whoever maintains the tooling: `plugin-marketplace`, so team skills work in every
folder.

## After

- Revoke the lent API keys.
- Remove the group's Write access to this repository, and delete the `practice/` and `skill/` branches.
- Move the group's skills out of `.claude/skills/` into `cohorts/<date>/`, so the next group starts
  with a clean list. Their pull requests stay on GitHub as the record.
