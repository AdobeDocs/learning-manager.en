---
description: The AI Assistant (Beta) for learners is a GenAI‑powered chat companion in Adobe Learning Manager that helps learners get quick, accurate answers from their assigned learning content. Using natural language queries, learners can instantly retrieve focused responses with clear citations, making it easy to find the right information, verify sources, and learn efficiently without searching through entire courses.
jcr-language: en_us
title: AI Assistant for learners in Adobe Learning Manager
exl-id: 8203488d-74a6-4463-9383-76d16cabccfa
---
# AI Assistant for learners

The AI Assistant (Beta) for learners helps them quickly find answers from the assigned learning content without browsing through entire courses. You can ask questions in plain language and receive accurate, focused responses with source links to the relevant course content.

>[!IMPORTANT]
>
>The AI Assistant for learners is currently available as a beta feature. Capabilities, supported scenarios, and limitations may change as the feature evolves.


## What is the AI Assistant for learners

The AI Assistant is a GenAI-powered chat companion in Adobe Learning Manager that delivers quick, accurate answers to learner questions using the trusted learning content available to them in Adobe Learning Manager. It also includes citations, so learners always know the source of the information.

### Key capabilities of the AI Assistant

1. Intelligent question answering
    * Single-turn and multi-turn conversations
    * Natural language understanding in English
    * Answers derived from course, certifications, learning paths, and job aids
    * Smart clarifying questions when queries are ambiguous
    * Powered by Azure open AI LLM capabilities to generate responses
2. Content sources and citations
    * Retrieves answers from available resources present in supported catalogs.
    * Provides citations with direct links to source materials
    * Supports all ALM content formats static and Interactive: PDF, DOCX, PPTX, XLSX, Audio (mp3, wav, m4a), Video (mp4, mov, wmv), HTML, SCORM 2004, SCORM 1.2
3. User experience
    * Side panel interface accessible from all learner pages
    * Responsive design that adapts to content area
    * Chat history maintained within browser session
    * Clean slate on new login or page refresh
    * Teacher or tutor tone: friendly, clear, and pedagogically sound
4. Administrator controls
    * Enable or disable feature at account level
    * Control access by user groups
    * Select which catalogs are included for AI responses
    * Terms of Use acceptance requirement to follow Adobe AI guidelines

## What types of content does the AI Assistant support

The AI Assistant retrieves information from learning content assigned to you, including:

* **Documents:** PDF, Word, PowerPoint, Excel, HTML
* **Media:** Audio (mp3, wav, m4a), Video (mp4, mov, wmv)
* **Interactive content:** SCORM 1.2, SCORM 2004
* **Learning object types:** Courses, learning paths, certifications, job aids

Adobe securely transcribes learning content using trusted third‑party processing services hosted within Adobe's private VPC environment.

### Catalog and content source limitations

The Learner AI Assistant only uses content from **Internal catalogs** that are explicitly configured by administrators.

The following content sources are **not supported** in the current release:

* Shared catalogs
* Acquired catalogs
* External catalogs
* Default catalogs
* Third‑party content libraries (for example, LinkedIn Learning or Go1)

If a learner does not have access to a course or job aid, the AI Assistant will not surface information from that content, and citation links will not be accessible.

## Use cases of AI Assistant

### Technical learner

Sarah is a sales engineer learning about graphics cards. She needs to quickly understand the technical specifications and benefits to answer customer questions confidently.

The AI Assistant helps Sarah with:

* Clear, technical explanation of complex GPU architecture
* Deepen understanding about various graphic cards and their differences
* Explanation of examples so Sarah can relate features to real world use cases

### Customer support

Marcus is a support specialist at a partner company. He needs quick answers about product features to help customers without escalating to engineering teams.

The AI Assistant helps Marcus with:

* Finding relevant support content for freuently asked customer queries
* Asking clarifying questions when the initial answer isn't specific enough
* Finding recommendations for related troubleshooting courses to improve his skills

### New employee onboarding

Jennifer just joined the company and is overwhelmed by the amount of training material. She needs a way to find specific information without reviewing entire courses.

The AI Assistant helps Jennifer with:

* Getting a step-by-step guidance on submitting expense reports
* Discovering courses about company policies without browsing the entire catalog
* Guding her to the appropriate section of a course without making her watch hours of video

## How does the AI Assistant uses content

The AI Assistant helps you find accurate answers quickly while you learn. To use it effectively, you should understand what content the assistant uses, what it does not use, and how it generates responses.

### What content does the AI Assistant use

The AI Assistant answers questions using only the learning content enabled by the account administrator. The content from the catalog is indexed.

The AI Assistant analyzes your assigned learning content to generate focused and contextual responses.

* Every response includes citations that reference the original source content.
* You can select a citation to navigate directly to the relevant course, module, or document.
* Citations help you verify information and explore additional context when needed.

### Streaming responses

A streaming response means the AI Assistant delivers the answer progressively as it is generated, so users can start reading the response immediately without waiting for the entire answer to finish loading.

### Citations and source transparency

Every AI Assistant response includes citations that link directly to the original course, module, or learning object. Citations allow you to:

* Select an inline citation number to jump to the exact referenced section
* Open the full source list by selecting Show Sources at the bottom of the response
* Verify information and explore additional context from the authoritative source

>[!IMPORTANT]
>
>The AI Assistant provides answers based on content enabled by the administrator, but if a user lacks access to a referenced item, they will see a "not supported" message when opening it.


## Built-in prompts

The AI Assistant includes built-in prompts to help learners get started quickly with common questions and scenarios. These prompts guide learners on how to interact with the assistant and demonstrate the types of questions they can ask.

![Built-in-prompts provided by Learner Assistant](assets/built-in-prompt-new.png)

Built-in prompts are customizable per account. Organizations can tailor them to reflect their learning goals, learner roles, terminology, or specific use cases. Administrators can work with their Customer Success Manager (CSM) to configure or update built-in prompts. 

Prompt customization is managed at the account level and is not configurable directly within the Adobe Learning Manager user interface in the current release.

## Administrator setup- Enable AI Assistant for learners

![AI-enabed Learner Assistant](assets/learner-ai-assistant-new.png)

Administrators select which user groups and Internal catalogs can access the AI Assistant feature. They should ensure the catalogs assigned include only the learning content that is appropriate to be surfaced through AI responses and citations, and that those catalogs are Default, Internal, not Shared, Acquired, or External.

Before configuring the AI Assistant, confirm that you have administrator credentials and have identified which user groups and catalogs should have access to the feature.

### Configure AI Assistant access

To enable Learner AI Assistant:

1. Log in to Adobe Learning Manager as an administrator.

2. Select **Settings** from the home page.
![Administrator console with the Settings option on the left pane](assets/settings-menu.png)

3. Select **Learner AI Assistant (Beta)** from the **Settings** menu.
![Administrator console displays the Learner AI Assistant option on the left pane](assets/learner-assistant-ai-beta.png)

4. Select the toggle switch to enable the **Learner AI Assistant (Beta)**.
![Administrators console displays the toggle enabled for Learner AI Assistant](assets/learner-assistant-toggle.png)

5. Select one or more user groups from the **Eligible user groups** option.

6. Select **Save** to apply the user group settings.

7. Select one or more catalogs from the **Eligible Catalogs** option.

8. Select **Save** to apply the catalog settings.

>[!IMPORTANT]
>
>Only Internal catalogs are supported by the AI Assistant. If a Shared, Acquired, External, or other non‑Internal catalog is selected, its content will not be surfaced by the AI Assistant, even if the catalog appears in the Eligible Catalogs list.

## Learner guide- Launch the AI Assistant

### Launch the AI Assistant

To launch the AI Assistant:

1. Log in to Adobe Learning Manager as a learner.

2. Select **Ask AI Assistant** on the home page.
![Learner home page displays Ask AI Assistant to select and open the Learner AI Assistant panel](assets/ask-ai-assistant.png)

3. When the **Learner AI Assistant** screen appears, select **Get Started**.
![Select Get started to launch the Learner Assistant](assets/get-started-learner-assistant.png)

>[!NOTE]
>
>When launching the AI Assistant for the first time, you must provide your consent before using it. The consent dialog will only appear during this initial launch. For all subsequent launches, you will be taken directly to the AI Assistant to enter your prompts.

4.Type your prompt in the text field.

![Type prompt in the Learner Assistant](assets/type-prompt-new.png)

5.Press **Enter** to receive a response. Review your answer, sources, and recommendations.

You can:

* Select the citation number inline to jump to the exact referenced section
* Open the full list of sources by selecting **Show Sources** at the bottom of the response

![Display sources in the response](assets/show-sources-latest.png)

The AI Assistant includes citations with every response to show where the information comes from. Each citation links directly to the original course, module, or learning object used to generate the answer.

You can select any citation to open the actual course page in Adobe Learning Manaager and review the full content in context. Citations help you verify information, explore additional details, and continue learning from the authoritative source.

## Access the AI Assistant via search

You can also launch the AI Assistant directly from the search bar. Type your question in the search field, then select **Ask AI Assistant** from the options that appear to get answers from your assigned learning content.he assigned learning content.

![Access the Learner Assistant from search bar](assets/learner-assistant-search-new.png)


## Provide feedback on Learner AI Assistant responses

Your feedback on the responses generated by the Learner AI Assistant (Beta) helps improve its accuracy, relevance, and overall performance.

### Like or dislike a response

* Select **Thumbs Up**, choose what you found helpful in the response, optionally add comments, and then select **Submit**.

![Select Thumbs Up to upvote a response](assets/la-feedback.png)

* Select **Thumbs Down**, choose the reason the response was not helpful, add any comments, and then select **Submit**.

## Start a new chat in AI Assistant

Starting a new chat allows the user to begin a fresh conversation, clearing prior context so the assistant can focus on the new topic without referencing previous interactions. This is important when switching topics or seeking answers unrelated to earlier questions.

Clear the current conversation and start a new chat at any time.

Select **New chat** in the AI Assistant screen and then select **Yes**.

![Start a new chat in Learner Assistant](assets/start-new-chat.png)

The AI Assistant provides learners with fast, contextual answers, supports multiple content types, and offers inline citations for transparency. Administrators can control access, ensuring the AI Assistant is tailored to organizational needs and enhances the learning experience.


## Troubleshooting

>[!NOTE]
>
>After configuring a new catalog, allow 4–5 hours for the content to be indexed and available for AI Assistant responses.

### Scenario 1: No Access to content

Problem: Learner has access to Learner Assistant but receives 'I don't have an answer to this question' responses.

**Possible causes**

* Learner's catalogs are not included when configuring AI Assistant
* Content related to the question is not in selected catalogs or catalogs are blank
* Learner doesn't have visibility to relevant content

**Solution**

* Verify the learner's catalog access
* Check which catalogs are enabled in Learner Assistant settings
* Ensure relevant content exists in those catalogs
* ait few hours after adding new content for it to be indexed

### Scenario 2: Irrelevant or poor quality answers

**Problem**: The AI Assistant provides answers that don't match the question or are low quality.

**Possible causes**

* Question is too broad or ambiguous
* Relevant content has poor metadata (descriptions, tags)
* Content structure makes it difficult to extract information

**Solution**

* Encourage learners to ask more specific questions
* Review and improve course descriptions and metadata
* Ensure content has clear headings and structure
* Review the detailed usage report to identify patterns
* Consider creating job aids for frequently asked questions

### Scenario 3: Out of scope questions

**Problem**: Learner asks questions unrelated to training content.

**Examples**:

* General knowledge questions ('Who is the president?')
* Personal opinions ('What do you think about X?')
* Inappropriate content
