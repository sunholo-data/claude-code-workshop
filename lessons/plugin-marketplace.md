# Team skills in every folder

Skills in the team repository load only when your session is opened on that folder. A **plugin**
packages the same skills so they load wherever you work, and a **marketplace** is the list your
team installs plugins from: a repository with a `.claude-plugin/marketplace.json` file. The team
repository can be its own marketplace. This node is for whoever looks after the team's tooling.
Adding a marketplace of your own needs the `claude` command line, which the desktop app does not
install for you: the Code tab's **+ → Add plugins** browser installs plugins, but has no documented
way to add a custom marketplace, and `/plugin` doesn't run in the Code tab.

## Do

**Where:** a session on the team skills repository's folder, in Manual, and that session's
terminal pane (**Ctrl** and the backtick key). Then a **+ New** session on a different folder,
such as `claude-code-workshop`.

1. Install the command line, once, in the terminal pane. On a Mac:

   ```
   curl -fsSL https://claude.ai/install.sh | bash
   ```

   On Windows, in PowerShell: `irm https://claude.ai/install.ps1 | iex`. Then close the terminal
   pane, open it again, and run `claude --version`.

   **You should see:** a version number. `command not found`? Follow what the installer printed
   about adding it to your PATH, then open the pane again. Source: code.claude.com/docs/en/quickstart.
2. **Predict:** you open a session on a client folder and ask for something a team skill does.
   Will it be used? Why not?
3. Reorganise the repository on a branch, because moving the skills out of `.claude/skills/` takes
   them away from everyone's sessions on this repository until they install the plugin:

   > Make a branch called plugin-marketplace. Following code.claude.com/docs/en/plugin-marketplaces, reorganise this repository as a marketplace with one plugin called <plugin>: each skill under plugins/<plugin>/skills/<skill>/SKILL.md; plugins/<plugin>/.claude-plugin/plugin.json with the plugin's name and no version field; and .claude-plugin/marketplace.json at the root with a name, an owner, and one entry named <plugin> whose source is "./plugins/<plugin>". Commit.

   Leaving out `version` means each new commit is a new version. If you set one, you must raise it
   on every change, or colleagues keep the old copy.
4. Check it, in the terminal pane:

   ```
   claude plugin validate .
   ```

   **You should see:** *Validation passed*. Then push the branch and open a pull request, as in
   [share-skill-pr](share-skill-pr.md); a reviewer merges it.
5. Once it's merged, add the marketplace and install the plugin for yourself, in every folder, in
   the terminal pane:

   ```
   claude plugin marketplace add <org>/<repo>
   claude plugin install <plugin>@<marketplace> --scope user
   ```

   **You should see:** the plugin installed at user scope. Project or local scope would install it
   for this folder only, and step 6 would fail.
6. **+ New** on a different folder, such as `claude-code-workshop`, and run a team skill as
   `/<plugin>:<skill>`.
7. Find out how a colleague gets your next change, and write it in the repository's README. A
   team's own marketplace doesn't auto-update by default.

## Proof

A team skill run as `/<plugin>:<skill>` from a session on a different folder.

## Misconceptions this exposes

- *"A plugin is a different kind of skill."* It's the same SKILL.md files, packaged so they travel.
- *"Once installed, everyone always has the latest."* Installs are copies. Check how and when
  updates reach people before you rely on it.
- *"The marketplace has to be public."* It can be a private repository that only the team can read.
