---
description: Look up what learners can do with the Adobe Learning Manager Model Context Protocol server and which tools support each capability.
jcr-language: en_us
title: Learner tools for the Model Context Protocol server
exl-id: 4509b984-d0ba-4b7e-a0bb-803aa235fd1e
---

# Learner tools for the Model Context Protocol server

## Overview

Every capability runs as the signed-in learner, after the learner connects. A request returns only what that learner can access in Adobe Learning Manager. Learn more about [connecting your AI client](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md).

## Learner capabilities

| **Capability** | **What learners can do** | **Example request** |
|----|----|----|
| Search learning content | Find courses, certifications and learning paths | What leadership courses are available? |
| View enrollments | Check enrollments and due learning | Which of my courses are about to expire? |
| Ask learning questions | Get answers from learning content | What does supply chain risk management mean in FedRAMP? |
| Generate learning paths | Create personalized learning paths | Help me find courses to upskill in project management. |
| Save learning paths | Save generated learning paths | Save this learning path. |

## Supported MCP tools

The Adobe Learning Manager MCP server exposes the following learner tools.

| **Tool name** | **Description** |
|----|----|
| search_learning_items | Search the catalog for courses, learning paths, certifications, job aids, badges, skills, catalogs and tags. Filter by learner state, skill, tag, catalog, delivery format, price and language. For subject-matter questions, use answer_learning_content_question. Example: "Beginner Python courses." |
| list_my_learning_enrollments | List the learner's enrolled, in-progress and completed courses, learning paths, certifications and job aids, with state, progress and deadline. Filter by learning object type or completion status. Results show the most recent enrollments first. Example: "What's due soon?" |
| get_learning_object | Get the full details of a course, learning path, certification or job aid by ID, optionally with instances, skills and sub-learning objects. Get the ID from search_learning_items or list_my_learning_enrollments. |
| get_my_learning_profile | Get the learner's profile, including account and manager details. For enrollments and progress, use list_my_learning_enrollments. |
| answer_learning_content_question | Answer questions about learning content, grounded in the learning material and cited to the source learning objects. Summarize one learning object, or compare two side by side for coverage, depth, prerequisites and audience. To find or list content, use search_learning_items or list_my_learning_enrollments. Example: "Explain TCP vs UDP as covered in my networking course." |
| personalized_learning_path | Recommend courses that match a learner's goals, topics and needs. Save an approved path to the learner's account. List saved paths, or get the details and courses of one path by ID. |

>[!IMPORTANT]
>
>Tool names are shown for reference and may vary depending on client implementation.
