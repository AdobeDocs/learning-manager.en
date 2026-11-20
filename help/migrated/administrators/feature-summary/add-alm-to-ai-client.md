---
description: Add the Adobe Learning Manager MCP server to your enterprise AI client, such as Claude or ChatGPT Enterprise, so learners can connect to it
jcr-language: en_us
title: Add Adobe Learning Manager to your enterprise AI client
exl-id: d893efb7-dc0d-4a3a-88d6-b315340e5daa
---

# Add Adobe Learning Manager to your enterprise AI client

You need administrator privileges in your AI client. Get the MCP endpoint URL, client ID, and secret key from your Adobe Learning Manager administrator first. View **Configure a Model Context Protocol server** for more details.

## Add the connector

1. Sign in to your enterprise AI client as an administrator.
2. Open the administrator settings for connectors.
3. Add a custom connector that uses the Model Context Protocol.
4. Enter the Adobe Learning Manager MCP endpoint URL.
5. Enter the client ID and the secret key from your Adobe Learning Manager administrator.
6. Save the connector.
7. Make the connector available to your learners.

>[!NOTE]
>
>AI client interfaces change often. If these steps don't match your client, see your AI client vendor's documentation for adding a remote connector.

## Troubleshooting

**Learners don't see the connector.** Confirm that the connector is enabled for the learner's workspace or group.

**Authorization fails when a learner selects Connect.** Check that the client ID and secret key match the values on the **Client credentials** page of the server in Adobe Learning Manager.
