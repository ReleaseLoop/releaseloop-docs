---
title: AI assistants (MCP)
description: Connect ReleaseLoop to ChatGPT or Claude with a sign-in, or to Muse, Grok, and config-file clients with an API key from Settings.
---

An AI assistant can read your ReleaseLoop workspace and create or update releases and tasks. It uses your account, so it can only see and change what you can.

## Where to find it in ReleaseLoop

Open [Settings, then Integrations](https://app.releaseloop.com/settings?tab=integrations). The Integrations tab has three sections, and the one you pick is kept in the page address:

- **AI assistants** (ChatGPT, Claude): sign-in connections, no key needed.
- **API keys** (Muse, Grok, other clients): personal keys for MCP clients.
- **Storage** (Google Drive): see [Google Drive](/integrations/google-drive/).

**AI assistants** opens first. It shows a card for **ChatGPT** and a card for **Claude**. Before you connect, a card has the badge **Official** and the button **Add to ChatGPT** or **Add to Claude**. Once your account has connected that assistant, the badge says **Connected**, the card shows the date, and the button becomes **Open in ChatGPT** or **Open in Claude**.

Below the cards, **Connected assistants** lists every assistant your account has allowed. The last line of the section links to **Create an API key** for Muse, Grok, or another MCP client.

## ChatGPT

The ReleaseLoop connector is available in ChatGPT. It signs in with OAuth. ChatGPT does not use an API key.

1. [Open ReleaseLoop in ChatGPT](https://chatgpt.com/plugins/plugin_asdk_app_6abcdc5d4df081919eff8b8b4fc25240).
2. Sign in to ReleaseLoop if you are asked to. The consent page is titled **Connect your account**.
3. Review what you are allowing, then click **Allow connection**. **Cancel** stops the request.

The consent screen says the assistant wants access to ReleaseLoop as the email you are signed in with. It lists:

- Read artists, releases, tasks and release details.
- Create and update releases and tasks.
- Read contacts and royalties where your account permits.

It also says access covers the workspaces available to your account, and that the assistant tools cannot delete records or process payments.

You can also find the same connector by searching for ReleaseLoop in ChatGPT's apps or connectors. The link above opens the listing directly.

You can also add the server by hand in ChatGPT developer mode: add the server URL `https://mcp.releaseloop.com` and choose OAuth. That path uses the same sign-in and **Allow connection** screen, and it does not need an API key.

After you allow a connection, **Connected assistants** in **Settings**, **Integrations**, **AI assistants** lists it with the date it was connected, and the ChatGPT card shows **Connected**. Click **Revoke**, then confirm with **Revoke access**. The assistant has to ask again before it can connect.

Example requests are on [MCP example prompts](/integrations/mcp-prompts/#chatgpt).

## Claude

ReleaseLoop is an official connector in Claude's directory. It signs in with OAuth, so Claude does not need an API key. This works on claude.ai, Claude Desktop, and the Claude mobile apps.

1. [Open ReleaseLoop in Claude](https://claude.ai/directory/releaseloop).
2. Click **Connect**. Claude opens the same **Connect your account** page described above.
3. Review what you are allowing, then click **Allow connection**.

You can also find it by searching for ReleaseLoop in Claude's **Connectors** settings. On Team and Enterprise plans, an owner may need to enable the connector for the organization first.

If the directory listing is not available to you yet, add it by hand: in Claude, open **Settings**, then **Connectors**, choose **Add custom connector**, and paste `https://mcp.releaseloop.com`. It uses the same sign-in.

The connection then appears under **Connected assistants** in **Settings**, **Integrations**, **AI assistants**, and the Claude card shows **Connected**. **Revoke**, then **Revoke access**, removes it there. You can also disconnect ReleaseLoop from Claude's Connectors settings.

Example requests are on [MCP example prompts](/integrations/mcp-prompts/#claude).

## Create a key

Muse, Grok, and clients configured with a JSON file use a key instead of a sign-in. Claude can use a key this way too, but the sign-in above is simpler.

1. Open [Settings, Integrations, API keys](https://app.releaseloop.com/settings?tab=integrations&section=keys).
2. The card is titled **Keys and setup**. It also shows the **Server URL** with **Copy URL**.
3. Name the key (the field placeholder is "Claude on my laptop") and click **Create key**.
4. Copy the secret. ReleaseLoop shows it once. The dialog title is **Copy this key now**.

The secret starts with `rl_mcp_`. If you lose it, rotate the key on this same screen. The list keeps the name and the prefix. It does not show the secret again.

## Connect Claude, Muse, or Grok

Use this server URL:

```text
https://mcp.releaseloop.com
```

Send this header with every request. Replace `rl_mcp_…` with the secret you copied:

```text
Authorization: Bearer rl_mcp_…
```

The **API keys** section has **Copy URL**, **Copy header**, **Copy config**, and **Copy snippet** for the same config:

```json
{
  "mcpServers": {
    "releaseloop": {
      "type": "http",
      "url": "https://mcp.releaseloop.com",
      "headers": {
        "Authorization": "Bearer rl_mcp_…"
      }
    }
  }
}
```

Restart the client after you save. Ask it to list your workspaces. A successful reply names the workspaces your account belongs to. If you belong to more than one, name the workspace before it writes.

## Revoke or rotate a key

In **Settings**, **Integrations**, **API keys**, each active key has **Rotate** and **Revoke**.

**Revoke** asks you to confirm (**Revoke this key?**). Assistants still holding that key stop on their next request.

**Rotate** issues a new secret, shown once, and the previous secret stops working. Paste the new secret into the client.

## What the assistant can do

It can look up your workspaces, artists, releases, tasks, contacts, and royalty imports. Releases come back newest first, and you can ask for a date range, such as "releases coming up from today" or "everything out in 2025". On one release it can summarize credits, tracks, tasks, marketing, and budget. For royalties, it can open one import and summarize the rows that matched a release. It does not return the raw royalty file.

It can create and update releases and tasks. It cannot delete anything. It will not change deal terms or file links.

If you belong to more than one workspace, name the workspace. The assistant will not guess.

If you are not allowed to see contacts, royalties, marketing, or budget, it tells you that section is hidden. An empty section you are allowed to see means there is nothing there yet.

If you ask it to create the same release or task again, it keeps the first one instead of making a copy.

Release statuses are Draft, Scheduled, Released, and Archived. Task statuses are To do, In progress, Done, and Approved. A phase belongs on a release task.

## Example prompts

See [Example prompts](/integrations/mcp-prompts/) for requests you can paste once the client is connected.
