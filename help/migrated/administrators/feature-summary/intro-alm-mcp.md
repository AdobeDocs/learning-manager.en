---
description: Learn how learners use the Adobe Learning Manager MCP server to search courses and check enrollments from AI clients such as Claude and ChatGPT
jcr-language: en_us
title: Adobe Learning Manager Model Context Protocol server
exl-id: 8d0a25a6-1301-4f68-8db7-e3b1d3ff6537
---

# Adobe Learning Manager Model Context Protocol server

## Overview

The Adobe Learning Manager Model Context Protocol server lets learners search for courses and check enrollments within clients, such as Claude and ChatGPT Enterprise. The Model Context Protocol (MCP) is a standard way for an AI client to connect to tools. The Adobe Learning Manager MCP server exposes Learner Assistant tools to any AI client that supports MCP.

## What can learners do with the server?

Learners ask questions in natural language in their AI client. The client calls Learner Assistant tools and returns the result. Learners can:

* Find courses that are available to them.
* Review their enrollments, including courses that are about to expire.
* Get answers drawn from learning content.
* Generate a learning path and save it.

For the full list, view the [Learner tools reference.](/help/migrated/learners/feature-summary/learner-tools-reference.md)

## Setup roles

The setup is divided between three roles:

* **Integration Administrator:** Creates the MCP server in Adobe Learning Manager. View **configure an MCP server**.
* **AI client administrator:** Adds the server to the organization's enterprise AI client, such as Claude or ChatGPT Enterprise.
* **Learner:** Selects **Connect** in the AI client and signs in with their enterprise identity.

Customers who build their own enterprise agents can also connect to the server. For example, a partner organization can offer its own customers access to learning through its own agent.

## Customer and partner education

Organizations that build their own enterprise AI agents can connect those agents to the Learner Assistant tools through the server. Their customers and partners then learn inside the assistant they already use. Learners don't need to leave that environment for a separate learning assistant.

For example, a manufacturer builds its own AI assistant. A partner company visits the manufacturer's environment to learn about its products. The manufacturer's assistant calls the Adobe Learning Manager tools and returns learning-related responses.

This approach lets organizations:

* Offer learning inside a partner's existing AI experience.

* Let custom enterprise agents use the Adobe Learning Manager learner tools.

* Build learning into their own workflows.

* Integrate learning with their enterprise AI ecosystem.

## Employee education

Employees who already use an AI client, such as Claude, can get their learning information there. For example, an employee can check assigned learning, review enrollments, find courses on a topic or ask for a learning path, without switching to Adobe Learning Manager.

This approach lets employees:

* Stay in the tools they already use.
* Reach their learning wherever they work.
* Use any AI client that supports MCP as an entry point to Adobe Learning Manager.
* Get learning information without changing context.

## One MCP server for both audiences

Customer and partner education and employee education use the same learner tools and the same server. Only the audience changes. Choose the approach that fits who your learners are.

| Audience | Who                | Where learners work                                       |
|--------------|------------------------|---------------------------------------------------------------|
| External     | Customers and partners | Your organization's own enterprise AI agent                   |
| Internal     | Employees              | An enterprise AI client, such as Claude or ChatGPT Enterprise |

## Security of learner requests

Each learner signs in with their enterprise identity. The request runs as that learner, so the AI client returns only the information that the learner can access in Adobe Learning Manager.

## Limitations of MCP in this update

* Tool availability depends on what your AI client supports.
* Each request is treated as new. Multi-turn conversations work only if your AI client keeps the conversation context.
