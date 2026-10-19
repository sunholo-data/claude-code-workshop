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
| Each participant | The self-assessment: every node's *I can…* answered yes / partly / no | |
| Each participant | One small, real task they'd like help with. An idea is enough | |
| Organiser | A GitHub organisation, and an empty team skills repository in it | |
| Organiser | The group's data rule in writing: what may and may not go to a model | |
| Facilitator | One Developer Knowledge API key per person, restricted to that API, in a project dedicated to the course so they can all be revoked together | |
| Facilitator | The group overlay in `overlay/` | |
| Facilitator | A dry run on a clean account, Mac and Windows: Code tab, a skill from a cloned repo, `.mcp.json` with the key | |

## The day

| Time | Block | Nodes | What it needs in the room |
|---|---|---|---|
| 09:00 | **Welcome.** The tree on the wall; the self-assessment read back as a distribution, not names. Install triage in parallel. | 0 | Tree printout or slide; the collected self-assessments; a spare person on installs |
| 09:30 | **Chat to agent.** Files, the folder as context, permissions and diffs, Plan mode, choosing a model. | 1 | `samples/` (a practice folder with nothing confidential); this repo cloned or downloaded |
| 10:30 | **Rules.** CLAUDE.md before and after; then the group writes its conventions together, data handling first. | 2 | A shared document or file for the conventions; the group's data rule |
| 11:15 | **Git.** Commit, see what changed, go back; clone, branch, push. | 3 | GitHub accounts; the practice repo |
| 12:00 | Lunch | | |
| 12:30 | **Skills.** Clone `presentation-template` and build a short deck with its skill; read how the skill is built; start writing your own. | 4 | github.com/sunholo-data/presentation-template; a browser to view the deck |
| 13:30 | **MCP.** Pasting an export versus connecting the source; add Google Developer Knowledge with a lent key; how to make your own. | 5 | The lent API keys, handed out individually; `.mcp.json` in this repo |
| 14:15 | **One real task each**, shown to the room: what you asked, what it did, how you checked it. Self-assessment again. Homework. | capstone | The task ideas from before the day |

## Homework

- Finish your own skill (`write-a-skill`).
- Install the Google Analytics MCP and run one report from data you are allowed to use
  (`local-mcp`). Bring the error if it doesn't work.
- Make your own Developer Knowledge key (`own-api-key`).
- Optional: one branch node of your choice.
- Bring one thing the conventions got wrong.

## The follow-up (about two hours)

| Block | Nodes | Needs |
|---|---|---|
| Homework back: what broke in `local-mcp`, fixed together | `local-mcp` | Error messages people brought |
| Everyone installs the team skills repository and pulls a change someone else made | `shared-skills-repo` | The repository, everyone with write access to branches |
| Each group contributes a skill by pull request; the other group reviews and uses it | `share-skill-pr` | Named reviewers |
| Many skills, one entry point: where this goes next | `skill-routing` | — |

## After

Revoke the lent API keys.
