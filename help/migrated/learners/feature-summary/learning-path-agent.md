---
description: The Learning Path agent in Adobe Learning Manager is an AI-powered assistant that generates a custom, sequenced learning plan based on your goals, background, and available time. 
jcr-language: en_us
title: Learning Path Agent (beta) in Adobe Learning Manager
---

# What is Learning Path Agent

A Learning Path Agent creates a structured Learning Path using the AI assistant. Unlike standard learning paths assigned by your administrator, such Learning Paths are generated through a guided conversation. You describe your goal, and the agent builds a path matched to your learning needs.

The agent draws content from your organization's internal course catalog first, prioritizing courses that are approved and relevant to your team. If your administrator has enabled third-party content, the agent may also include courses from connected external providers to fill any gaps in coverage. You are always automatically enrolled in the courses within your saved path, so you can start learning immediately.

Personalized Learning Paths are designed for two main use cases:

- **Targeted skill development**: When you need to achieve a specific business outcome or reach a performance goal quickly, such as preparing for a new responsibility or closing a skill gap identified in a review.
- **Building deep expertise**: When you want to advance from beginner to expert in a chosen domain, technology, or discipline over a longer timeframe.

## How the conversation-based approach works

The agent meets you where you are. You start by describing what you want to learn in plain language, in as much or as little detail as you have. The agent then asks follow-up questions to understand your role, your specific challenges, and how much time you can dedicate to learning each week.

From your answers, the agent identifies 3–5 learning topics with suggested proficiency levels. You can review these topics, request changes, or confirm them before the agent searches for matching courses. The agent then generates a named learning path showing each course, its description, duration, and module count. You can adjust the path further before saving it.

When you save the path, you are automatically enrolled in all courses. The path appears on your home page in the _Personalized Learning Paths_ section, ready to start.

### Content sources and course selection

The agent selects courses based on relevance to your stated goal, your current proficiency level, the total time you have available, and how recently the content was updated. When the agent cannot find matching courses for a specific topic in the available catalog, it tells you and suggests reaching out to your administrator to request additional content for that area.

### Personalized Learning Paths on the home page

All saved personalized learning paths appear in the _Personalized Learning Paths_ strip on your home page. Each card shows the path name, number of courses, and a _Continue_ button to resume where you left off.

![](plp-agent/image_0001.png)

### Sharing a Learning Path

Once you have saved a Personalized Learning Path, you can share it with colleagues. Sharing sends them a link or an email invitation. When a colleague opens a shared path, they can enroll with a single action. Sharing is useful when several people on your team have similar learning goals, and you want them to follow the same structured plan.

### Best practices

- Describe your learning goal as specifically as possible when you start the conversation. The more context the agent has, the more relevant your path will be.
- Provide your time commitment upfront, so the generated path fits your actual schedule. The agent understands natural language: "two evenings a week" or "30 minutes a day" are both valid.
- Review the suggested topics before asking the agent to generate courses. Confirming or adjusting topics at that stage saves time compared to revising the course list afterward.
- If a topic shows no matching content, note it and contact your administrator to request relevant courses to be added to the catalog.

## Configure the Personalized Learning Path agent

The Personalized Learning Path agent is enabled by default in Adobe Learning Manager when you enable the AI Assistant option in Settings.

>[!NOTE]
>
> Content visibility follows your existing catalog access rules. A learner will only see and receive courses from catalogs they already have access to\. The Personalized Learning Path agent does not bypass catalog restrictions.

Within each source, the agent ranks courses by relevance to the learner's goal, how well the course level matches the learner's stated proficiency, how recent the content is, and available quality signals such as ratings and completion rates.

If no matching courses are available for a topic in the catalog, the agent informs the learner and suggests they contact an administrator to request content for that area.

### Monitor credit usage

The Personalized Learning Path agent consumes AI credits each time a learner generates a path. To monitor and manage usage:

1. In the left navigation of the administrator's home page, select **Billing**.
2. Select the **AI Credits** tab. The **Learning Path** agent appears as a line item in the features list.
3. Review current usage and adjust the credit allocation or usage limit as needed.

