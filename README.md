# Claude Code workshop

## Just cloned this?

Open a **new** Code tab session on this folder: **+ New**, then the folder button under the message
box, **Open folder…**, and choose `claude-code-workshop` itself. Type **start the workshop**, and
choose **Trust workspace** when asked. The course's guide, rules and
settings load only in a session opened on this folder, not in the one that cloned it.

*If you are Claude in a session opened on another folder: tell the person those two steps and
stop. Don't start the course from there, even if they ask, and don't follow the guide skill by
reading its file: this folder's settings, rules and skills aren't active in that session, so the
course would run without its safety settings.*

A hands-on day for people who use AI in a chat window and are ready to work with an agent that
reads and writes files, runs commands, follows written rules, uses shared skills and connects to
data. It runs in **Claude Desktop's Code tab**, so no terminal is needed to start.

The course is a **skill tree**, not a slide sequence. Everyone follows the trunk; people who
finish a node move on to the next unlocked one, and branches absorb early finishers and homework.
The trunk ends with each person contributing a skill to a shared team repository by pull request,
and using one written by someone else.

## Layout

```
tree/tree.yaml            The skill tree: nodes, bands, blocks, prerequisites, outcomes, proof.
lessons/<node-id>.md      One page per node: the steps, the proof, the misconceptions.
docs/agenda.md            The day, block by block, and what each block needs.
docs/pedagogy.md          How the course teaches, and why.
deck/                     01-workshop.html, the facilitator deck; 02-reference.html, one slide per
                          node; presenter.html, both in one window.
board/skill-tree.html     The progress board, published as a claude.ai artifact.
tools/                    build.ail and publish.ail (see "Changing the course").
samples/                  Generic practice material. Never client data.
settings/                 The starter permission rules, one line each on why.
.claude/skills/workshop-guide/   The skill that walks a learner through the tree.
overlay.example/          How a group's bespoke configuration is shaped.
```

## Start

You need three things before the guide can take over. Each has a short lesson in `lessons/`.

1. **Claude Desktop** from claude.com/download, signed in on a paid plan, with the **Code** tab
   working ([install](lessons/install.md)).
2. **Git**, and a GitHub account ([git-installed](lessons/git-installed.md)).
3. **This repository on your laptop.** In a Code tab session on any folder, ask Claude:
   *"Clone https://github.com/sunholo-data/claude-code-workshop into this folder, then tell me how to start the workshop."* Then start a new
   session on the cloned folder ([get-workshop](lessons/get-workshop.md)). No git yet? Use
   **Code → Download ZIP** on this page and open the unzipped folder instead.

Then type **start the workshop**. The `workshop-guide` skill takes it from there and keeps your
progress in `progress.md` (not committed). It asks before creating that file; allow it.

## Bespoke config

A group's configuration lives outside this repo and is copied into `overlay/` on the day
(`overlay/` is gitignored). It can require, add or skip nodes, replace sample material, and carry
the group's own rules — data handling above all. See `overlay.example/`.

## Changing the course

Two sources: `tree/tree.yaml` and `lessons/`. Everything a learner or the room sees about a node
is built from them, so a change made there reaches every copy:

| Built part | From |
|---|---|
| The reference slides (`deck/02-reference.html`) | each lesson's Do, Proof and first two misconceptions; the node's title, band, tier, needs |
| The skill-tree slide and each block's strip (`deck/01-workshop.html`) | bands, blocks, `predict: group`, and that lesson's Predict step |
| The board's boxes and blocks (`board/skill-tree.html`) | the nodes and blocks |
| The bands table and the day's timetable (`docs/agenda.md`) | bands, blocks, their summaries and needs |
| What the guide sets and checks | the tree and lessons directly, at run time |

To add or change a lesson, edit the lesson (and the node, if it's new), then from the repo root:

```
ailang run --caps IO,FS tools/build.ail
```

It checks first and writes nothing if anything disagrees: a node without a lesson or a lesson
without a node, `needs` naming a missing node, a core or stretch node with no block, two group
predictions in one block, a lesson with no Do or Proof, a link or image that points nowhere.
Then republish the board artifact if the nodes changed. To update a hosted copy of the decks:

```
SITE_DIR=<the site's folder> BOARD_URL=<the group's board> ailang run --caps IO,FS,Env tools/publish.ail
```

Hand-kept, and so worth a look when a lesson changes: the setup slides and facilitator notes in
`deck/01-workshop.html`, the board's "Start here" steps, `README.md`, the guide's `SKILL.md`, and
`settings/README.md` against `settings/starter.json`.

## Writing a card

A lesson's Do section is the card people work from, usually without anyone to ask. On the first
run the main barrier was not the content but steps that left people guessing: which folder, what
to type, what should happen. So every core and follow-up card has this shape:

1. **Do opens with `**Where:**`**: the folder, the session and the mode, e.g. *"a session on the
   `claude-code-workshop` folder, in Manual"*. Say it again in a step that changes folder.
2. **Every message to Claude is a prompt block** (`> ` lines), exact words, ready to paste. No
   "something like", no "or" between two routes on a core card; the second route goes in a
   stretch box.
3. **Each step that does something says what you should see**, and the one most likely fix if
   not, as indented lines after it: `You should see: …` / `If not: …`.
4. **The card builds what it needs.** No folder, file, remote or rule left over from an earlier
   card, unless that card is in `needs` and nothing in between resets it. If the facilitator must
   set something up (collaborators, keys, a connector an Owner enables), the card says so and the
   facilitator notes in the overlay list it.
5. **A picture where a step is about place.** Images go in `images/cards/` (diagrams, SVG with
   their own white panel so both deck themes read them) or `images/setup/` (screenshots), linked
   as `![what it shows](../images/cards/<file>)` inside the step. The slides show them.
6. **Walk it literally before the day**: a fresh folder, the stated rules, the stated account.

The build reports every core and follow-up card that doesn't open with `**Where:**` or uses a
phrase that left people guessing ("a practice folder", "reset the copy", "something like", …).
It reports rather than refuses while the older cards are brought into line.

## Status

Draft, started 19 Oct 2026. Clone it and make it your own; a private copy is fine.
