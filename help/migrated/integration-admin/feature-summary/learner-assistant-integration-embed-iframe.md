---
description: Learn how to embed the Learner Assistant in your app using an iframe, including setup, configuration, and event handling
jcr-language: en_us
title: Integrate Learner Assistant by embedding iFrame
---

# Learner Assistant embedding using an iframe

## Overview

Adobe Learning Manager (ALM) users can embed the **Learner Assistant** directly into their own learner-facing applications (for example, custom portals, LMS front ends, learning hubs, etc.) using a standard HTML `<iframe>`.

When embedded via iFrame, the Learner Assistant provides access to all Learner Assistant capabilities, including:

* Orchestrator
* Answer Agent
* Knowledge Agent
* Learning Path Agent

>[!IMPORTANT]
>
>iFrame embedding gives your application full access to Learner Assistant's underlying agents. However, your application (the "parent app") is responsible for handling any events the assistant emits. For example, when a learner clicks on a citation or a course link inside the assistant's response, the assistant emits an event, and your parent application must handle that event and perform the actual navigation. The Learner Assistant does not navigate on your application's behalf.

## Prerequisites

Before you begin, make sure you have:

* An ALM tenant with Learner Assistant enabled. Configure the required catalog(s) from the administrator settings page.
* A valid accessToken for authenticating the learner (or admin) session. To generate an access token, follow the instructions on the [Authentication using OAuth 2.0](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20) page. The page includes the steps required to authenticate and generate the access token needed to proceed.
* The ability to embed an `<iframe>` in your application and communicate with it via the browser's postMessage API.
* Front-end code ownership of the parent application, since your application must listen for and respond to messages from the embedded iFrame.

## Learning Assistant configuration parameters

| Parameter Name | Value | Description |
|---|---|---|
| hostName | learningmanager.adobe.com | Specifies the host domain for the application. |
| accessToken | token123 (actual access token) | Token used to authenticate and authorize the user session. |

## Initialize iFrame

Pass the configuration to the Learner Assistant via the postMessage API, using an embedded iFrame configuration handshake.

1. The parent application embeds the Learning Assistant as an `<iframe>`.
2. If no URL-based configuration is found, the Learning Assistant sends an ALM_CHAT_REQUEST_CONFIG event to the parent application.
3. The parent application responds with an ALM_CHAT_CONFIG event containing the configuration payload. For example:

   ```json
   {
     "hostName": "learningmanager.adobe.com",
     "accessToken": "token123",
     "openByDefault": false,
     "isAdmin": false
   }
   ```

4. After successful initialization, the Learner Assistant renders and is ready to use.

## iFrame event summary

The Learner Assistant and the parent application communicate through postMessage events in both directions.

### Outgoing events (Learner Assistant iFrame to Parent App)

| Event Name | Description | Parameters Passed |
|---|---|---|
| ALM_CHAT_OPENED | Fired when the chat is opened. | -- |
| ALM_CHAT_CLOSED | Fired when the chat is closed. | -- |
| ALM_CHAT_LO_REDIRECT | Navigate to the personalized Learning Path overview page. | loId, loType, instanceId |
| ALM_CHAT_URL_REDIRECT | Fired when an external link is clicked in the chat message. | url |
| ALM_CHAT_REQUEST_CONFIG | Requests configuration from the parent application. | -- |
| ALM_CHAT_WAITING_FOR_REPLY | Indicates the assistant is processing a request or waiting for a response. | isWaitingForReply |
| ALM_CHAT_PERSONALIZED_PATH_CREATED | Triggered when a Learning Path is saved. | -- |

### Incoming events (Parent App to Learner Assistant)

| Event Name | Description | Payload |
|---|---|---|
| ALM_CHAT_CONFIG | Sends the configuration payload required to initialize the assistant. | Configuration object |
| ALM_CHAT_OPEN | Opens the Learner Assistant. | None |
| ALM_CHAT_CLOSE | Closes the Learner Assistant. | None |
| ASK_AI_ASSISTANT_QUERY | Opens the chat window and submits a query to the assistant. | { query: "Question text" } |

## Event-handling requirements in the parent application

Embedding the Learner Assistant via iFrame does not make it a fully self-contained widget. Your parent application must actively listen for outgoing events and take the appropriate action. At a minimum, your application should:

* Listen for ALM_CHAT_REQUEST_CONFIG and respond with ALM_CHAT_CONFIG so the assistant can initialize.
* Handle ALM_CHAT_LO_REDIRECT: when a learner clicks a citation or source in the assistant's reply, your application receives the loId, loType, and instanceId, and is responsible for navigating the learner to the correct course or learning object.
* Handle ALM_CHAT_URL_REDIRECT: when a learner clicks an external link in a chat message, your application receives the url and is responsible for opening or navigating to it (for example, in a new tab).
* Optionally track ALM_CHAT_OPENED / ALM_CHAT_CLOSED / ALM_CHAT_WAITING_FOR_REPLY to reflect the assistant's state in your own UI (for example, showing a loading indicator while isWaitingForReply is true).
* Optionally use ALM_CHAT_OPEN / ALM_CHAT_CLOSE / ASK_AI_ASSISTANT_QUERY to control the assistant programmatically. For example, opening the assistant and pre-filling a query from a **Help** button elsewhere in your application.

## Need help?

Reach out to your Adobe Customer Success Manager to set up a technical walkthrough.
