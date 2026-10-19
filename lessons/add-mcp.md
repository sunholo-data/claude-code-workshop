# Add a remote MCP server

**Server:** Google Developer Knowledge — Google's own documentation (Analytics, Tag Manager,
BigQuery, Cloud and more) as tools Claude can search. It runs at Google, so there is nothing to
install: `https://developerknowledge.googleapis.com/mcp`.

**Key:** in the session you use a key lent by the facilitator. It is restricted to this one API
and is revoked after the course. Making your own is the next node, [own-api-key](own-api-key.md).

## Do

1. Set the key where this repo's `.mcp.json` can read it, as `GOOGLE_DK_API_KEY`. Ask Claude how,
   and watch what it changes.
2. Restart the session so the server loads. `/mcp` lists the servers and whether they connected.
3. **Predict:** ask *"How do I add a custom dimension to a GA4 Data API report?"* What will Claude
   do differently now that the server is there?
4. Ask it. Look for a call to `search_documents` or `answer_query`.

## Proof

An answer where Claude called one of those tools, and you can say which, and what it sent to
Google.

## Misconceptions this exposes

- *"Claude now knows the docs."* It doesn't; it searches them each time, and only when it decides to.
- *"The key is a password for my account."* It identifies a project, not a person. Anyone holding
  it can spend that project's quota, which is why it is restricted and why it is not committed.
