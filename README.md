# Claude Code workshop

A hands-on day for people who use AI in a chat window and are ready to work with an agent that
reads and writes files, runs commands, follows written rules, uses shared skills and connects to
data. It runs in **Claude Desktop's Code tab**, so no terminal is needed to start.

The course is a **skill tree**, not a slide sequence. Everyone follows the trunk; people who
finish a node move on to the next unlocked one, and branches absorb early finishers and homework.
The trunk ends with each person contributing a skill to a shared team repository by pull request,
and using one written by someone else.

## Layout

```
tree/tree.yaml            The skill tree: nodes, prerequisites, outcomes, proof. Source of truth.
docs/agenda.md            The day, block by block, and what each block needs.
docs/pedagogy.md          How the course teaches, and why.
lessons/<node-id>.md      One page per node (being written).
samples/                  Generic practice material. Never client data.
deck/                     The facilitator deck (built with the presentation-template skill).
.claude/skills/workshop-guide/   The skill that walks a learner through the tree.
overlay.example/          How a group's bespoke configuration is shaped.
```

## Start

You need three things before the guide can take over. Each has a short lesson in `lessons/`.

1. **Claude Desktop** from claude.com/download, signed in on a paid plan, with the **Code** tab
   working ([install](lessons/install.md)).
2. **Git**, and a GitHub account ([git-installed](lessons/git-installed.md)).
3. **This repository on your laptop.** In a Code tab session on any folder, ask Claude:
   *"Clone https://github.com/sunholo-data/claude-code-workshop into this folder."* Then start a new
   session on the cloned folder ([get-workshop](lessons/get-workshop.md)). No git yet? Use
   **Code → Download ZIP** on this page and open the unzipped folder instead.

Then type **start the workshop**. The `workshop-guide` skill takes it from there and keeps your
progress in `progress.md` (not committed). It asks before creating that file; allow it.

## Bespoke config

A group's configuration lives outside this repo and is copied into `overlay/` on the day
(`overlay/` is gitignored). It can require, add or skip nodes, replace sample material, and carry
the group's own rules — data handling above all. See `overlay.example/`.

## Status

Draft, started 19 Oct 2026. Clone it and make it your own; a private copy is fine.
