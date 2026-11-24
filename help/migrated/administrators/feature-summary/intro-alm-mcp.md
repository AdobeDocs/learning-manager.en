---
description: Extend Adobe Learning Manager into Claude, ChatGPT Enterprise and custom agents so learners can find courses, track progress and get answers.
jcr-language: en_us
title: Adobe Learning Manager Model Context Protocol server
exl-id: 8d0a25a6-1301-4f68-8db7-e3b1d3ff6537
---

# Adobe Learning Manager Model Context Protocol server

The Model Context Protocol (MCP) is an open standard that lets an AI client discover and invoke external tools. The Adobe Learning Manager MCP server exposes the Adobe Learning Manager learner tools to any MCP-compatible client, such as a custom enterprise agent, Claude or ChatGPT Enterprise. Learners reach their training and progress from the client they already use, while the learning content and records remain in Adobe Learning Manager.

## How it works

A learner sends a natural-language request to an AI client. The client selects the most relevant learner tool and calls the MCP server with the learner's OAuth access token. Adobe Learning Manager runs the tool as that learner and returns the result, and the client composes the final response.

Each call carries the learner's identity. A learner can therefore retrieve only the content and records that they're already permitted to access.

The AI client calls the MCP server, which routes each request to the matching learner tool.

## Learner capabilities

Learners work in natural language in the AI client they already use. The client interprets each request, calls the appropriate Adobe Learning Manager learner tool, and returns a response based on what that learner can access. Learners can:

* Discover the courses, certifications and learning paths that are available to them.
* Track their enrollments, progress and deadlines, including learning that is about to expire.
* Get answers grounded in learning content.
* Generate a personalized learning path from their goals, and save it.

For the full list, view the **learner tools reference**.

## Customer and partner education

>[!IMPORTANT]
>
>Customers who build their own enterprise agents can also connect to the server. For example, a partner organization can offer its own customers access to learning through its own agent.

Customer and partner education is a primary use of the MCP server. Organizations that build their own enterprise AI agents can connect those agents to the Adobe Learning Manager learner tools. Their customers and partners then learn inside the assistant they already use, without moving to a separate learning assistant.

For example, Acme Inc. builds its own enterprise AI assistant. An Acme Inc. partner visits the assistant to learn about Acme Inc. products. The assistant connects to the Acme Inc. Adobe Learning Manager account through the MCP server and returns learning-related responses. The partner never leaves the Acme Inc. experience.

This approach lets organizations:

* Deliver learning inside a partner's existing AI experience.
* Extend custom enterprise agents with the Adobe Learning Manager learner tools.
* Embed learning in their own workflows.
* Integrate learning with their enterprise AI ecosystem.

## Employee education

Employees who already use an AI client, such as Claude, can get their learning information there. For example, an employee can check assigned learning, review enrollments, find courses on a topic or ask for a learning path, without switching to Adobe Learning Manager. For sample requests, learn more about [sample prompts for learners](/help/migrated/learners/feature-summary/sample-prompts-for-learners.md).

This approach lets employees:

* Remain in the tools they already use.
* Reach their learning wherever they work.
* Use any MCP-compatible AI client as an entry point to Adobe Learning Manager.
* Retrieve learning information without changing context.

## One server for both audiences

Customer and partner education and employee education use the same learner tools and the same server. Only the audience changes. Choose the approach that fits who your learners are.

| **Audience** | **Example** | **Where learners work** |
|----|----|----|
| External | Customers and partners | Your organization's own enterprise AI agent |
| Internal | Employees | An enterprise AI client, such as Claude or ChatGPT Enterprise |

## Setup roles

Setup is divided among three roles.

* **Administrator:** Creates an MCP client application in Adobe Learning Manager and manages it. Learn more about [configuring an MCP server](/help/migrated/administrators/feature-summary/configure-mcp-admin.md).
* **AI client administrator:** Adds the server to the organization's enterprise AI client, such as Claude or ChatGPT Enterprise.
* **Learner:** Selects **Connect** in the AI client, authenticates the connection and provides their Adobe Learning Manager account details.

## Security of learner requests

Each learner authenticates the connection and provides their Adobe Learning Manager account details. Every request runs as that learner, so the AI client returns only the information that the learner can access in Adobe Learning Manager. The server doesn't grant learners additional access.

## Limitations

* The MCP server is available to Adobe Learning Manager Ultimate tier accounts only.
* Tool availability depends on what your AI client supports.
* The server treats each request as new. Multi-turn conversations work only if your AI client retains the conversation context.
