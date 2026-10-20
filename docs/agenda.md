# Agenda and what each block needs

A six-hour day plus a follow-up of about two hours, a week later. Times assume 09:00–15:00 with a
30-minute lunch at 12:00 and short breaks on the hour. Every block runs the same way: a demo of at
most ten minutes, hands-on, then the room compares what happened. Node ids refer to
[`tree/tree.yaml`](../tree/tree.yaml).

## Before the day

| Who | What | Status |
|---|---|---|
| Each participant | Claude Desktop installed, signed in with a paid plan, Code tab working (`install`) | |
| Each participant | Git installed. On a Mac, `xcode-select --install`; on Windows, Git for Windows (`git-installed`) | |
| Each participant | A GitHub account, username sent to the facilitator | |
| Each participant | This repository cloned, a session open on it, and "start the workshop" answered (`get-workshop`) | |
| Each participant | The self-assessment: every node's *I can…* answered yes / partly / no | |
| Each participant | One small, real task they'd like help with. An idea is enough | |
| Organiser | A GitHub organisation, and an empty team skills repository in it | |
| Organiser | The group's data rule in writing: what may and may not go to a model | |
| Facilitator | One Developer Knowledge API key per person, restricted to that API, in a project dedicated to the course so they can all be revoked together | |
| Facilitator | The group overlay in `overlay/` | |
| Facilitator | For the homework: a GA4 export in BigQuery (a copy of Google's public sample is enough), an OAuth client, the BigQuery connector added in claude.ai, and each participant granted query rights on that one dataset | |
| Facilitator | A dry run on a clean account, Mac and Windows: Code tab, a skill from a cloned repo, `.mcp.json` with the key | |

## The day

| Time | Block | Nodes | What it needs in the room |
|---|---|---|---|
| 09:00 | **Welcome.** The tree on the wall; the self-assessment read back as a distribution, not names. Install triage in parallel. | 0 | Tree printout or slide; the collected self-assessments; a spare person on installs |
| 09:30 | **Chat to agent.** Files, the folder as context, permissions and diffs, Plan mode, choosing a model; then **trust is earned per action**: the same task in Manual, Accept edits and Auto, mapped to the delegation ladder. | 1 | `samples/` (a practice folder with nothing confidential); this repo cloned, or downloaded as a ZIP by anyone whose git isn't working yet |
| 10:45 | **Rules.** CLAUDE.md before and after; the group writes its conventions together, data handling first; then the settings that enforce them: allow, ask, deny. | 2 | A shared document or file for the conventions; the group's data rule; `settings/starter.json` |
| 11:30 | **Git.** Commit, see what changed, go back; clone, branch, push. | 3 | GitHub accounts; the team skills repository, which is also the practice repository |
| 12:00 | Lunch | | |
| 12:30 | **Skills.** Clone `presentation-template` and build a short deck with its skill; read how the skill is built; start writing your own. | 4 | github.com/sunholo-data/presentation-template; a browser to view the deck |
| 13:30 | **MCP.** Pasting an export versus connecting the source; add Google Developer Knowledge with a lent key; how to make your own. | 5 | The lent API keys, handed out individually; `.mcp.json` in this repo |
| 14:15 | **One real task each**, shown to the room: what you asked, what it did, how you checked it. Self-assessment again. Homework. | capstone | The task ideas from before the day |

## Homework

- Finish your own skill (`write-a-skill`).
- Connect the BigQuery connector and query the GA4 sample read-only (`bigquery-mcp`). Bring the
  error if it doesn't work. Optional: run a GA4 server yourself (`local-mcp`).
- Make your own Developer Knowledge key (`own-api-key`).
- Optional: one branch node of your choice.
- Bring one thing the conventions got wrong.

## The follow-up (half a day)

The first half finishes the tree as a team; the second half belongs to the group's own decisions,
which a generic course can't script.

| Block | Nodes | Needs |
|---|---|---|
| Homework back: what broke connecting BigQuery, fixed together; one GA4 question answered as a group | `bigquery-mcp` | Error messages people brought; the connector working on the facilitator's laptop |
| Everyone installs the team skills repository and pulls a change someone else made | `shared-skills-repo` | The repository on the group's own GitHub organisation; everyone with access |
| Each group contributes a skill by pull request; the other group reviews and uses it | `share-skill-pr`, `protect-main` | Named reviewers; a branch rule on `main` if the plan allows it |
| Many skills, one entry point: overlaps found and fixed | `skill-routing` | At least four skills in the repository |
| *Lunch* | | |
| The group's open decisions, and where its AI work will run | — | The group's own material |

Optional for whoever maintains the tooling: `plugin-marketplace`, so team skills work in every
folder.

## After

Revoke the lent API keys.
