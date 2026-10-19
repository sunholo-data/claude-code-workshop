# A local MCP server on your own data

**Server:** Google Analytics MCP (`github.com/googleanalytics/google-analytics-mcp`). It runs on
your laptop and reads GA4 **as you**: every property your Google account can open, it can open.
Read your group's data rules before you start; this is where they matter most.

Good as homework: the installs take a while, and it is fine to get stuck and bring the error.

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

It prints `Credentials saved to file: [PATH]`. Set that path as `GOOGLE_APPLICATION_CREDENTIALS`,
and your project ID as `GOOGLE_PROJECT_ID`; this repo's `.mcp.json` reads both. Restart and check
`/mcp`.

## Do

1. **Predict:** which accounts and properties will `get_account_summaries` list?
2. Ask Claude to list them. Were you right? Is anything there you should not touch?
3. Ask a question of one property your rules allow. If you have none, use Google's demo account
   (the Google Merchandise Store).

## Proof

A `run_report` result from an allowed property, with the property named, and one sentence on what
left your laptop to produce it.
