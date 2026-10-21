# How a skill is built

A skill is a folder in `.claude/skills/` with one required file, `SKILL.md`. Read it as a recipe
card in three parts. The **frontmatter**, between the two `---` lines at the top, holds a `name` and
a `description`. Claude has the name and description of every available skill in front of it all
the time, and the description is what makes it pick this one. The **body** below the frontmatter
holds the instructions, which Claude reads only once it uses the skill. Anything else in the folder
travels with it: `resources/` for reference notes the body points to, and `scripts/` for programs
Claude runs rather than reads. A skill in a repository's `.claude/skills/` loads in sessions opened on
that repository or a folder inside it, and in sessions that add the repository with `/add-dir`.
Claude picks up a new or edited skill straight away, without a new session.

## Do

**Where:** your session on the `presentation-template` folder from [use-a-skill](use-a-skill.md),
in Manual, then **+ New** sessions on the same folder.

1. Open `.claude/skills/presentation-slides/SKILL.md` in an editor, or ask:

   > Show me .claude/skills/presentation-slides/SKILL.md, the frontmatter first.

2. Find the three parts. Copy out the description. List the files in `resources/` and `scripts/`,
   and for each one find the sentence in the body that tells Claude when to use it, or note that
   none exists. (At least one file has none: what does that mean for when Claude will open it?)
3. **Predict:** which of these will trigger the skill? *"Make me some slides"*, *"I need something to
   show on the screen on Thursday"*, *"Turn these notes into something I can present."* Write yes or
   no for each.
4. Try each in a **fresh** session (**+ New** on `presentation-template`), so nothing carries over.
   Afterwards, ask:

   > Which skill did you use, if any?

5. Pick a phrase you would really say that missed, or only just hit. Edit the description so it
   covers that phrase, without making it so broad that it fires on any request about a document.
6. **+ New** again and try your phrase. Claude would see the edit in the old session too, but a new
   one is the clean test: nothing from the earlier attempts carries over.

## Proof

The skill's description rewritten so it triggers on a phrase you'd actually use, shown working in a
new session.

## Misconceptions this exposes

- *"Claude reads every skill all the time."* It reads every **description**. The body loads only
  when the skill is used, which is why a folder can carry many skills, and why a vague description
  means a skill that never fires.
- *"The name is what makes it fire."* The name is how you call it directly (`/presentation-slides`).
  Picking it unprompted is the description's job.
- *"The scripts are part of the instructions."* Claude runs them; it doesn't need to read them. That
  is why a script gives the same result every time and an instruction might not.
