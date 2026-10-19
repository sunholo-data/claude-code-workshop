# Team skills in every folder

Skills in the team repository load only when your session is opened on that folder. A **plugin**
packages the same skills so they load wherever you work, and a **marketplace** is the list your
team installs plugins from: a repository with a `.claude-plugin/marketplace.json` file. The team
repository can be its own marketplace. This node is for whoever looks after the team's tooling; it
uses the `claude` command line, which the desktop app does not install for you.

## Do

1. **Predict:** you open a session on a client folder and ask for something a team skill does.
   Will it be used? Why not?
2. Ask Claude to reorganise the team repository as a marketplace with one plugin, following
   code.claude.com/docs/en/plugin-marketplaces:
   - each skill under `plugins/<plugin>/skills/<skill>/SKILL.md`
   - `plugins/<plugin>/.claude-plugin/plugin.json` with the plugin's `name`
   - `.claude-plugin/marketplace.json` at the root, with a `name`, an `owner`, and one entry whose
     `source` is `"./plugins/<plugin>"`. Keep the entry name and the plugin's name the same.
3. Check it: `claude plugin validate .` should end with *Validation passed*.
4. Add it and install: `claude plugin marketplace add <org>/<repo>`, then
   `claude plugin install <plugin>@<marketplace>`.
5. Open a session on a different folder and run a team skill as `/<plugin>:<skill>`.
6. Find out how a colleague gets your next change, and write it in the repository's README.

## Proof

A team skill run as `/<plugin>:<skill>` from a session on a different folder.

## Misconceptions this exposes

- *"A plugin is a different kind of skill."* It's the same SKILL.md files, packaged so they travel.
- *"Once installed, everyone always has the latest."* Installs are copies. Check how and when
  updates reach people before you rely on it.
- *"The marketplace has to be public."* It can be a private repository that only the team can read.
