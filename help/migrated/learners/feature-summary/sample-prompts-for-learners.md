---
description: Find sample prompts that learners can ask in Claude or ChatGPT Enterprise to search courses, check enrollments, and build learning paths
jcr-language: en_us
title: Sample prompts for Adobe Learning Manager learners
exl-id: e5d64ac4-03e9-49bc-95d0-bb074d55987f
---

# Sample prompts for Adobe Learning Manager learners

Use these prompts in Claude or ChatGPT Enterprise to search courses, check enrollments and build learning paths.

Connect your AI client first. Learn more about [connecting your AI client to Adobe Learning Manager](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md). Each prompt maps to a tool in the [learner tools reference](/help/migrated/learners/feature-summary/learner-tools-reference.md).

>[!TIP]
>
>Name what you need, such as a topic, a course status or a deadline. Specific requests help the AI client select the right tool.

## Enrollments

| **Prompt**                               | **Tool**                     |
|------------------------------------------|------------------------------|
| What courses am I enrolled in?           | list_my_learning_enrollments |
| Which of my courses are about to expire? | list_my_learning_enrollments |

## Search

| **Prompt**                              | **Tool**              |
|-----------------------------------------|-----------------------|
| What leadership courses are available?  | search_learning_items |
| Show security training available to me. | search_learning_items |

## Knowledge

| **Prompt** | **Tool** |
|----|----|
| What does supply chain risk management mean in FedRAMP? | answer_learning_content_question |
| Explain the requirements in my compliance course. | answer_learning_content_question |

## Learning paths

| **Prompt** | **Tool** |
|----|----|
| Help me find a set of courses to upskill in project management. | personalized_learning_path |
| Save this learning path. | personalized_learning_path |
