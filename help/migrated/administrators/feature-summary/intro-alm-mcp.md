---
description: Let learners discover courses, track progress and get answers from Adobe Learning Manager content inside Claude, ChatGPT Enterprise and custom agents.
jcr-language: en_us
title: Adobe Learning Manager Model Context Protocol server
exl-id: 8d0a25a6-1301-4f68-8db7-e3b1d3ff6537
---

# Adobe Learning Manager Model Context Protocol server

## Overview

The Model Context Protocol (MCP) is a standard way for an AI client to connect to tools. The Adobe Learning Manager MCP server brings learning to where learners already work. It exposes the Adobe Learning Manager learner tools to any AI client that supports MCP, such as a custom enterprise agent, Claude or ChatGPT. Learners can then access their trainings and progress from within the same client, while the content stays in Adobe Learning Manager.

## Learner capabilities

Learners work in natural language in the AI client they already use. The client interprets each request, calls the appropriate Adobe Learning Manager learner tool, and returns a response based on what that learner can access. Learners can:

* Discover the courses, certifications and learning paths that are available to them.
* Track their enrollments, progress and deadlines, including learning that is about to expire.
* Get answers grounded in learning content.
* Generate a personalized learning path from their goals, and save it.
For the full list, view the **learner tools reference**.

The AI client calls the MCP server, which routes each request to the matching learner tool.

For the full list, view the **learner tools reference**.

## Customer and partner education

Customer and partner education is a primary use of the MCP server. Organizations that build their own enterprise AI agents can connect those agents to the Adobe Learning Manager learner tools. Their customers and partners then learn inside the assistant they already use, without moving to a separate learning assistant.

For example, Acme Inc. builds its own enterprise AI assistant. An Acme Inc. partner visits Lenovo's environment to learn about Lenovo products. Acme's assistant connects to its Adobe Learning Manager account through the MCP server and returns learning-related responses, so the partner never leaves the Acme experience.

This approach lets organizations:

* Offer learning inside a partner's existing AI experience.
* Let custom enterprise agents use the Adobe Learning Manager learner tools.
* Build learning into their own workflows.
* Integrate learning with their enterprise AI ecosystem.

## Employee education

Employees who already use an AI client, such as Claude, can get their learning information there. For example, an employee can check assigned learning, review enrollments, find courses on a topic or ask for a learning path, without switching to Adobe Learning Manager. For sample requests, see [sample prompts for learners](https://word-edit.officeapps.live.com/docs/sample-prompts-adobe-learning-manager-learners).

This approach lets employees:

* Stay in the tools they already use.
* Reach their learning wherever they work.
* Use any AI client that supports MCP as an entry point to Adobe Learning Manager.
* Get learning information without changing context.

## One server for both audiences

Customer and partner education and employee education use the same learner tools and the same server. Only the audience changes. Choose the approach that fits who your learners are.

| **Audience** | **Example** | **Where learners work** |
|----|----|----|
| External | Customers and partners | Your organization's own enterprise AI agent |
| Internal | Employees | An enterprise AI client, such as Claude or ChatGPT Enterprise |

## Setup roles

The setup is split between three roles.

* **Administrator:** Creates an MCP client application in Adobe Learning Manager and manages it. See [configure an MCP server](https://word-edit.officeapps.live.com/docs/configure-model-context-protocol-server-adobe-learning-manager).
* **AI client administrator:** Adds the server to the organization's enterprise AI client, such as Claude or ChatGPT Enterprise.
* **Learner:** Selects **Connect** in the AI client, authenticates the connection and provides their Adobe Learning Manager account details.

## Security of learner requests

Each learner authenticates the connection and provides their Adobe Learning Manager account details. The request runs as that learner, so the AI client returns only the information that learner can access in Adobe Learning Manager. The server doesn't give learners extra access.

## Limitations of MCP in this update

* Tool availability depends on what your AI client supports.
* Each request is treated as new. Multi-turn conversations work only if your AI client keeps the conversation context.
