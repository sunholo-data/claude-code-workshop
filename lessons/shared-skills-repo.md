# The team's skills repository

The team keeps its skills in one GitHub repository, in `.claude/skills/`. Everyone clones it and
opens sessions on it, so everyone has the same skills. When someone's change is merged on GitHub,
you get it by **pulling**. Your group's address is in the overlay as `shared_skills_repo`, or ask
the facilitator.

## Do

1. Ask Claude to clone the team repository next to your other work, then start a **+ New session**
   on the cloned folder.
2. **Predict:** type `/` in the prompt box. Which skills will be listed? Will your skill from
   [write-a-skill](write-a-skill.md) be among them?
3. Look. Then ask: *"Which skills does this folder have, and when would each one be used?"*
4. The facilitator merges a small change to one skill. Before you pull: will your session see it?
5. Ask Claude to pull, and to show you the commit that came in and who made it. Start a new session
   and check the skill again.
6. Open a session on a **different** folder and type `/`. Are the team's skills there?

## Where this goes next

Skills in a repository work only in sessions on that folder. To have them in every folder, a team
can publish the same skills as a **plugin** through its own **plugin marketplace**: a repository
with a `.claude-plugin/marketplace.json` file listing the plugins, each plugin carrying its own
`skills/` folder. Each person adds the marketplace once (`/plugin marketplace add <org>/<repo>` in a
terminal session, or `claude plugin marketplace add <org>/<repo>` in a shell), then installs the
plugin, in the Code tab under **+ → Plugins → Add plugin**. Plugin skills are called as
`/<plugin>:<skill>`. A team's own marketplace does not update automatically by default; turn
auto-update on for it, or update from the plugin manager. Source: code.claude.com/docs/en/plugins.

## Proof

The shared skills show up in your Code tab session, and you pulled a change someone else made: the
commit and its author, in your log.

## Misconceptions this exposes

- *"Once it's merged on GitHub, I have it."* You have it after you pull. Until then your copy is the
  one you cloned.
- *"Installed means available everywhere."* A repository's skills belong to the folder. The plugin
  route is how a skill follows you between folders.
- *"Pulling will overwrite my work."* Git won't silently throw away uncommitted changes, and work on
  your own branch is untouched. Commit first and it is safe.
