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

1. Find the **Connectors** list in the panel on the right of the Code tab. Which are on? Each one's tools are
   available to Claude in this session.
2. Choose a question you could answer from a source your group's rules allow (a calendar or a
   shared drive folder are typical). Check the rule before you start.
3. **Export route:** put an export or copy of the data in the folder and ask the question with
   `@` on that file. Write down exactly what you gave it.
4. **Predict:** you ask the same question in a new session, with the connector on and no file.
   What will Claude fetch? More than your export, or less?
5. Ask. Expand the tool calls: which tool, with what search terms, and what came back.
6. Say the data path out loud: where the data came from, which tool fetched it, whose account it
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
