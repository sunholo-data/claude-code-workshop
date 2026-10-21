# Make your own API key

The lent key stops working after the course. This makes one you own. You need a Google account
and a Google Cloud project; your organisation may already have one you should use. Ask first.

## Do

**Where:** the Google Cloud console in your browser (or the terminal pane), then a session on the
`claude-code-workshop` folder, in Manual.

1. **Predict:** when you swap your own key in, what will change for Claude, and what for you?

### In the browser (Cloud console)

1. Open **console.cloud.google.com** and choose the project at the top (or **New project**).
2. **APIs & Services → Library**, search for **Developer Knowledge API**, click **Enable**.
3. **APIs & Services → Credentials → Create credentials → API key.** Copy the key it shows.
4. Click the new key, then under **API restrictions** choose **Restrict key**, tick
   **Developer Knowledge API**, and **Save**. Name it something you'll recognise later.
5. Open `.claude/settings.local.json` yourself and replace the lent key with yours (never paste a
   key into the chat). Start a new session and check `/mcp`.

### Or from the command line

This needs `gcloud`, the Google Cloud command line. Check in the terminal pane (**Ctrl** and the
backtick key) with `gcloud --version`. Not found? Install the Google Cloud CLI from
**docs.cloud.google.com/sdk/docs/install**: on Windows, download and run
`GoogleCloudSDKInstaller.exe`; on a Mac, download the archive for your chip (Apple silicon or
Intel), unpack it and run `./google-cloud-sdk/install.sh`, as the page shows. Then close and reopen
the terminal pane, and sign in there with `gcloud auth login`. Run these in the terminal pane:

```
gcloud services enable developerknowledge.googleapis.com --project=PROJECT_ID
gcloud services api-keys create --project=PROJECT_ID --display-name="Developer Knowledge"
gcloud services api-keys update KEY_NAME --api-target=service=developerknowledge.googleapis.com
```

`create` prints a `keyString` (the key) and a `name` (use it as `KEY_NAME`).

## Good habits

- One key per purpose, restricted to one API. Delete keys you no longer use.
- Never paste a key into a file that is committed. `.mcp.json` reads it from the environment
  for that reason.
- Google's page does not state a price; the project has quotas, visible under the API's
  **Quotas** page. Going over returns `429 RESOURCE_EXHAUSTED`.

Source: developers.google.com/knowledge/mcp

## Proof

The server answers with your own key in `settings.local.json` in place of the lent one.

## Misconceptions this exposes

- *"A new key means Claude can do more."* Nothing changes for Claude: the same server, the same
  tools. What changes is who the use is billed to and who can switch it off: you.
- *"An unrestricted key is simpler."* It is, for anyone who finds it: restricted to one API, a
  leaked key can do one thing.
