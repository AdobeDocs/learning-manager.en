---
description: Find answers to common questions about Virtual Coach authoring, licensing, security, data privacy, scoring, and the learner experience
jcr-language: en_us
title: Virtual Coach FAQ
exl-id: b8955b04-4655-413a-b570-a05b1f76285c
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
---

# Virtual Coach FAQ

## Authoring

Get answers to common questions about building, configuring, and troubleshooting a Virtual Coach role-play.

1. **Why did my role-play score zero even though I covered most of the topics?**
Check whether one of your topics has **Make or Break** enabled. If a learner doesn't address a Make or Break topic at all during the conversation, the simulation's final score is 0 regardless of how well they performed on everything else. Reserve Make or Break for one or two genuinely non-negotiable topics to avoid this happening on a reasonable attempt. For the full setup, see [create and publish a Virtual Coach role-play](/help/migrated/authors/feature-summary/virtual-coach/create-publish-virtual-coach-role-play.md).

2. **How many personas can a multi-persona role-play include?**
Up to four personas in a single scenario, each configured individually with its own **Role**, **Personality**, and **Persona Concerns**. Use this when a learner needs to navigate more than one stakeholder in the same conversation, such as a buying-committee pitch or an executive panel review.

3. **How do I choose between voice, chat, and video for a role-play?**
This depends on the persona type you select. **System Personas** support either **Voice & Video** (an animated avatar with a spoken voice) or **Voice** only. **Custom Personas** support voice interaction, and you can enable **Video Avatar** separately for personas that support Voice & Video mode. Choose Voice & Video for the most realistic simulation, or Voice only for scenarios where a visual avatar isn't necessary, such as phone-based training.

4. **How do I write a good prompt for the AI Co-create Assistant?**
Enter a short description that outlines the scenario, such as `Handling price objections in enterprise sales` or `Pitching our new product to a buying committee`. The AI assistant then asks follow-up questions to help you build the Overview, AI persona, and Evaluation Topics. Provide as much context as you can about the situation, the persona's role and concerns, and how you want to measure success — more detail in your initial description means less back-and-forth in the chat. See [gather materials for a Virtual Coach role-play](/help/migrated/authors/feature-summary/virtual-coach/gather-materials-for-virtual-coach-role-play.md) for a fuller prompt template.

5. **Can I edit a role-play after it's published?**
Yes. Changes to persona settings, topics, and other configuration take effect immediately for any unpublished role-play. If a role-play is already published and assigned to learners, republish it after making changes so learners see the latest version.

For general product, licensing, and admin questions, see the [Adobe Learning Manager Virtual Coach FAQ](/help/migrated/authors/feature-summary/virtual-coach/virtual-coach-faq.md).

## Training and compliance

1. **How does Virtual Coach protect customer and learner data?**
Customer data is stored using AES‑256 encryption, secured in transit using TLS 1.3+, and logically separated by unique customer identifiers to ensure isolation between customer environments. These controls are validated through annual third-party penetration testing.

2. **Where is Virtual Coach data stored and processed?**
Customer data is stored in EU data centers, supporting alignment with European privacy requirements.

3. **How long does Virtual Coach retain customer and learner data, and can it be deleted?**
Session data may be retained for the duration of the service agreement, and customers can configure company-specific retention policies. Individual users can delete their own recordings, administrators can perform bulk deletions, and data can be exported before deletion. Automatic deletion mechanisms and audit logging are also supported.

4. **Is customer-uploaded content used for purposes other than generating the role-play, such as AI training or product improvement?**
No, customer data is not used for AI training.

5. **How does Virtual Coach use AI, and what safeguards are in place for AI-generated responses?**
Virtual Coach uses generative AI to create interactive role-play experiences. Multiple safeguards are in place, including Azure OpenAI content filters for categories such as violence, hate speech, sexual content, and self-harm; prompt-level guardrails; and contextual controls that keep the AI focused on learning and development use cases. AI safety testing is also conducted, and safeguards such as Safety-Based Prompt Transformation and clarify-then-decline behavior are used for sensitive requests. Additionally, contractual commitments require disclosure of AI-generated outputs and compliance with applicable AI regulations.

6. **What privacy and compliance standards does Virtual Coach support?**
Virtual Coach supports GDPR-related privacy protections, configurable retention controls, audit logging, user deletion capabilities, and EU-based data hosting. The contractual agreement also requires compliance with applicable laws and regulations, including the EU AI Act and the California AI Transparency Act (SB‑942).

7. **Who owns content uploaded to Virtual Coach and the content generated during a session?**
The customer owns the content uploaded to Virtual Coach and the content generated during a session.

8. **Where does Virtual Coach data reside, within Adobe Learning Manager or with the Virtual Coach service provider?**
Role-play data is stored within the Virtual Coach service provider's cloud infrastructure and hosted in EU data centers.

## Product

1. **How is Virtual Coach activated for an existing Adobe Learning Manager customer?**
See [Activating Virtual Coach](/help/migrated/administrators/feature-summary/virtual-coach/manage-virtual-coach-usage-billing.md#activatevirtualcoach)

2. **How long is the Virtual Coach activation valid, and how is it renewed?**
Virtual Coach activation in Adobe Learning Manager is valid for the duration of your add-on subscription contract. It is not automatically perpetual. Instead, the validity aligns with your subscription period.

    **Renewal:** To continue using Virtual Coach after your contract period ends, you must renew your subscription. At the time of purchase, Adobe provides an activation key, which the account administrator uses to enable Virtual Coach in the Billing section. If you renew your contract, you will receive instructions and a new activation key if needed to maintain uninterrupted access.

    Monthly Active User (MAU) credits are also allocated for each contract period. Any unused credits at the end of the contract lapse. They do not carry over into a renewed or new period. Your activation lasts as long as your paid Virtual Coach subscription is active, and renewal occurs by extending your subscription, as managed through your Adobe account.

3. **What happens to uploaded source documents and generated session data after a role-play is created or completed?**
Uploaded source documents can be used to create and configure role-play scenarios, personas, and evaluation criteria. After learners complete a role play, Virtual Coach generates evaluation results, scores, coaching feedback, and completion information to support learning and reporting activities. Data associated with role plays remains available according to the applicable content lifecycle and retention policies.

4. **Can learners retry a role-play?**
Yes. Learners can repeat a role-play session multiple times to practice their skills, apply coaching feedback, and improve their performance. After completing a role play, learners can review their feedback and start another attempt to continue developing their skills.

## General

1. **What is Virtual Coach?**
Virtual Coach is an AI-powered role-play and coaching feature built into Adobe Learning Manager. It lets learners practice real-world conversations with an AI persona that responds intelligently in real time, then receive an instant performance report covering what they said and how they said it. For a full explanation, see [what Virtual Coach is](/help/migrated/authors/feature-summary/virtual-coach/what-virtual-coach-is.md).

2. **Who uses Virtual Coach?**
Organizations use Virtual Coach to train sales representatives, customer service teams, call center agents, managers and leaders, new hires, partners, and employees learning new products or processes. Virtual Coach is available to all learners, authors, and administrators in an Adobe Learning Manager account where it's been activated. Learners access and complete role-play sessions, authors create and publish role-play scenarios, and administrators manage credits and view reports.

3. **Does Virtual Coach automatically use my existing Adobe Learning Manager content?**
No. Authors must provide reference materials, such as playbooks, sales decks, transcripts, and scoring rubrics, or a written prompt, for each role-play they create. Virtual Coach uses those uploaded materials and persona definitions to drive the conversation; it doesn't automatically draw on content already in your Content Library or courses. See [gather materials for a Virtual Coach role-play](/help/migrated/authors/feature-summary/virtual-coach/gather-materials-for-virtual-coach-role-play.md) for what to prepare.

4. **What types of role-plays are available?**
Virtual Coach supports three domains: Sales Enablement, Leadership Development, and Skills Assessment. Authors choose from pre-built templates covering scenarios such as B2B discovery calls, cold calls, handling objections, giving difficult feedback, and de-escalating customer complaints. Authors can also create custom scenarios from scratch using the AI assistant. See [create and publish a Virtual Coach role-play](/help/migrated/authors/feature-summary/virtual-coach/create-publish-virtual-coach-role-play.md).

5. **What languages does Virtual Coach support?**
Virtual Coach is available in nine languages for both the interface and simulation content: German (Germany), Spanish (LATAM), Spanish (Spain), French (France), Italian (Italy), Portuguese (Portugal), Portuguese (Brazil), Dutch (Netherlands), and English.

6. **How is Virtual Coach licensed and billed?**
Virtual Coach is available as an add-on subscription to Adobe Learning Manager. Usage is measured in Monthly Active Users (MAUs). An MAU credit is consumed when a learner launches a course in a calendar month; additional sessions by the same learner that month don't consume additional credits. Unused credits at the end of the annual contract lapse. See [manage Virtual Coach usage and billing](/help/migrated/administrators/feature-summary/virtual-coach/manage-virtual-coach-usage-billing.md).

7. **How is a learner's score calculated?**
Each session produces a Knowledge score and a Style score. The Knowledge score reflects whether the learner addressed the required topics and provided accurate information. The Style score reflects how the learner communicated, including pace, clarity, filler words, sentence strength, and vocal energy. Authors set the weight of each component when configuring the scenario; a common configuration is 70% Knowledge and 30% Style. See [understand your Virtual Coach performance report](/help/migrated/learners/feature-summary/virtual-coach/understand-virtual-coach-performance-report.md).

8. **Can learners download their performance report?**
Yes. In addition to viewing the report on screen, learners can download it as a PDF to keep for their own records or share with a manager.

9. **Can a learner retry a role-play?**
Yes. Learners can attempt a role-play as many times as they want. Each attempt is a new, independent session and generates a new performance report. Only the first session in a calendar month consumes an MAU credit.

10. **Can learners submit their sessions for human review?**
No.

11. **Is Virtual Coach available on mobile?**
Virtual Coach is supported on the Adobe Learning Manager desktop and mobile web, and by APIs. It's not available in the Adobe Learning Manager mobile app (iOS/Android) in the current release.

12. **Is learner data used to train the AI?**
No. Virtual Coach is hosted on GDPR-compliant infrastructure, and no personal learner data is used to train AI models.

13. **What's the difference between a job aid and a course module for Virtual Coach?**
A job aid is a standalone, on-demand resource that learners can access directly from the Catalog at any time without being enrolled in a course. A course module is accessed as part of a structured course sequence with enrollment, completion tracking, and formal assessment. The same role-play can be published as a job aid and added to multiple courses simultaneously. See [add a Virtual Coach role-play to a course](/help/migrated/authors/feature-summary/virtual-coach/add-virtual-coach-role-play-to-course.md).

14. **How should we package Virtual Coach when rolling out a new process or product?**
Package the role-play inside a course or learning journey alongside the related training content, and distribute the course link through email or other change-management communications. Virtual Coach works best positioned as the last mile of training — the checkpoint right after learners complete related content, where they demonstrate they can apply it, rather than as a standalone activity.

15. **Is Virtual Coach supported on headless or API implementations?**
Public APIs for fetching courses and job aids also fetch Virtual Coach courses and job aids. The `jobAidType` filter is available for fetching Virtual Coach job aids specifically. Virtual Coach content is supported in the headless player, and courses and job aids containing Virtual Coach work in the fluidic player.

For questions about building and configuring a role-play, see this FAQ page.
