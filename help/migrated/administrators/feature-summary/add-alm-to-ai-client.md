---
description: Register the Adobe Learning Manager MCP server as a connector in your enterprise AI client, so that learners in your organization can connect and query their learning.
jcr-language: en_us
title: Add Adobe Learning Manager to your enterprise AI client
exl-id: d893efb7-dc0d-4a3a-88d6-b315340e5daa
---

# Add Adobe Learning Manager to your enterprise AI client

## Overview

You need administrator privileges in your AI client. Before you begin, obtain the MCP endpoint URL, client ID and secret key from your Adobe Learning Manager Administrator. Learn more about [configure a Model Context Protocol server](/help/migrated/administrators/feature-summary/configure-mcp-admin.md).

## Add the connector

1. Sign in to your enterprise AI client as an Administrator.
2. Open the Administrator settings for connectors.
3. Add a custom connector that uses the Model Context Protocol.
4. Enter the Adobe Learning Manager MCP endpoint URL.
5. Enter the client ID and the secret key from your Adobe Learning Manager Administrator.
6. Save the connector.
7. Make the connector available to your Learners.

>[!NOTE]
>
>AI client interfaces change frequently. If these steps don't match your client, refer to your AI client vendor's documentation for adding a remote connector.

## Troubleshooting

**Learners don't see the connector.** 
Confirm that the connector is enabled for the learner's workspace or group.

**Authorization fails when a learner selects Connect.** 
Verify that the client ID and secret key match the values on the **Client credentials** page of the server in Adobe Learning Manager.
