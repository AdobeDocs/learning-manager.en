---
description: Look up what learners can do with the Adobe Learning Manager Model Context Protocol server and which MCP tools support each capability
jcr-language: en_us
title: Learner tools for the Model Context Protocol server
exl-id: 4509b984-d0ba-4b7e-a0bb-803aa235fd1e
---

# Learner tools for the Model Context Protocol server

Every capability runs as the signed-in learner, after the learner connects. A request returns only what that learner can access in Adobe Learning Manager. View [Connect your AI client](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md) for more information.

## Learner capabilities

| **Capability** | **What learners can do** | **Example request** |
|----|----|----|
| Search learning content | Find courses, certifications and learning paths | What leadership courses are available? |
| View enrollments | Check enrollments and due learning | Which of my courses are about to expire? |
| Ask learning questions | Get answers from learning content | What does supply chain risk management mean in FedRAMP? |
| Generate learning paths | Create personalized learning paths | Help me find courses to upskill in project management. |
| Save learning paths | Save generated learning paths | Save this learning path. |

## Supported MCP tools

The Learner Assistant MCP server exposes the following learner-facing tools.

| **MCP tool** | **Purpose** | **Supports capability** |
|----|----|----|
| Search | Search available learning content | Search learning content |
| Get Enrollment | Retrieve learner enrollment information | View enrollments |
| Answer Agent | Answer questions using learning content | Ask learning questions |
| Get User | Identify the signed-in learner for each request | All capabilities |
| Get Learning Object | Retrieve details of a learning object, such as description and duration | Search learning content, View enrollments |
| Generate Learning Path | Create recommended learning paths | Generate learning paths |
| Save Learning Path | Save generated learning paths | Save learning paths |

>[!IMPORTANT]
>
>Tool names are shown for reference and may vary depending on client implementation.

