# Make your own API key

The lent key stops working after the course. This makes one you own. You need a Google account
and a Google Cloud project; your organisation may already have one you should use. Ask first.

## In the browser (Cloud console)

1. Open **console.cloud.google.com** and choose the project at the top (or **New project**).
2. **APIs & Services → Library**, search for **Developer Knowledge API**, click **Enable**.
3. **APIs & Services → Credentials → Create credentials → API key.** Copy the key it shows.
4. Click the new key, then under **API restrictions** choose **Restrict key**, tick
   **Developer Knowledge API**, and **Save**. Name it something you'll recognise later.
5. Replace the lent key with yours in `GOOGLE_DK_API_KEY`, restart, and check `/mcp`.

## Or from the command line

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

The server still answers after the lent key is revoked.
