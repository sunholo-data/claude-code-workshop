# Connectors and MCP

There are two ways to put data in front of Claude. **Pasting an export:** you download a file and
put it in the folder. Claude sees exactly what you chose, frozen at the moment you exported it.
**Connecting the source:** Claude calls a tool that queries the source live, as you, and decides
for itself what to fetch. Either way, whatever Claude reads goes to the model as part of the
conversation. The difference is who chooses what goes, and how much.

Both routes into the Code tab use the same protocol, MCP. **Connectors** are MCP servers with a
setup screen, connected once for your Claude account and available in your local Code tab sessions.
A project's **`.mcp.json`** lists MCP servers in a file that travels with the folder, so everyone who
opens it gets the same ones. This repository has one; [add-mcp](add-mcp.md) uses it.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual, then a **+ New** session on
the same folder. No API key in this card: connectors sign in with your own account. The key comes
in the next card, [add-mcp](add-mcp.md).

1. See which connectors are on: click **+** next to the message box and choose **Connectors** (it
   may say **Add connectors**). Not there? Try **Settings → Connectors** from your profile menu at
   the bottom left; the app has moved this between versions. Each connector that's on gives Claude its tools in this session.
   If **Google Drive** isn't connected, connect it and sign in with your work Google account.

   **You should see:** **Google Drive** listed as connected. Not listed at all, on a Team or
   Enterprise plan? An Owner has to turn it on for the organisation first: tell the facilitator,
   and use a connector your group's rules allow instead.
2. Pick **one Google Doc** your group's rules allow you to share with a model, such as your own
   notes from an earlier session. Not a client folder, and not a calendar or mailbox: those name
   clients in almost every item. Write down a question whose answer is in that doc.
3. **Export route:** in the doc, **File → Download → Markdown (.md)**. Save it into a folder called
   `exports` inside the workshop folder (make the folder if it isn't there): git ignores it, so the
   export can't be committed to this public repository by accident. Then type `@exports/`, pick
   the file, and ask your question after it:

   > @exports/<your file> <your question>

   **You should see:** an answer from that one file. Write down exactly what you gave it: one file,
   as it was when you downloaded it.
4. **Predict:** you ask the same question in a new session, with no file, so Claude has to use the
   connector. What will it fetch? More than your export, or less?
5. Delete the export, so the next session can't find it in the folder:

   > Delete the file in exports/.

   **You should see:** a prompt for `rm` (deleting is an ask rule): approve it.
6. **+ New**, open `claude-code-workshop`, Manual, and ask the same question without `@`:

   > Using Google Drive, <your question>

   Expand the tool calls: which tool, with what search terms, and what came back. If the results
   show anything your rules don't allow, such as a client document, stop and say so. That is what
   "it reaches what your account reaches" looks like.
7. Say the data path out loud: where the data came from, which tool fetched it, whose account it
   ran as, and where it went next.

## Proof

A question answered from a connected source, with the data path said aloud.

## Misconceptions this exposes

- *"Connecting is safer, because nothing is copied."* What the tool returns goes into the
  conversation just as a paste does, and it may fetch more than you would have exported.
- *"A connector can see everything."* It acts as you, so it reaches what your account reaches. No
  more, but no less either.
- *"Connectors and MCP are different things."* A connector is an MCP server with a setup screen.
  `.mcp.json` is the same idea written into a file that belongs to the project, not to you.
