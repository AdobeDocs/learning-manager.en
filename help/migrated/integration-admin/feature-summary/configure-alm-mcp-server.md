---
description: Create an MCP server in Adobe Learning Manager, connect it to Claude or ChatGPT, and manage credentials, tools, limits, and troubleshooting
jcr-language: en_us
title: Configure the Adobe Learning Manager MCP server
exl-id: b5d2c08e-a11e-4f55-9ba5-a652a9575678
---

# Configure the Adobe Learning Manager MCP server

Configure the Model Context Protocol (MCP) server once for your organization. Configuration has two parts: create an MCP server in Learning Manager, and then connect it to your AI assistant. Afterward, learners sign in to Learning Manager from the AI assistant and can use the MCP tools.

Before you begin, ensure that:

* The MCP server is enabled for your Learning Manager account. Contact your Adobe Customer Success Manager or Adobe Support to enable it. Until then, every request returns 403 Forbidden.
* The AI assistant administrator has permission to add and configure connectors in that platform.

**Prerequisite:** Model Context Protocol server is a backend flag based feature which works only for Ultimate tier accounts.

## Create an MCP server in Learning Manager

Creating an MCP server sets up an OAuth application and gives you the MCP server URL, Client ID, and Client Secret.

1. Sign in to Learning Manager as an Integration Admin.
2. In the navigation menu, select **MCP Servers**.
3. In the upper-right corner, select **Create**.

      ![](assets/integration-admin-mcp1.png)

4. On the **Application Details** page, enter the following, and then select **Next**:

    * **Application Name:** Enter up to 50 characters, for example, ALM for Claude. Learners see this name when they authorize the connection, so choose a name they recognize.
    * **Redirect Domains:** Enter the callback domain of each AI assistant, one domain per line. Start each with and don't include a path. This field is required.
    * **Description:** Enter up to 150 characters, for example, lets learners use ALM from Claude.

5. On the **Tool Configuration** page, review the tools and the descriptions that AI assistants use to decide when to call each tool. To change a description, select **Actions** (**…**) \> **Edit**. To restore the default, select **Reset**. Then select **Next**.
6. On the **Client Credentials** page, copy the **MCP Server URL**, **Client ID**, and **Client Secret**. Store them securely. You need them to connect your AI assistant.

The MCP server always has Learner scope, so there are no scopes to select.

Register the domain for each AI assistant you plan to connect.

| **AI assistant** | **Redirect domain to register** | **Full callback URL (reference)** |
|----|----|----|
| Claude | [https://claude.ai](https://claude.ai/) and [https://claude.com](https://claude.com/) | <https://claude.ai/api/mcp/auth_callback> |
| ChatGPT | [https://chatgpt.com](https://chatgpt.com/) | <https://chatgpt.com/connector/oauth/&lt;id>\> (ChatGPT shows the ID during setup) |

Register exact domains, such as [https://chatgpt.com](https://chatgpt.com/). Don't use partial wildcards such as [https://*chatgpt.com*](https://chatgpt.com)*, because they can match unrelated domains. To allow subdomains, use a whole-label wildcard such as* [*https://*.example.com](https://.example.com).

One MCP server can serve several AI assistants if you list all their redirect domains. To revoke access for one assistant without affecting the others, create a separate MCP server for each. All servers use the same MCP server URL.

You need only the MCP server URL. Claude and ChatGPT automatically discover the Learning Manager OAuth endpoints. For manual setup, view **OAuth endpoints for the Learning Manager MCP server**.

## Connect Claude Pro or Max

Refer to Claude documentation if these steps no longer match the interface.

>[!NOTE]
>
>The verbosity of the responses to questions posed changes as responses from the answer_learning_content_question tool are reframed and formatted by the clients.

1. In Claude, go to **Customize** \> **Connectors**.
2. Select **Add** (+), and then select **Add custom connector**.
3. Enter the connector details, and then select **Continue**:

    * **Name:** Enter a name your learners recognize, for example, Adobe Learning Manager.
    * **Remote MCP server URL:** Enter the MCP Server URL from the Client Credentials page, in the format [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp).

4. Under **Authentication**, keep **Sign in now**. Claude reads the Learning Manager OAuth settings and marks matching options as *Detected*.
5. Under **OAuth client**, select **Use your own OAuth client**. Paste the **Client ID** and **Client Secret**.
6. Select **Add**. Claude opens the Learning Manager sign-in page. After you sign in, the connector shows as connected.

>[!NOTE]
>
>Claude labels the Client Secret field as optional, but Learning Manager requires it. If you leave it empty or enter a wrong value, sign-in fails with an "Authorization failed" message.

## Connect Claude Team or Enterprise

Only an organization Owner, or a member with a role that can manage connectors, can add the connector. Members never see the Client ID or Client Secret.  

>[!NOTE]
>
>The verbosity of the responses to questions posed changes as responses from the answer_learning_content_question tool are reframed and formatted by the clients.
  
1. In Claude, sign in as an organization Owner or a member with permission to manage connectors.
2. Go to **Organization settings** \> **Connectors**.
3. Select **Add**, hover over **Custom**, and then select **Web**.
4. Enter the name and MCP server URL, and then set **Authentication** and **OAuth client** as described in steps 4 and 5 of the previous procedure.
5. Select **Add**.

The connector is now available to your organization. Each member selects **Connect** and signs in to Learning Manager with their own account.

## Connect ChatGPT Team or Enterprise

>[!NOTE]
>
>The verbosity of the responses to questions posed changes as responses from the answer_learning_content_question tool are reframed and formatted by the clients.

1. Log in to ChatGPT as a workspace owner or admin.
2. In the left sidebar, click **Plugins**.
3. Click **Add** in the upper-right corner and select **Create MCP App**.
4. In the **New Plugin** window, configure the connection:

    * **Name:** Adobe Learning Manager, or the name your learners know your learning platform by.
    * **Connection:** keep **Server URL** selected and enter [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp)
    * **Authentication:** OAuth


      ![](assets/integration-administrator-mcp1.png)

5. Click **Advanced OAuth settings**. ChatGPT discovers the ALM OAuth endpoints automatically.
6. Under **Client registration**, keep **Registration method** set to **User-Defined OAuth Client**, then enter the **OAuth client ID** and **OAuth client secret** from Step 1.
7. Check the **Callback URL** shown in this panel. Its domain (<https://chatgpt.com>) must be in the MCP server's **Redirect Domains** from Step 1.

      ![](/help/migrated/integration-admin/feature-summary/assets/integration-admin-mcp2.png)

**Endpoints are discovered automatically**

You normally don't need to change the OAuth endpoints. If ChatGPT asks for them, use: Auth URL [https://\[alm-host\]/oauth/o/authorize](https://[alm-host]/oauth/o/authorize), Token URL [https://\[alm-host\]/oauth/token](https://[alm-host]/oauth/token), Registration URL empty, Resource [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp), scope learner:write.

1. Select **I understand and want to continue**, then click **Create**.
1. In the **Connect** window, click **Continue** and sign in to ALM. The window should show *Approved by your admin*.
1. Make the plugin available to the target users in your workspace.

![](/help/migrated/integration-admin/feature-summary/assets/integration-admin-mcp3.png)

## End-user authentication

Once the administrator has finished configuring the MCP server, learners add the ALM connector from their AI assistant's list of connectors and click **Connect**. This opens the ALM sign-in page. After signing in (with SSO, if your account uses it) and approving access, the AI assistant is linked to the learner's ALM account.

## Rotate the Client Secret or revoke access

You can't regenerate a Client Secret. To rotate it:

1. Create a new MCP server, as described earlier in this article.
2. Update your AI assistant with the new Client ID and Client Secret.
3. In **Integration Admin** \> **MCP Servers**, select **Actions** (**…**) \> **Delete** for the old server.

Learners must sign in again after you switch.

To disconnect an AI assistant for all learners, delete its MCP server from the same page.

## Available tools

The MCP server exposes the following tools. All of them run with the signed-in learner's permissions.

<table style="width:100%;">
<colgroup>
<col style="width: 46%" />
<col style="width: 31%" />
<col style="width: 21%" />
</colgroup>
<thead>
<tr>
<th><strong>Tool</strong></th>
<th><strong>What it does</strong></th>
<th><strong>Example prompts</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>search_learning_itemsread-only</td>
<td>Searches the catalog for courses, learning paths, certifications, job aids, badges, skills, catalogs, and tags. Filters: type, learner state, skill, tag, catalog, delivery format, price, and language. Returns up to 10 results per page.</td>
<td>"Beginner Python courses"<br />
"Free classroom trainings in French"</td>
</tr>
<tr>
<td>list_my_learning_enrollmentsread-only</td>
<td>Lists the learner's enrolled, in-progress, and completed learning, with state, progress, and deadline. Most recently enrolled first by default.</td>
<td>"What am I enrolled in?"<br />
"What's due soon?"<br />
"My completed trainings"</td>
</tr>
<tr>
<td>get_learning_objectread-only</td>
<td>Gets full details of a course, learning path, certification, or job aid by ID, optionally including instances, skills, and sub-items.</td>
<td>"Tell me more about the second course"</td>
</tr>
<tr>
<td>get_my_learning_profileread-only</td>
<td>Gets the learner's ALM profile, including account and manager.</td>
<td>"Who is my manager in ALM?"</td>
</tr>
<tr>
<td>answer_learning_content_questionuses AI credits</td>
<td>Answers questions about course subject matter using the ALM Learning Assistant, grounded in course content with citations. Returns a conversation ID that the assistant uses for follow-up questions.</td>
<td>"Explain TCP vs UDP as covered in my networking course"</td>
</tr>
<tr>
<td>personalized_learning_path</td>
<td>Provides personalized learning paths in Adobe Learning Manager tailored to a learner's goals, topics, and learning needs. Supports generating course recommendations, saving a selected learning path to the learner's account, listing the learner's saved learning paths (action list), and getting the details and courses of one saved learning path by its id (action details). Helps learners identify relevant learning content for developing skills and reaching learning goals.</td>
<td>"Save the selected learning path to my account."</td>
</tr>
</tbody>
</table>

Conversations started through answer_learning_content_question appear in the Learner AI Conversation report, the same as conversations in the ALM Learning Assistant.

## Limits

| **Limit** | **Value** |
|----|----|
| Results per page (search and enrollments) | Up to 10. Use the returned cursor for more pages. |
| answer_learning_content_question rate | 10 requests per minute per learner (burst of 5), with at most 2 in progress at once |
| Supported MCP protocol versions | 2025-11-25, 2025-06-18, 2025-03-26 |
| Transport | Streamable HTTP, stateless (POST only; no server-sent event stream) |

## **OAuth endpoints reference**

Claude and ChatGPT discover these automatically. They're listed here for clients or proxies that need them entered by hand. Replace \[alm-host\] with the host in your MCP Server URL (your region host or ALM custom domain).

| **Value** | **URL** |
|----|----|
| MCP server URL | [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp) |
| Authorization URL | [https://\[alm-host\]/oauth/o/authorize](https://[alm-host]/oauth/o/authorize) |
| Token URL | [https://\[alm-host\]/oauth/token](https://[alm-host]/oauth/token) |
| Refresh URL | [https://\[alm-host\]/oauth/token/refresh](https://[alm-host]/oauth/token/refresh) |
| Authorization server base | [https://\[alm-host](https://[alm-host)\] |
| Resource | [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp) |
| Scope | learner:write |

## Troubleshooting

| **Symptom** | **Cause and fix** |
|----|----|
| Unregistered redirect during sign-in | The AI assistant's callback domain isn't in the application's **Redirect Domains**. Add it (for example, <https://claude.ai>) and try again. |
| Sign-in succeeds, then the assistant says authorization failed (Invalid client) | The Client Secret entered in the assistant doesn't match the application. Copy it again from ALM, check for extra spaces, and reconnect. |
| All requests return 403 Forbidden | The MCP server is not enabled for your account. Contact Adobe Support. |
| Connected as the wrong ALM user | The browser already had an ALM session. Disconnect, sign out of ALM (or use a private window), and connect again. |
| "Rate limit exceeded" from the Q&A tool | The learner exceeded the Q&A rate limit. Wait a minute and try again. |
| The assistant asks to sign in again | The learner's token expired or was revoked. Click **Connect** again. |

## FAQ

### **Can learners use the MCP server without an admin setting it up?**

No. An Integration Admin must create an MCP server in ALM (Step 1), because the MCP server doesn't support dynamic client registration.

### **Can we use our own domain?**

Yes. If your ALM account has a custom domain, use it in place of \[alm-host\] in all URLs.

### **Which ALM roles can use the MCP server?**

Any ALM user can connect. The tools act in the learner context, and ALM's own permission checks apply to every request.
