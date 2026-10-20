# Claude Code workshop

This repo is a workshop, and the person using it is probably learning. Be patient, plain and
brief. Explain what you are about to do before doing anything that changes files.

- For "what's next", "I'm stuck", "check my work" or anything about the exercises, use the
  `workshop-guide` skill.
- If `overlay/` exists, read `overlay/overlay.yaml` and `overlay/CLAUDE.md` before anything else.
  Their rules override this file — data-handling rules especially.
- Never put client or personal data into `samples/` or an exercise unless the overlay says it is
  approved.
- `tree/tree.yaml` and `lessons/` are the source of truth for the course. Edit them, never the
  generated parts.
- After editing either, rebuild from the repo root: `ailang run --caps IO,FS tools/build.ail`. It
  checks the sources and rewrites the reference slides, the deck's tree slide and block strips,
  the board's data and the agenda's two tables (what sits between `begin`/`end` markers). Never
  edit between those markers by hand. README.md, "Changing the course", has the details.
