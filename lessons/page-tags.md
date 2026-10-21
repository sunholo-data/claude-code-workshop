# Check a page's tags

Checking tracking by hand means opening the browser's developer tools, reading the dataLayer, and
filtering the network log for analytics hits. The Code tab has its own **Browser pane**, and
Claude can use it: open a page, read what the page holds, and report which tags fired. No
installs. The skill here is not the reading; it is asking Claude **how it knows** each thing it
reports, because a tool can fail quietly and leave a gap that looks like an answer.

Use a page you are allowed to check: your own organisation's site, or a page your group's data
rule allows. Never a client's site without their say-so.

## Do

**Where:** a session on the `claude-code-workshop` folder, in Manual.

1. Open the Browser pane: **Cmd+Shift+B** on a Mac, **Ctrl+Shift+B** on
   Windows.
2. Ask:

   > Open https://<your site>/ in the Browser pane. What's in window.dataLayer, and which GA4 requests did the page send?

   The first time Claude acts on a site, a card asks you to allow it. Choose **Allow once**.
3. **Predict:** before you read the answer, write down which events you expect in the dataLayer,
   and how many GA4 hits a single page view should send.
4. Read the answer. For each GA4 hit, find the measurement ID (`tid=G-…`) and the event name
   (`en=…`).
5. Ask: *"For each thing you reported, how did you find it: which tool, and did any tool fail?"*
   If the network log came back empty, Claude may have used the page's own record of what it
   loaded instead. That shows each request's address, not whether it succeeded.
6. Clear the pane's cookies (**⋮ → Clear browsing data**), load the page again, and ask the same
   question before you touch the cookie banner. Compare: what changed in the dataLayer, and did
   any hit go out before you consented?

## Proof

The dataLayer events and the GA4 hits on a page you may check, each with how Claude found it.

## Misconceptions this exposes

- *"No hits in the answer means no hits were sent."* A tool that saw nothing and a page that sent
  nothing look the same until you ask how it knows.
- *"It looked at the page, so it saw what my visitors see."* The pane is a browser of its own,
  separate from yours, but not a fresh one: it keeps its cookies between sessions (see **Keep
  cookies** in its **⋮** menu), so a consent choice you clicked there last week still applies.
  Consent, logins and cached choices change what fires.
- *"Seeing the request means it worked."* An address shows a hit was sent, not that it was
  accepted or carried the right values. That needs the payload and the response, which is a job
  for a fuller tool such as the Chrome DevTools MCP server.
