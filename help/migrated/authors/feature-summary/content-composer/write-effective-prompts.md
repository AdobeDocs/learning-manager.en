---
description: The prompt is the most important input in Content Composer. A specific prompt, such as naming the audience, 2–3 topics, and a scope signal, produces a more accurate brief, a stronger outline, and less editing downstream.
jcr-language: en_us
title: Write effective prompts in Content Composer
---

# Write effective prompts in Content Composer

Learn how to write effective prompts at every stage of Content Composer, from the opening prompt through the brief, outline, and course editor, to produce accurate, well-structured AI-generated courses with less editing. 

Content Composer is conversational throughout. The quality of what it produces at every stage depends on the quality of what you give it. This guide covers how to communicate with the AI effectively at each of the four stages: **Home**, **Brief**, **Outline**, and **Course**.

## Stage 1: Home- write your opening prompt

The opening prompt is your starting point. It doesn't need to be perfect. Content Composer reads your prompt and uses it to open a conversation. Even a rough prompt gets the process moving; the assistant will ask follow-up questions at the Brief stage to fill in what's missing.

That said, a more specific prompt means the AI pre-fills the Brief more accurately, reducing back-and-forth before you generate the outline. If you have a clear idea of the audience, title, and goal, put it in the prompt.

### What does Content Copmposer expect

Content Composer expects the following:

- **What** is the course about? Describe the subject area in one or two sentences. This becomes the course title.
- **Who** are the learners? Name their role and experience level. This becomes the learner profile.
- **What is the learning objective?** Describe the outcome or behavioural change you want learners to accomplish after completing the course. This becomes the learning objective in the Brief.

### Anatomy of an effective prompt

**[Learners + experience level]** + **[a specific title]** + **[learning objective]**

An effective prompt does three things: it describes what the course is about, who it's for, and what learners should be able to do after completing it.

**Example**:

I want to create a course for new sales representatives covering our enterprise pricing tiers and the discount approval workflow. By the end, they should be able to handle the three most common customer objections confidently.

Breaking this down:

- **Title:** A course on enterprise pricing, discount approvals, and handling customer objections for new sales representatives
- **Learner:** New sales representatives in their first 90 days, unfamiliar with enterprise pricing structures
- **Objective:** Handle the three most common customer objections confidently using the approved messaging framework

Once you select **Get started**, Content Composer opens the **Brief** stage. Review the pre-filled fields, the title, learner profile, and objective that the AI generated from your prompt, and refine anything that doesn't match your intent before generating the outline.

### Do's and don'ts of an effective prompt

| Include | Avoid |
|---|---|
| A clear course title or subject area | Vague subjects ("something on security", "a general training") |
| The learner's role or demographic ("new sales reps", "frontline warehouse staff") | Broad audiences ("all staff", "everyone", "users") |
| The learner's experience level ("early-career", "familiar with X but not Y") | Assuming the AI knows your audience's background |
| What learners currently struggle with or don't know | Skipping learning gaps. The AI uses them to shape vocabulary and scenarios |
| A clear learning objective — what learners will be able to do after the course | Generic goals ("teach them everything about X", "cover all aspects of") |

### Starter prompts by course type

| **Course type**                | **Starter prompt**                                                                                                                                                                                                                                       |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Compliance training**        | "I want to create a course for all employees on GDPR data handling, covering what counts as personal data, how to store and share it correctly, and what to do if a breach occurs."                                                            |
| **Onboarding**                 | "I want to create an onboarding module for new customer support agents covering how to log a ticket, escalate an issue, and close a case in our helpdesk system."                                                                                                                                              |
| **Technical skills**           | "I want to create a course for junior software engineers on secure coding practices, like SQL injection prevention, input validation, and how to read a SAST report."                                                                                    |
| **Soft skills**                | "I want to create a course for frontline retail managers on giving constructive feedback, such as covering the SBI model, how to prepare for a feedback conversation, and how to follow up."                                                   |
| **Policy and procedure**       | "I want to create a course for warehouse staff on manual handling procedures, like correct lifting technique, when to use equipment, and how to report a near-miss."                                                                                     |
| **Product training**           | "I want to create a course for customer support agents on our returns policy, such as covering the eligibility criteria, how to process a return in \[system\], and how to handle escalations."                                                          |
| **Sales enablement**           | "I want to create a course for mid-level account executives on negotiating enterprise deals, for example, covering how to identify decision-makers, how to handle price objections using our value framework, and when to escalate to a sales director." |
| **Leadership development**     | "I want to create a course for first-time people managers covering how to run a weekly 1:1 effectively, like setting an agenda, giving recognition, and addressing underperformance early."                                                    |
| **Systems and tools training** | "I want to create a course for HR coordinators who are new to Workday, such as covering how to create a job requisition, move a candidate through hiring stages, and generate a headcount report."                                                       |
| **Health and safety**          | "I want to create a refresher course for all site staff on fire safety procedures, for example, covering the evacuation route for each building zone, how to use a fire extinguisher, and what to do if you discover a fire outside working hours."      |

## Stage 2: Brief- sharpen the AI's suggestions

After you submit your prompt, Content Composer opens the Brief stage and pre-fills three fields: the course title, the learner profile, and the learning objective. The AI asks follow-up questions to sharpen each field before you generate the outline.

This is a conversational stage. The quality of your responses to the AI's questions directly determines the quality of the outline it produces.

### Course title

The AI pre-fills the course title based on your prompt. Review it and select it if it fits, type your own, or describe what you want instead:

"Neither. The course is specifically about the approval workflow, not general pricing."

### Learner profile

The AI asks about role, experience level, and what learners currently struggle with. Be specific about both what they know and what they don't:

| Less useful | More useful |
|---|---|
| "All employees" | "Mid-career software developers familiar with agile but with no enterprise security compliance experience" |
| "New to the topic" | "Early-career managers promoted from individual contributor roles with no formal management training" |
| "Our sales team" | "New account executives in their first 90 days, comfortable with CRM tools but unfamiliar with enterprise pricing structures" |

### Learning objective

The AI asks what learners will be able to do on the job after completing the course. This is the most important Brief field — it controls what the AI prioritises in your source files, how the outline is structured, and what the quiz tests.

Write the objective as a behaviour starting with an action verb:

| Weak objective | Strong objective |
|---|---|
| "Understand data protection" | "Identify personal data, apply correct storage and sharing practices, and report a suspected breach using the organisation's reporting process" |
| "Learn about objection handling" | "Respond to the three most common customer objections using the approved messaging framework, without escalating to a sales director" |
| "Know the onboarding process" | "Complete the first-week onboarding checklist, submit the required compliance forms, and access the tools needed for their role without IT assistance" |

>[!IMPORTANT]
>
>**Before you generate the outline:** The outline is built entirely from the Brief, not from your original prompt. Before selecting **Generate Outline**, confirm that the title is learner-facing, the learner profile names a specific role and experience level, and the learning objective describes a measurable on-the-job behaviour. A well-defined Brief produces a well-structured outline. If any field still feels generic, refine it now.  It saves significant editing later.

You are always in control. Content Composer will ask follow-up questions to help refine the Brief, but you decide what goes in each field. A well-defined Brief produces a well-structured outline. The more specific your inputs, the less editing you'll need later.

### Signs the Brief needs more work

- The learner profile says "employees who want to learn about X" rather than naming a specific role and experience level
- The learning objective describes a subject area rather than a measurable on-the-job behaviour
- The title is vague ("IT Security") rather than a learner-facing outcome ("Identify and respond to phishing attempts")

## Stage 3: Outline- edit through conversation

After you confirm the Brief, Content Composer generates a lesson and topic structure. You review it and request changes through the chat panel before generating the full course.

Outline editing is entirely conversational in the current release. You cannot select a lesson or title on the canvas to rename or reorder it. All changes are made by typing plain-language requests.

This is also the most effective stage to make structural changes. Editing the outline takes seconds. Restructuring a generated course takes significantly longer.

### How to phrase outline editing requests

Be direct and specific. Name the lesson by its current title, describe the change you want, and optionally explain why.

**Rename:**

- "Rename Lesson 1 to 'How Phishing Attacks Work'."
- "Rename title 2.3 to 'Escalation paths and timelines'."

**Add:**

- "Add a new topic to Lesson 2 about QR code phishing."
- "Add a lesson on incident response after Lesson 4."

**Remove:**

- "Remove topic 1.3."
- "Delete Lesson 5. That content is covered in a separate course."

**Reorder:**

- "Move Lesson 3 to be the second lesson."
- "Move topic 2.1 to the end of Lesson 2."

**Split:**

- "Split Lesson 3 into two lessons, one covering spam filters, and one covering patch management."

**Merge:**

- "Merge Lessons 4 and 5 into a single lesson called 'Incident Response and Recovery'."

**Regenerate:**

- "Regenerate the outline with a stronger focus on password hygiene and MFA."
- "Regenerate the outline — the current structure is too technical for a non-technical audience."

### What the outline stage cannot do

- The hierarchy is fixed as Lessons > Topics. You cannot create sub-topics or three-level structures.
- You cannot add components or media at this stage. Those are added in the Course editor.

<!--
### When to regenerate versus when to edit

| Use conversational editing when... | Regenerate when... |
|---|---|
| The overall structure is right but individual names or topics need adjusting | The overall structure doesn't match your intent at all |
| You want to add or remove specific items | The Brief was refined significantly after the first outline was generated |
| One lesson needs splitting or merging | The outline feels generic and lacks your organisation's specific context |
-->

## Stage 4: Course- refine content through the assistant

After you approve the outline and generate the course, the **Create with Content Composer** panel remains open on the right side of the screen. You can use it to refine, expand, or adjust any part of the generated course through conversation.

The assistant in the Course editor is designed for content editing tasks. For product how-to questions, use this help documentation rather than asking the assistant.

### How to phrase course editing requests

**Rewrite or adjust a specific section:**

- "Rewrite the paragraph in the second section of Lesson 1 to be more concise — aim for three sentences."
- "Make the content in topic 2.1 less technical. The audience has no IT background."
- "Add a real-world example to the introduction of Lesson 1."

**Adjust tone:**

- "Rewrite Lesson 2 in a more conversational tone."
- "Make the content in topic 3.2 more authoritative — this is a compliance course."

**Expand or add content:**

- "Add a scenario-based example to topic 1.3 showing how a phishing email might look."
- "Expand the section on MFA to include instructions for setting it up on mobile."

**Reduce or simplify:**

- "Shorten the text on slide 5 to three bullet points."
- "Summarize the second paragraph in topic 2.2 in one sentence."

**Adjust the quiz:**

- "Regenerate the quiz for Lesson 2 with harder questions."
- "Replace question 3 with a scenario-based question about recognising a social engineering attempt."
- "Add two more questions to the Lesson 1 quiz focused on MFA setup."

**Adjust images:**

- "Replace the image in topic 2.2 with something that shows a social engineering scenario."
- "Generate an image for topic 1.1 that illustrates a phishing email on a laptop screen."

**Add or modify components:**

- "Add a flip card to topic 3.1 with the three pricing tier definitions."
- "Add an accordion to topic 2.3 with the escalation steps — one panel per step."
- "Convert the bullet list in topic 1.2 into a timeline component."

### What the Course assistant cannot do

- Rename lessons or topics directly on the canvas. Use the assistant: "Rename Lesson 2 to 'Password Hygiene'."
- Create branching or adaptive paths. The course structure is linear.
- Add new lessons or restructure the outline. Structural changes require returning to the Outline stage.

## Best practices across all stages

- **Describe what you want to build before opening Content Composer.** A sentence drafted in advance tends to be clearer than one typed under the pressure of the input field.
- **Invest time in the learning objective.** The objective in the Brief controls the outline structure, source file prioritisation, and quiz alignment. A specific, behaviour-focused objective reduces editing at every subsequent stage.
- **Refine the Brief before generating the outline.** The outline is built from the Brief, not the original prompt. A well-defined Brief with a specific learner profile and learning objective produces a structured, relevant outline.
- **Edit the outline before generating the course.** Structural changes at the outline stage take seconds. The same changes after course generation take significantly longer.
- **Use the Course assistant for content, not structure.** Structural changes, adding lessons, reordering topics, belong in the Outline stage. Use the Course assistant for refining text, tone, examples, and quiz questions.
- **Be specific in every request.** Name the lesson, topic, slide, or question you want to change. "Make it better" gives the AI nothing to act on. "Make topic 2.1 more concise and add a real-world example" does.
