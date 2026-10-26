# Add a remote MCP server

**Server:** Google Developer Knowledge — Google's own documentation (Analytics, Tag Manager,
BigQuery, Cloud and more) as tools Claude can search. It runs at Google, so there is nothing to
install: `https://developerknowledge.googleapis.com/mcp`.

## You need

- An **API key** for the server. Ask your facilitator: they send it privately, as a
  password-manager share, never by email or chat. It is restricted to this one API and revoked
  after the course. Making your own is the next node, [own-api-key](own-api-key.md).
- Never paste it into the chat: anything in the chat is sent to the model.

**Facilitator:** hand the keys out at the start of this card, not during
[connectors](connectors.md), which needs none.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual, then a **+ New** session on
the same folder.

The key goes in `.claude/settings.local.json`, your own file for this folder, which git ignores.
You edit it yourself: the workshop's rules deny Claude reading that file, and a deny on reading
also stops Claude writing or creating it.

1. Get the lines to add, without Claude touching the file:

   > Print the JSON that sets the env variable GOOGLE_DK_API_KEY to PASTE-KEY-HERE in a Claude Code settings file. Don't open or create .claude/settings.local.json: I'll edit it myself.

   **You should see:** a short block like this, and no request to save anything:

   ```json
   {
     "env": {
       "GOOGLE_DK_API_KEY": "PASTE-KEY-HERE"
     }
   }
   ```

2. Show hidden files, then open the folder. In Finder the `.claude` folder is hidden: press
   **⌘⇧.** (Command, Shift, full stop). In File Explorer: **View → Show → Hidden items**. Open
   `claude-code-workshop/.claude/`.
   - **`settings.local.json` is there** (it usually is: approving a rule or the MCP server writes
     it). Open it in TextEdit or Notepad. After the very first `{`, add this line, comma included:
     `"env": { "GOOGLE_DK_API_KEY": "PASTE-KEY-HERE" },`
   - **It isn't there.** In TextEdit (**Format → Make Plain Text**) or Notepad, paste the block
     from step 1 and save it in `.claude` as `settings.local.json`. TextEdit asks about the
     extension: choose **Use .json**. Notepad: **Save as type** → **All files**.

   Then select `PASTE-KEY-HERE` and paste your key over it, keeping the quotes. Save.

   If the file has a `"disabledMcpjsonServers"` line naming `google-developer-knowledge`, you
   declined the server at setup: delete that name from the list (or the whole line, if it was the
   only one), and save.
3. Check the file can't reach GitHub:

   ```
   !git check-ignore -v .claude/settings.local.json
   ```

   **You should see:** the `.gitignore` line that keeps the file private. Nothing printed? Stop and
   tell the facilitator before you commit anything.

   The deny rule stops Claude opening the file, or printing it with `cat`, but not a search across
   the whole folder (`grep -r`), which reads every file. Don't ask Claude to search the folder for
   the key.
4. **+ New**, open `claude-code-workshop`, Manual, so the server loads with the key. If it asks
   whether to use this project's MCP server `google-developer-knowledge`, allow it. A new server
   only shows up once the session has started properly, so send any short message first (*"hi"*
   will do). Then ask:

   > Which tools do you have from the google-developer-knowledge server?

   **You should see:** `search_documents`, `answer_query` (and possibly `get_documents`). None? Check
   the file saved as `settings.local.json`, not `.txt`, and that the quotes around the key are
   straight, not curly.
5. **Predict:** you'll ask the question below. What will Claude do differently now that the server
   is there?

   > How do I add a custom dimension to a GA4 Data API report?

6. Send it. Expand the tool calls.

   **You should see:** a call to `search_documents` or `answer_query`, and what it sent to Google.
   No tool call, just an answer? Claude answered from what it already knew. Ask again, starting
   with *"Using Google Developer Knowledge,"*. Having a tool doesn't mean it gets used: when the
   source matters, name it.

## Proof

An answer where Claude called one of those tools, and you can say which, and what it sent to
Google.

## Misconceptions this exposes

- *"Claude now knows the docs."* It doesn't; it searches them each time, and only when it decides to.
- *"The key is a password for my account."* It identifies a project, not a person. Anyone holding
  it can spend that project's quota, which is why it is restricted and why it is not committed.
