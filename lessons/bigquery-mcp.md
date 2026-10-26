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

Ask your facilitator for these. They send them privately, as a password-manager share, never by
email or chat:

- **Pro or Max only:** the **Client ID** and **Client secret** for the connector. On Team or
  Enterprise they go to your Owner instead, and you never need them. Never paste them into a chat
  with Claude or into this repository.
- The **Google Cloud project ID** the queries run in, and the **dataset** that holds the GA4
  sample, written as `<project>.<dataset>`. Every BigQuery tool needs a project ID; Claude can't
  guess it.
- Which Google account they granted, usually your work account. The grant is three roles on that
  project: **MCP Tool User** (`roles/mcp.toolUser`), **BigQuery Job User**
  (`roles/bigquery.jobUser`) and **BigQuery Data Viewer** (`roles/bigquery.dataViewer`), the last
  ideally on the one dataset. Not **BigQuery User**: that one can create datasets.

Who adds the connector depends on your plan. On **Team** or **Enterprise**, only an Owner can add a
custom connector, in **Organization settings → Connectors**: the facilitator sends the Client ID and
secret to your Owner, and tells you when it's there. Everyone else finds it under
**Customize → Connectors** and clicks **Connect**: skip step 1. On **Pro** or **Max**, you add it
yourself in step 1.

## Do

**Where:** claude.ai settings in the desktop app for steps 1 and 2, then a session on the
`claude-code-workshop` folder, in Manual.

1. **Pro or Max only.** Open **Customize → Connectors**, click **+ Add**, then **Add custom
   connector**. Name it `BigQuery` and set the URL to `https://bigquery.googleapis.com/mcp`. Where
   it asks how to sign in, choose to use your own OAuth client (it may be labelled **Use your own
   OAuth client**) and paste the Client ID and secret. Click **Add**. The labels on this screen
   change often; if yours differ, look for the OAuth client fields.
2. Click **Connect**. Google asks you to sign in: choose the account your facilitator named.
   *"Google hasn't verified this app"* is expected for a practice setup; choose **Continue**, then
   allow BigQuery access.
3. **Quit the Desktop app and open it again**, then open a session on `claude-code-workshop`.
   Click **+** next to the message box, then **Connectors**.

   **You should see:** **BigQuery** in the list, turned on.
4. **Predict:** you'll ask for the top five events in January 2021 and how many users triggered
   each. Which tool will Claude use? Which event do you expect at the top, and roughly how many
   users?
5. Send, with the IDs from your facilitator:

   > Using the BigQuery connector, in project <project ID>, query the dataset <project>.<dataset>: what were the top five events in January 2021, and how many users triggered each?

   The tool calls are labelled **BigQuery: …**; open one and read the SQL before you read the
   answer. Is it counting users, not events, and only January?
6. Ask a question you'd ask of a real client, in the same project and dataset, for example where
   people drop out between viewing an item and adding it to the cart. Check one number yourself in
   the SQL.
7. See what you can reach:

   > Using the BigQuery connector, list the datasets in project <project ID>.

   That lists one project. Is anything there you shouldn't be able to reach?

## Proof

A query result from the GA4 sample through the connector, and one sentence on what left Google to
produce it.

## If it doesn't work

- **"Access blocked" or "this app isn't available" at sign-in.** Your Google account isn't on the
  app's test-user list. Send the facilitator the address you signed in with.
- **Connected, but "does not have permission".** Your account hasn't been granted access yet, or
  you signed in with a different account. Disconnect, then connect again with the right one.
- **No BigQuery in the Code tab.** Quit and reopen the Desktop app (step 3).
- **"projectId is required" or a guessed project.** Name the project ID in the request, as in
  step 5.
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
