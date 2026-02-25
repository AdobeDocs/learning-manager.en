---
description: Learner AI Assistant (Beta) is a GenAI‑powered chat companion in Adobe Learning Manager that helps learners get quick, accurate answers from their assigned learning content. Using natural language queries, learners can instantly retrieve focused responses with clear citations, making it easy to find the right information, verify sources, and learn efficiently without searching through entire courses.
jcr-language: en_us
title: Learner AI Assistant (Beta) in Adobe Learning Manager
exl-id: 8203488d-74a6-4463-9383-76d16cabccfa
---
# Learner Assistant

The Learner AI Assistant (Beta) for learners helps them quickly find answers from the assigned learning content without browsing through entire courses. You can ask questions in plain language and receive accurate, focused responses with source links to the relevant course content.

>[!IMPORTANT]
>
>Learner AI Assistant is currently in Beta and is being released through a phased rollout. Access may vary by user.


## What is the Learner AI Assistant?

Learner AI Assistant is a GenAI-powered chat companion in Adobe Learning Manager that delivers quick, accurate answers to learner questions using the trusted learning content available to them in Adobe Learning Manager. It also includes citations, so learners always know the source of the information.

## Why use it?

* Learners face content overload and often don't know where to begin or which resource to use.

* Catalog and access rules make it difficult to discover what content is available to them.

* Learning journeys are fragmented across multiple formats and training types, such as courses, virtual classrooms, job aids, and assessments.

* There is no easy, unified way to retrieve specific information from diverse formats like SCORM, PDFs, documents, videos, or transcripts.

* Different learner roles and industries (e.g., sales, marketing, support, operations) have unique information needs that require quick, contextual answers.

## What types of content can the AI Assistant transcribe

The AI Assistant can find information from all types of learning content assigned to you, including:

* **Documents:** PDF, Word, PowerPoint, Excel, HTML

* **Media:** Audio (mp3, wav, m4a), Video (mp4, mov, wmv)

* **Interactive Content:** SCORM 1.2, SCORM 2004, 

* **Learning Object Type:** Courses, learning paths, certifications, job aids

Adobe securely transcribes your learning content using trusted third-party processing services hosted within Adobe's private VPC environment.

**IMPORTANT**

The AI Assistant only consumes content that is:

* Available in the catalogs configured for Learner Assistant by admins, and

* Part of internal catalogs in Adobe Learning Manager.

Shared, Acquired, External, or other non‑Internal catalogs are not supported as content sources for the AI Assistant in the current release.

If you don't have access to a course, the related citation links will not be accessible to you. Third‑party libraries (like LinkedIn Learning or Go1) are not included for retrieving answers.

## Conversational capabilities

The AI Assistant supports both single questions and multi-turn conversations. It reminds your previous queries within the same session.

**Example conversation:**

You: "What's the refund policy?"
Assistant: Provides summary
You: "What about refunds after 30 days?"
Assistant: Returns more specific information

## Use cases for AI Assistant

### Just‑in‑time learning support (all learners)

Learners often need quick answers while working, not full course replays. The AI assistant enables instant retrieval of precise information from assigned learning content.

**What it helps with:** 

* Get direct answers to specific questions from courses, job aids, and documents

* Jump to exact referenced sections using citations

* Reduce time spent searching across multiple Learning Objects

![Just-in-time learning support using Learner Assistant](assets/just-in-time.png)

### Sales enablement and customer conversations

Sales teams need fast, accurate product and process information during live customer interactions. The AI assistant acts as an on‑demand knowledge companion.

**What it helps with:**

* Retrieve up‑to‑date product features and positioning

* Generate quick sales scripts or talking points from training content

* Compare product versions or offerings using assigned learning material

* Reinforce sales knowledge without retaking entire courses

![Sales enablement using Learner Assistant](assets/sales-enablement.png)

**Example 2**

**Purpose:** Show that the AI Assistant can help sales reps answer customer comparison questions instantly.

**Recommended Prompt:** Compare Adobe Learning Manager and a traditional LMS for enterprise training. Show the comparison in a tabular format.

![Tabular output in the Learner Assistant](assets/tabular-format.png)

### Marketing and campaign readiness

Marketing teams frequently need quick refreshers before reviews, launches, or stakeholder discussions. The AI assistant summarizes complex learning content into actionable insights.

**What it helps with:**

* Summarize long courses or videos into key takeaways

* Refresh process or product knowledge before meetings

* Discover related learning content to deepen expertise

![marketing and campaign  readiness using Learner Assistant](assets/marketing-readiness.png)

### Operational and process clarification

Operations, support, and internal teams rely on accurate process documentation. The AI Assistant helps clarify policies and workflows instantly.

**What it helps with:** 

* Find answers about internal processes, SOPs, and compliance guidelines

* Clarify step‑level details without browsing lengthy documents

* Reduce dependency on SMEs for repetitive questions

![Operational and process documentation using Learner Assistant](assets/operational-process.png)

### Faster onboarding and role transitions

New hires and employees moving into new roles often struggle to navigate large learning catalogs. The AI assistant accelerates ramp‑up by guiding them to relevant answers.

**What it helps with:** 

* Answer common onboarding questions from assigned content

* Provide quick explanations of role‑specific concepts

* Support self‑directed learning without information overload

![Onboarding employees](assets/onboarding.png)

### Knowledge refresh and continuous learning

Experienced learners need quick refreshers rather than full retraining. The AI Assistant supports continuous learning in the flow of work.

**What it helps with:** 

* Refresh knowledge on demand without re‑watching courses

* Reinforce learning outcomes after training completion

* Encourage frequent, low‑effort engagement with learning content

![Knowledge refresh response in Learner Assistant](assets/knowledge-refresh.png)

## How the Learner AI assistant uses content

The Learner AI assistant helps you find accurate answers quickly while you learn. To use it effectively, you should understand what content the assistant uses, what it does not use, and how it generates responses.

### What content does the AI Assistant use

The Learner AI Assistant answers questions using only the learning content assigned to you in Adobe Learning Manager.

* The assistant uses content from Internal catalogs that your administrator enables for the learner AI assistant.

* The assistant respects your role, group membership, and catalog permissions when retrieving information.

### What content does the AI Assistant not use

The Learner AI Assistant limits responses to your assigned learning scope.

* It does not use content from Default, Shared, Acquired, External, or other non‑Internal catalogs.

* It does not retrieve information from third‑party content libraries such as LinkedIn Learning or Go1.

* It does not browse the internet or access external websites to generate answers.

### How the AI Assistant generates answers

The Learner AI Assistant analyzes your assigned learning content to generate focused and contextual responses. 

* Every response includes citations that reference the original source content.

* You can select a citation to navigate directly to the relevant course, module, or document.

* Citations help you verify information and explore additional context when needed.

### Use the AI Assistant responsibly

Use the Learner AI Assistant as a learning aid to explore, refresh, and reinforce knowledge. 

* Treat responses as guidance based on available learning content.

* Refer to the cited source material for complete and authoritative information.

### How administrators control access

Administrators manage access to the Learner AI Assistant and control the content it uses.

* Administrators assign the assistant to specific user groups.

* Administrators select which Internal catalogs the assistant can use as content sources.

* These controls ensure that the assistant surfaces only approved and relevant learning content.

## About built-in prompts

The Learner AI Assistant includes a set of built‑in prompts to help learners get started quickly with common questions and scenarios. These prompts guide learners on how to interact with the assistant and demonstrate the types of questions they can ask.

![Built-in-prompts provided by Learner Assistant](assets/built-in-prompts.png)

Built‑in prompts are customizable per account. Organizations can tailor these prompts to reflect their learning goals, learner roles, terminology, or specific use cases.

Administrators can work with their Customer Success Manager (CSM) to configure, modify, or update the built‑in prompts for their account. Prompt customization is managed at the account level and is not configurable directly within the Adobe Learning Manager user interface in the current release.

The prompts shown to learners may vary by account based on the configuration defined with Adobe.

## Enable Learner AI Assistant 

![AI-enabed Learner Assistant](assets/learner-ai-assistant.png)

The AI Assistant (Beta) provides AI-powered support to help learners discover and engage with content more effectively. Administrators control access by assigning the feature to specific user groups and catalogs. Only Internal catalogs should be used when configuring the AI Assistant. Content from Shared, Acquired, External, or other non‑Internal catalogs is not supported for surfacing in AI Assistant responses and citations.

Administrators select which user groups and Internal catalogs can access the AI Assistant feature. They should ensure the catalogs assigned include only the learning content that is appropriate to be surfaced through AI responses and citations, and that those catalogs are Internal, not Shared, Acquired, or External.

Before configuring the AI Assistant (Beta), confirm that you have administrator credentials and have identified which user groups and catalogs should have access to the feature.

### Configure Learner Assistant access

To enable Learner AI Assistant:

1.Log in to Adobe Learning Manager as an administrator.

2.Select **Settings** from the home page.

![Administrator console with the Settings option on the left pane](assets/settings-menu.png)

3.Select **Learner AI Assistant (Beta)** from the **Settings** menu.

![Administrator console displays the Learner AI Assistant option on the left pane](assets/learner-assistant-ai-beta.png)

4.Select the toggle switch to enable the **Learner AI Assistant (Beta)**.

![Administrators console displays the toggle enabled for Learner AI Assistant](assets/learner-assistant-toggle.png)

5.Select one or more user groups from the **Eligible user groups** option.

6.Select **Save** to apply the user group settings.

7.Select one or more catalogs from the **Eligible Catalogs** option.

8.Select **Save** to apply the catalog settings.

>[!IMPORTANT]
>
>Only Internal catalogs are supported by the AI Assistant. If a Shared, Acquired, External, or other non‑Internal catalog is selected, its content will not be surfaced by the AI Assistant, even if the catalog appears in the Eligible Catalogs list.

## Access Learner AI Assistant in Adobe Learning Manager

Adobe Learning Manager's Learner AI Assistant (Beta) helps you find answers quickly while you learn. This intelligent tool responds directly to your questions about courses, content, and platform features, all from your learner account.

The AI Assistant can only use content from Internal catalogs that your administrator has enabled for Learner Assistant. Content that lives only in Shared, Acquired, or External catalogs is not included.

The Learner AI Assistant (Beta) is available only to selected learners.  

### Launch the AI Assistant

To launch Learner AI Assistant:

1.Log in to Adobe Learning Manager as a learner.

2.Select **Ask AI Assistant** on the home page.

![Learner home page displays Ask AI Assistant to select and open the Learner AI Assistant panel](assets/ask-ai-assistant.png)

3.When the **Learner AI Assistant (Beta)** screen appears, select **Get Started**.

![Select Get started to launch the Learner Assistant](assets/get-started-learner-assistant.png)

>[!NOTE]
>
>When launching the AI Assistant for the first time, you must provide your consent before using it. The consent dialog will only appear during this initial launch. For all subsequent launches, you will be taken directly to the AI Assistant to enter your prompts.

4.Type your prompt in the text field.

![Type prompt in the Learner Assistant](assets/type-prompt.png)

5.Press **Enter** to receive a response. Review your answer, sources, and recommendations.

Adobe allows prompt customization at the account level. To configure or update built‑in prompts, contact your Adobe Customer Success Manager (CSM).

AI Assistant responses include citations with every response so learners can easily verify where the information is coming from. Each cited reference links back to the original course module, job aid, or other learning content.

Learners can:

* Select the citation number inline to jump to the exact referenced section

* Open the full list of sources by selecting **Show Sources** at the bottom of the response

![Display sources in the response](assets/show-sources.png)

The Learner Assistant includes citations with every response to show where the information comes from. Each citation links directly to the original course, module, or learning object used to generate the answer.

You can select any citation to open the actual course page in Adobe Learning Manaager and review the full content in context. Citations help you verify information, explore additional details, and continue learning from the authoritative source.

## Access the AI Assistant using search

Admins can also launch the AI Assistant directly from the search bar. Simply type your question, and select **Ask AI Assistant** from the options that appear below to get answers from the assigned learning content.

![Access the Learner Assistant from search bar](assets/learner-assistant-search.png)

## Provide feedback on Learner AI Assistant (Beta) responses

Your feedback on the responses generated by the Learner AI Assistant (Beta) helps improve its accuracy, relevance, and overall performance.

### Like or dislike a response

* Select **Thumbs Up**, choose what you found helpful in the response, optionally add comments, and then select **Submit**.

![Select Thumbs Up to upvote a response](assets/thumbs-up.png)

* Select **Thumbs Down**, choose the reason the response was not helpful, add any comments, and then select **Submit**.

![Select Thumbs Down to downvote a response](assets/thumbs-down.png)

## Start new chat in AI Assistant

Learners can clear the current conversation and start a new chat at any time.

* Select **New chat** in the AI Assistant screen and then select **Yes**.

![Start a new chat in Learner Assistant](assets/start-new-chat.png)
