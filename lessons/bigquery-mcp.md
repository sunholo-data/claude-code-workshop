# GA4 data through BigQuery

GA4 can export every event to BigQuery, Google's data warehouse, and Google runs an MCP server
for BigQuery at `https://bigquery.googleapis.com/mcp`. Connect Claude to it and you can ask
questions of GA4 data in plain language, while Claude writes and runs the SQL. Nothing is installed
on your laptop. Here you use a practice copy of Google's public GA4 sample: the Google Merchandise
Store, November 2020 to January 2021. No client data.

You add it as a **connector** in claude.ai, signed in with your own Google account. Every query
then runs as you, and Google Cloud decides what you can reach: your facilitator gave your account
read access to that one dataset and nothing else. That is the data rule enforced by Google, not
just written down.

## You need

- The **Client ID** and **Client secret** for the connector. Your facilitator sends them to you
  privately. Never paste them into a chat with Claude or into this repository.
- The Google account your facilitator granted access to, usually your work account.

If your organisation's admin has already added BigQuery for everyone, skip step 1 and click
**Connect** on it instead.

## Do

1. In claude.ai, open **Settings → Connectors → Add custom connector**. Name it `BigQuery`, set the
   URL to `https://bigquery.googleapis.com/mcp`, open **Advanced settings**, and paste the Client
   ID and secret. Click **Add**.
2. Click **Connect**. Google asks you to sign in: choose the account your facilitator named.
   *"Google hasn't verified this app"* is expected for a practice setup; choose **Continue**, then
   allow BigQuery access.
3. **Quit the Desktop app and open it again.** It reads your connectors when it starts, so one you
   added while it was open isn't there yet.
4. Start a new Code tab session on your practice folder. Check that **BigQuery** is in the
   **Connectors** list on the right.
5. **Predict:** ask *"Using the BigQuery connector, what were the top five events in the GA4 sample
   in January 2021, and how many users triggered each?"* Which tool will Claude use? Roughly how
   many page views?
6. Run it. The tool calls are labelled **BigQuery: …**; open one and read the SQL before you read
   the answer. Is it counting what you asked?
7. Ask a question you'd ask of a real client, for example where people drop out between viewing
   an item and adding it to the cart. Check one number yourself in the SQL.
8. Ask Claude to list the datasets it can see. Is anything there you shouldn't be able to reach?

## Proof

A query result from the GA4 sample through the connector, and one sentence on what left Google to
produce it.

## If it doesn't work

- **"Access blocked" or "this app isn't available" at sign-in.** Your Google account isn't on the
  app's test-user list. Send the facilitator the address you signed in with.
- **Connected, but "does not have permission".** Your account hasn't been granted access yet, or
  you signed in with a different account. Disconnect, then connect again with the right one.
- **No BigQuery in the Code tab.** Quit and reopen the Desktop app (step 3).
- **Claude runs a `bq` command instead.** You have Google's command-line tools installed, and Claude
  reached for them. Say *"use the BigQuery connector, not the command line"*.

## Misconceptions this exposes

- *"The export is the same as the GA4 reports."* It's raw events. Totals won't match the GA4
  screens exactly, and a property only exports from the day the link was set up.
- *"Connected means it can see all our data."* It sees only the datasets your account was granted.
  Adding a client's export later is one grant, made after the team's data decision.
- *"Read-only is a promise from Claude."* It's Google's: your account can read this dataset and
  write nowhere, whatever SQL Claude writes. Ask Claude to create a table and watch it fail.
- *"The connector is Claude's access."* It's yours. Claude borrows your sign-in, so it can reach
  what you can and nothing more. That's why the grant is made to you.
