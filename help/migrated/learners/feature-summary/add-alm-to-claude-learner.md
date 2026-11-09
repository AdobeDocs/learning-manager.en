---
description: Add the Adobe Learning Manager server to your own Claude account as a custom connector, sign in, and ask about your learning
jcr-language: en_us
title: Add Adobe Learning Manager to Claude as a learner
exl-id: 31c00b29-4919-48b7-9993-ed3ac358ba5e
---

# Add Adobe Learning Manager to Claude as a learner

## Overview

Use these steps only if your organization hasn't already added the connector for you. If you see an Adobe Learning Manager connector in Claude, select **Connect** instead.

## Add the connector in Claude

1. In Claude, go to **Customize** > **Connectors**.
2. Select **Add** (**+**), and then select **Add custom connector**.
3. Enter a **Name**, such as Adobe Learning Manager.
4. Enter the MCP endpoint URL in **Remote MCP server URL**.
5. Select **Continue**.
6. Under **Authentication**, keep **Sign in now**.
7. Under **OAuth client**, select **Use your own OAuth client**.
8. Enter the client ID in **Client ID**.
9. Enter the secret key in **Client Secret**.
10. Select **Add**.
11. Sign in to Adobe Learning Manager when the sign-in page opens.

After you sign in, the connector shows as connected. Ask a question about your learning. For ideas, view [Sample prompts for learners](/help/migrated/learners/feature-summary/sample-prompts-for-learners.md).

>[!IMPORTANT]
>
>Claude labels the Client Secret field as optional, but Adobe Learning Manager requires it. If you leave it empty or enter a wrong value, sign-in fails with an "Authorization failed" message.

>[!NOTE]
>
>Your requests run with your own permissions. Claude can see only what you can see in Adobe Learning Manager.

## Use a different Adobe Learning Manager account

If your browser already has an active Adobe Learning Manager session, Claude connects to that account without asking for credentials. To connect as a different user, sign out of Adobe Learning Manager first, or use a private browser window.

## Other AI clients

For ChatGPT or another client, the steps differ. See your AI client's documentation for adding a custom connector, and use the same three values from your administrator.

## Troubleshooting

**Sign-in shows an unregistered redirect message.** 
Your administrator must add the Claude domain to **Redirect Domains** for the server. Ask your administrator to add `https://claude.ai`, and try again.

**Claude says authorization failed.** 
Check the secret key for extra spaces or a wrong value. Copy it again from your administrator, remove the connector, and add it again.

**You connected as the wrong user.** 
Disconnect the connector, sign out of Adobe Learning Manager, and connect again in a private browser window.

**Claude asks you to sign in again.** 
Your session expired, or your access was revoked. Select **Connect** to sign in again.
