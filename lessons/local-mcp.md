# Run a GA4 server yourself

**Optional.** The [BigQuery route](bigquery-mcp.md) is the easy way to GA4 data. This branch is for
anyone who wants GA4's own reports rather than the export, or wants to run a server on their own
laptop. It reads GA4 **as you**: every property your Google account can open, it can open,
client properties included. Read your group's data rules before you start.

Two options, both needing a Google Cloud project with the **Google Analytics Admin API** and
**Google Analytics Data API** enabled, and an OAuth client of type *Desktop app*:

- **Google's official server** (`github.com/googleanalytics/google-analytics-mcp`): read-only by
  design. Needs `uv` and `gcloud`. Steps below.
- **A GA4 command-line tool with a skill**, such as `github.com/daidalytics/google-analytics-cli`:
  needs only `uv`, but its own login asks for **edit and user-management rights** as well as read.
  Add deny rules for its delete, create, update and access commands before you use it, or log in
  read-only through `gcloud` as its README describes.

## You need

- `uv`, which runs the server and brings its own Python: `uvx analytics-mcp`
- `gcloud`, the Google Cloud command line, for the one-time login
- An OAuth client file, from your facilitator or your organisation's Cloud project. That project
  needs the **Google Analytics Admin API** and **Google Analytics Data API** enabled.

Ask Claude to install `uv` and `gcloud` for you. Read each command before you approve it.

## Log in once

```
gcloud auth application-default login \
  --scopes https://www.googleapis.com/auth/analytics.readonly,https://www.googleapis.com/auth/cloud-platform \
  --client-id-file=PATH_TO_CLIENT_FILE
```

Type it in the terminal pane (**Ctrl** and the backtick key), not with `!`: it opens a browser to sign you in, and
nothing about a sign-in belongs in the conversation. It prints `Credentials saved to file: [PATH]`. Then, in a session on your
`workshop-practice` folder from [git-safety-net](git-safety-net.md), not on the workshop clone (its
`.mcp.json` is tracked and public, and this one names a file on your laptop), ask:

> Add an MCP server called analytics-mcp to .mcp.json in this folder: command uvx, argument analytics-mcp, with the env variable GOOGLE_APPLICATION_CREDENTIALS set to <the path it printed>. Don't commit it.

Then **+ New** on `workshop-practice`, allow the project's MCP server if asked, and ask Claude which
tools it has from `analytics-mcp`. (Google's README also shows a `GOOGLE_PROJECT_ID`; the server
doesn't read it.)

## Do

**Where:** a session on `workshop-practice`, in Manual, with the server added as above.

1. **Predict:** which accounts and properties will `get_account_summaries` list?
2. Ask Claude to list them. Were you right? Is anything there you should not touch?
3. Ask a question of one property your rules allow. If you have none, use Google's demo account,
   the Google Merchandise Store. It only appears after you add it: open
   support.google.com/analytics/answer/6367342, click the **Google Merchandise Store** link while
   signed in with the same Google account, then ask Claude to list the properties again.

## Proof

A GA4 report from a property your group's rules allow, with the property named, and what your
sign-in could reach.

## Misconceptions this exposes

- *"It's the same access as the BigQuery connector."* The connector reaches one dataset someone
  granted you. This server reaches every GA4 property your Google account can open.
- *"Running it locally keeps the data local."* The server runs on your laptop, but the report it
  fetches still goes to Claude to answer your question.
