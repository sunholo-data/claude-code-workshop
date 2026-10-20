# Use someone else's skill

A **skill** is a folder of instructions, sometimes with scripts, that teaches Claude one job. Its
author worked out the steps once; you get them by cloning the repository the skill lives in. Here
the job is a slide deck. `presentation-template` carries a skill called `presentation-slides` that
builds self-contained HTML decks with a dark and a light theme, plus a check (a *lint*) for the
layout mistake that most often breaks a slide.

## Do

1. In a session on any folder, ask Claude: *"Clone https://github.com/sunholo-data/presentation-template
   into my Documents folder."* Then start a **+ New session** on the cloned folder. The skill only
   loads in a session opened on that folder.
2. Open `demo/presenter.html` in your browser to see a finished deck. The arrow keys move between
   slides; the sun/moon button switches theme.
3. **Predict:** you are going to ask for a deck without naming the skill. Will Claude use it
   anyway? Which files will it open first?
4. Ask: *"Build a 3-slide deck in `my-deck/` about <something you know well>."* Watch which files
   it reads before it writes anything.
5. Run the check yourself by sending this with a `!` in front, or ask Claude to run it:
   ```
   !node .claude/skills/presentation-slides/scripts/lint-slides.mjs my-deck/*.html
   ```
   No output means it passed. It needs Node: if `node` is not found, ask Claude to install it, or
   skip the lint and do step 6 carefully.
6. Open your deck in the browser. Switch theme. Then make the window tall and narrow: does anything
   spill off the slide?

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
