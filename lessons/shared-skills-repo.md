# The team's skills repository

The team keeps its skills in one GitHub repository, in `.claude/skills/`. Everyone clones it and
opens sessions on it, so everyone has the same skills. When someone's change is merged on GitHub,
you get it by **pulling**. Your group's address is in the overlay as `shared_skills_repo`, or ask
the facilitator.

## Do

**Where:** first a session on the `claude-code-workshop` folder, to clone; then a **+ New**
session on the team repository's folder, in Manual.

**Facilitator, before the session:** the team repository exists, its address is in the overlay as
`shared_skills_repo`, everyone has Write access and has accepted the invitation, it has at least
one skill in `.claude/skills/`, and someone is ready to merge a small change in step 5.

1. Clone it next to your other work:

   > Read shared_skills_repo in overlay/overlay.yaml and clone that repository next to this workshop folder, not inside it.

   **You should see:** a `git clone` request (approve), then a new folder next to
   `claude-code-workshop`. The overlay line is empty? Ask the facilitator for the address.
2. **+ New**, open the cloned folder, Manual. Run the four checks in
   [clone-branch](clone-branch.md) step 1 here: this is a different repository, so your access to
   it is checked separately. All four must be good.
3. **Predict:** type `/` in the prompt box. Which skills will be listed? Will the skill you wrote
   in [write-a-skill](write-a-skill.md) be among them?
4. Type `/` and look. Then ask:

   > Which skills does this folder have, and when would each one be used?

5. The facilitator merges a small change to one skill on GitHub. **Predict:** before you pull, will
   your session see it?
6. Pull it in:

   > Pull, then show me each commit that came in, with its author and message.

   **You should see:** no prompt (pull is allowed), then at least one commit by someone else. Then
   **+ New** for a fresh session here, and check the changed skill.
7. Open a session on a **different** folder, such as `claude-code-workshop`, and type `/`. Are
   the team's skills there?

## Where this goes next

Skills in a repository work only in sessions on that folder. To have them in every folder, a team
can publish the same skills as a **plugin** through its own **plugin marketplace**: a repository
with a `.claude-plugin/marketplace.json` file listing the plugins, each plugin carrying its own
`skills/` folder. Each person adds the marketplace once (`/plugin marketplace add <org>/<repo>` in a
terminal session, or `claude plugin marketplace add <org>/<repo>` in a shell), then installs the
plugin, in the Code tab under **+ → Add plugins**. Plugin skills are called as
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
