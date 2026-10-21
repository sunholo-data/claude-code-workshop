# Use someone else's skill

A **skill** is a folder of instructions, sometimes with scripts, that teaches Claude one job. Its
author worked out the steps once; you get them by cloning the repository the skill lives in. Here
the job is a slide deck. `presentation-template` carries a skill called `presentation-slides` that
builds self-contained HTML decks with a dark and a light theme, plus a check (a *lint*) for the
layout mistake that most often breaks a slide.

## Do

**Where:** first a session on the `claude-code-workshop` folder, in Manual, to clone. Then a
**+ New** session on the cloned `presentation-template` folder, in Manual. That session has its
own `CLAUDE.md` and skill, and none of the workshop's: no guide, and none of its permission rules,
so Manual asks before every command and edit.

1. Clone the template next to the workshop folder:

   > Clone https://github.com/sunholo-data/presentation-template next to this workshop folder, not inside it.

   **You should see:** a `git clone` request (approve), then `presentation-template` next to
   `claude-code-workshop`.
2. **+ New**, the folder button, **Open folder…**, choose `presentation-template`, and set
   **Manual**. The skill only loads in a session opened on that folder.

   **You should see:** the folder button says `presentation-template`. Type `/` and
   `presentation-slides` is in the list.
3. Open `demo/presenter.html` in your browser (double-click it in Finder or File Explorer) to see a
   finished deck. The arrow keys move between slides; the sun/moon button switches theme.
4. **Predict:** you are going to ask for a deck without naming the skill. Will Claude use it
   anyway? Which files will it open first?
5. Send, with a topic you know well:

   > Build a 3-slide deck in my-deck/ about <something you know well>.

   Watch which files it reads before it writes anything. The skill mentions a `frontend-design`
   skill: you don't have it, and you don't need it. Ignore that line, and say no if Claude offers to
   install it.

   **You should see:** Claude reading `SKILL.md` and its `resources/`, then a request to create a
   file in `my-deck/` (approve).
6. Run the check yourself. The repository's own instructions tell Claude to lint the folder, which
   checks nothing (see below), so name the files. Send:

   ```
   !node .claude/skills/presentation-slides/scripts/lint-slides.mjs my-deck/*.html
   ```

   **You should see:** no output: it passed. A list of `file:line` problems? Ask Claude to fix
   them and run the line again. `node: command not found`? Your laptop has no Node: skip the lint,
   tell the facilitator, and do step 7 carefully.
7. Open your deck in the browser. Switch theme. Then make the window tall and narrow: does anything
   spill off the slide?
8. Record it in the workshop: go back to your session on `claude-code-workshop` (in the sidebar)
   and tell the guide *"I've done use-a-skill"*, with the lint command you ran. `progress.md` lives
   there, not in `presentation-template`.

## Proof

A three-slide deck in `my-deck/`, built with the `presentation-slides` skill, passing its lint, and
the lint command you ran, with the deck's file names in it.

## Misconceptions this exposes

- *"To use a skill I need to know how it works."* You asked in your own words. The skill's
  description matched the request, and Claude did the rest.
- *"The lint passed, so my deck was checked."* Run it with just the folder name, `my-deck`, instead
  of `my-deck/*.html`. It prints nothing and reports success, because it checked no files at all. A
  check that cannot fail tells you nothing.
- *"The skill is installed in Claude now."* It lives in this folder. Open a session on another
  folder and it isn't there.
