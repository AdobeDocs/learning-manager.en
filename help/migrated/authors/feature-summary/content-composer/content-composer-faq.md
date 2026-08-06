---
description: Find answers to the most common Content Composer questions, including why Generate Outline is greyed out, how to rename a lesson, why quiz questions feel misaligned, and what to do when Publish is disabled.
jcr-language: en_us
title: Adobe Learning Manager Content Composer FAQ
---

# Adobe Learning Manager Content Composer FAQ

Get answers to frequently asked questions about using Content Composer.

**The Generate Outline button is grayed out. What do I do?**

All three **Brief** fields, **Title**, **Learners**, and **Objective,** must contain content before **Generate Outline** activates. Check the canvas for any field still showing placeholder text in italics, such as *Enter the Learners profile here* or *Enter the Objective of this course*. Fill in the empty field and the button activates immediately.

**I can't select the outline to rename a lesson. Why?**

Outline editing is conversational in the current beta. You cannot select a lesson or topic on the canvas to rename or reorder it. Type your change in plain language in the assistant chat panel.

Examples:

- "Rename Lesson 1 to 'How Phishing Works'"

- "Move topic 1.3 to be the first topic in Lesson 2"

- "Delete Lesson 4 and distribute its topics across Lesson 3"

**The generated outline doesn't match what I wanted. What went wrong?**

The outline reflects the prompt and brief. If the structure feels off, the most common causes are a prompt that covers too many topics at once, or a learning objective that doesn't name the specific skills or behaviors the course should develop.

**The AI skipped an important section of my uploaded file. How do I fix this?**

Content Composer prioritizes sections of your source file that are most relevant to your learning objective. If a section was skipped, it likely wasn't reflected in the objective.

To fix this:

1. Return to the **Brief** panel and update the objective to explicitly name the missing topic.

2. Ask the assistant to regenerate the outline: "Regenerate the outline, making sure to include the data retention policy section."

You can also add the missing content manually as a new topic in the outline conversation: "Add a new topic to Lesson 2 called 'Data Retention Policy'."

**Can I use Content Composer with Adobe Captivate?**

No. Content Composer and Adobe Captivate do not share a round-trip workflow. You cannot open Content Composer projects in Captivate, and you cannot open Captivate projects in Content Composer.

A Captivate-exported MP4 can be inserted as a **Video** component in Content Composer.

**Can I use Content Composer for compliance or regulated training?**

Yes. This is one of its strongest cases. Upload your policy or procedure documents in Manage source files, and select Restrict output to content in files so the AI generates only from what you provided rather than supplementing with general knowledge.

**Why are knowledge checks not graded?**

Knowledge checks in Content Composer are designed for learning reinforcement during a lesson, not for scoring. They provide immediate feedback to the learner but do not produce a grade or completion record.

Only end-of-lesson quiz assessments are graded. If you need an assessment that contributes to a learner's score, use the quiz, not a knowledge check component.

**The quiz questions don't match what the course teaches. How do I fix this?**

Content Composer uses AI to generate quiz questions, and AI output is non-deterministic. The questions may not always reflect exactly what you expect. Review all quiz questions after the course is generated, edit any that need adjustment directly in the Course editor, and verify the content is accurate before publishing.
