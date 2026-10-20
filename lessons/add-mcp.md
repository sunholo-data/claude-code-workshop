# Add a remote MCP server

**Server:** Google Developer Knowledge — Google's own documentation (Analytics, Tag Manager,
BigQuery, Cloud and more) as tools Claude can search. It runs at Google, so there is nothing to
install: `https://developerknowledge.googleapis.com/mcp`.

**Key:** in the session you use a key lent by the facilitator. It is restricted to this one API
and is revoked after the course. Making your own is the next node, [own-api-key](own-api-key.md).

## Do

1. Ask Claude: *"Create .claude/settings.local.json with an env entry GOOGLE_DK_API_KEY set to
   PASTE-KEY-HERE."* Don't paste the key into the chat: anything in the chat is sent to the model.
2. Open that file yourself and replace `PASTE-KEY-HERE` with your key. In Finder, the `.claude`
   folder is hidden: press **⌘⇧.** (Command, Shift, full stop) to show it. Save.
3. Check it can't reach GitHub: send `!git check-ignore -v .claude/settings.local.json`. It names
   the `.gitignore` line that keeps the file private. Claude itself can't read the file: the
   repo's settings deny it, so the key never enters the chat.
4. Start a new session so the server loads. If it asks whether to use this project's MCP server,
   say yes. `/mcp` lists the servers and whether they connected.
5. **Predict:** ask *"How do I add a custom dimension to a GA4 Data API report?"* What will Claude
   do differently now that the server is there?
6. Ask it. Look for a call to `search_documents` or `answer_query`.

## Proof

An answer where Claude called one of those tools, and you can say which, and what it sent to
Google.

## Misconceptions this exposes

- *"Claude now knows the docs."* It doesn't; it searches them each time, and only when it decides to.
- *"The key is a password for my account."* It identifies a project, not a person. Anyone holding
  it can spend that project's quota, which is why it is restricted and why it is not committed.
