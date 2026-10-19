# GA4 data through BigQuery

GA4 can export every event to BigQuery, Google's data warehouse, and Google runs an MCP server
for BigQuery at `https://bigquery.googleapis.com/mcp`. Connect Claude to it and you can ask
questions of GA4 data in plain language, while Claude writes and runs the SQL. Nothing is installed
on your laptop. Here you use a practice copy of Google's public GA4 sample: the Google Merchandise
Store, November 2020 to January 2021. No client data.

Who can see what is decided by Google Cloud access rights: you can query only the datasets you've
been given access to. That is the data rule enforced, not just written down. Your facilitator
has already set up the connector and given you access.

## Do

1. In claude.ai, open **Settings → Connectors**, find the **BigQuery** connector your team admin
   added, and click **Connect**. Sign in with the Google account your facilitator named.
2. Open a Code tab session on any practice folder. Ask: *"Which BigQuery tools do you have?"*
   You should see a read-only query tool, `execute_sql_readonly`, among them.
3. **Predict:** ask *"In the GA4 sample, what were the top five events in January 2021, and how
   many users triggered each?"* Which tool will Claude use? Roughly how many page views?
4. Run it. Read the SQL Claude wrote before you read the answer: is it counting what you asked?
5. Ask a question you'd ask of a real client, for example where people drop out between viewing
   an item and adding it to the cart. Check one number yourself in the SQL.
6. Ask Claude to list the datasets it can see. Is anything there you shouldn't be able to reach?

## Proof

A read-only query result from the GA4 sample, and one sentence on what left Google to produce it.

## Misconceptions this exposes

- *"The export is the same as the GA4 reports."* It's raw events. Totals won't match the GA4
  screens exactly, and a property only exports from the day the link was set up.
- *"Connected means it can see all our data."* It sees only the datasets you were granted. Adding
  a client's export later is one grant, made after the team's data decision.
- *"Read-only is a promise from Claude."* It is a separate tool that refuses anything but `SELECT`,
  plus a deny rule on the other one in your settings.
