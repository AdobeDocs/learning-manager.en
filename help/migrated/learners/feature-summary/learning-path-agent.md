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

Within each source, the agent ranks courses by relevance to the learner's goal and how well the course level matches the learner's stated proficiency.

If no matching courses are available for a topic in the catalog, the agent informs the learner and suggests they contact an administrator to request content for that area.

<!-- 
### Monitor credit usage

The Personalized Learning Path agent consumes AI credits each time a learner generates a path. To monitor and manage usage:

1. In the left navigation of the administrator's home page, select **Billing**.
2. Select the **AI Credits** tab. The **Learning Path** agent appears as a line item in the features list.
3. Review current usage and adjust the credit allocation or usage limit as needed.

>[!CAUTION]
>
>If the credit limit for the Learning Path agent is reached, learners receive an in-app message that the agent is unavailable and are directed to contact an administrator. Increase the allocation to restore access. 
-->

## Create a Personalized Learning Path with the Learner AI assistant

Use the Learner AI assistant in Adobe Learning Manager to generate a personalized learning path matched to your goal, background, and available time. Then save it to your profile and start learning immediately.

### Open the Learner AI assistant and start a conversation

1. Select **AI Assistant** from your home page.
2. Type your learning goal in the text field. Be as specific as you can. For example:
    - *I am a software developer and I want to create an AI agent using Cursor.*
    - *I just got promoted to a manager role and want to learn how to handle difficult conversations.*
    - *I want to master financial modeling as an analyst.*
![](assets/ai-assistant.png)

3. Optionally, select _+ New chat_ to start a fresh conversation if you have previous sessions open.

Notes:

- Optionally, attach a document using the _paperclip_ icon, such as a resume, a manager feedback email, or a project brief. The agent uses the document to get more context about your lrarning goal and background.
- Select _Send_.

### Describe your goal and background

The agent responds with a message acknowledging your goal and asks for additional context to tailor your path. It typically asks about:

- _Your current role and background_ what you already know, how long you have been in your role, or any relevant experience.
- _Your specific challenges or scenarios_ the real-world situations you need this learning to address immediately.
- _Your time commitment_ the number of hours per week you can realistically dedicate to learning.

![](assets/goal-background.png)

You do not need to answer every question. The only required input is your learning goal or challenge. The agent will proceed with whatever context you provide.

>[!TIP]
>
>The agent understands natural time expressions. You can say "two evenings a week," "about 30 minutes a day," or "a couple of hours on weekends", and the agent converts it to weekly hours to estimate and confirms it with you.

Type your response and select _Send_.

![](assets/time-commitment.png)

Continue the conversation until the agent presents your suggested topics.

![](assets/suggested-topics.png)

### Review the suggested topics

After gathering enough context, the agent presents a list of 3–5 learning topics, each with a title, a brief description, and a suggested proficiency level.

1. Read the topic list carefully. The agent selects proficiency levels based on what you have shared, but you can request changes.
2. To adjust a topic, for example, to change the proficiency level or swap a topic, type your feedback in the chat. For example, I already have some knowledge of the first topic. Can you set that one to intermediate?
3. If you are happy with the topics as suggested, confirm them by replying in the chat or selecting the suggested confirmation prompt if one appears.

### Review the learning path

The agent searches the available catalog and builds a named learning path. The path shows:

- The path name and total estimated duration
- Each course title, description, duration, and module count
- An indication if some topics had no matching content available

If some topics have no matching content:

The agent informs you that it could not find courses for those specific topics and suggests reaching out to your administrator to request content for those areas. The path is still generated for the topics where courses were found.

<!-- - Review the path. If you want to change something, for example, remove a course, adjust the scope, or explore different topics. Type your request in the chat\. For example, Can you remove the first course and replace it with something shorter? -->
When you are satisfied with the path, ask the agent to save it by typing save the learning path.

![](assets/create-lp.png)

### Save and access your Learning Path

When you save the path, the agent confirms the save and enrolls you automatically in all courses within the path.

To access your path:

- Select _Go to the Learning Path_ from the confirmation message to open it immediately, or
- Find it in the _Personalized Learning Paths_ strip on your home page at any time.

### Share your Learning Path

From the path overview page, you can share your saved path with colleagues.

1. Open your saved path from the _Personalized Learning Paths_ strip on your home page.
2. Select _Share_.
3. Share the generated link, or enter email addresses to send a direct invitation.

A colleague who receives the shared link can enroll in the path with a single action.

## Best practices

- Provide context about your role and current challenges. The more specific you are, the more relevant the course selection.
- Mention your weekly time commitment in natural language. The agent will confirm its interpretation before generating the path.
- Review the suggested topics before asking for path generation. Adjusting topics at that stage is faster than revising the course list afterward\.
- If the generated path includes courses you have already completed, let the agent know. It can suggest alternatives.

## Frequently asked questions

_Where do I find my saved personalized learning paths?_

All your saved paths appear in the _Personalized Learning Paths_ strip on your home page. Each card shows the path name and a _Continue_ button. You can also open any path from there to see its full course list and your progress.

_How many personalized learning paths can I save?_

The _Personalized Learning Paths_ strip on your home page shows a maximum of 10 paths.

_What information should I provide to get a relevant Learning Path?_

At minimum, describe your learning goal or the specific challenge you are trying to address. The more context you provide, the better the path\. Useful information includes your current role, how long you have been doing it, any relevant prior experience, and how many hours per week you can realistically dedicate to learning.

_What happens if the agent cannot find matching courses for my topics?_

The agent tells you directly in the conversation that it could not find matching courses for one or more of your topics. It generates the path using only the topics where courses were available.

If the agent cannot find courses for any of your topics, it will inform you that it is unable to create a path for that goal. In either case, reach out to your learning administrator and let them know which topics had no content available. They can add relevant courses to the catalog so future path requests are covered.

<!-- 
_How does the agent decide which courses to include?_

The agent prioritizes your organization's internal course catalog above external sources. It selects courses based on relevance to your stated goal, whether the course level matches your proficiency, how recently the content was published or updated, and quality signals such as ratings and completion rates\. Your administrator controls which content sources are available. 
-->

_Can I adjust the topics in my learning path?_

Yes. During the conversation, you can ask the agent to add, remove, or change topics before the path is generated. The agent will update the topic list and regenerate the path to match.

_Can I change the individual courses in a generated path?_

No. Once the agent generates a path, the course selection is fixed. You cannot swap, remove, or replace individual courses. Whatever the agent recommends is what the path contains.

If the suggested courses do not feel right, the best approach is to go back and adjust your topics before generating. The agent selects courses based on the topics you confirm, so changing the topic scope or proficiency level will produce a different course set.

_Why does the agent keep asking follow-up questions?_

The agent needs enough clarity about your learning goal to identify relevant topics. If your initial message was broad, such as "I want to learn marketing", it will ask questions to narrow the scope. Providing more specific details about your role, the challenges you face, and what you want to be able to do after learning will help the agent move to topic generation faster.