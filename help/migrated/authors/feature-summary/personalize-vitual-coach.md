---
jcr-language: en_us
title: Personalize your virtual coach simulation  
description: Learn how to personalize your virtual coach simulation using conversation context, persona background information etc.
contentowner: mmanuel
---

# Personalize your Virtual Coach simulation

Define the conversation context, the persona's background, and the persona's concerns to make your roleplay scenario realistic and challenging. The more detail you provide in each field, the more accurately and consistently the AI persona behaves during the simulation.

The **Personalize Your Simulation** screen is part of the **Edit Role-Play** flow. If you used **Co-Create with AI** or **Auto-Generate Role-Play**, these fields are pre-filled based on your inputs; review and refine them before publishing.

## Conversation Context

The Conversation Context sets the stage for the learner. It tells the AI persona the background and purpose of the roleplay so the persona understands why the conversation is happening and what the main focus should be.

>[!IMPORTANT]
>
>This field is written for the AI persona, not for the learner. Do not include instructions or guidelines intended for the learner here. Use the **AI Trainer Opener** field for learner-facing context.

## What to include

**Explain the situation:** Describe what type of conversation this is, such as a sales discovery call, a cold call, or an elevator pitch, and who initiated it.

**Describe the AI persona's position:** Explain who the persona is in relation to the learner. For example: a customer evaluating a product, a CFO reviewing a budget proposal, or an employee receiving feedback.

**Use "the learner" consistently:** When referring to the person the persona is speaking with, always write "the learner." Avoid labels such as "the agent," "the seller," or "the rep," which can cause inconsistent persona behavior.

**Keep it concise:** Include only information relevant to the conversation setup. Save persona-specific details such as motivations, habits, and constraints for the **Persona Background Information** field.

**Example**

This is a sales discovery call. The learner has reached out via email to schedule an introductory call with Karen Mitchell, the Medical Affairs Director at a mid-sized hospital network. Karen agreed to a 15-minute call to learn more about the learning platform. She is time-constrained and evaluating whether the platform meets clinical content quality standards before involving her team.

## Persona Background Information

The **Persona Background Information** gives the AI persona a personality. The more detail you enter, the more accurate and consistent the persona's responses will be throughout the simulation.

### What to include

* **Basic details:** The persona's name, age, role, and current situation as it relates to the topic and goal of the roleplay.
* **Motivations and goals:** What the persona cares about, wants to achieve, or change. What are their pain points?
* **Beliefs and attitudes:** How the persona feels about the conversation topic and about the learner's organization.
* **Behaviors and habits:** Tendencies that shape the persona's perspective. For example: frequent clinic visits, cautious decision-making, or an eagerness to adopt new tools.
* **Decision criteria:** What convinces the persona to move forward, and what constraints they are working within, such as time, budget, or internal approval processes.
* **Specific details:** Include any details that should shape specific responses. For example, if the persona requires verification information before sharing data, note that here.
* **Tip:** Specific details help the persona respond in a natural and believable way. Generic backgrounds produce generic behavior.

**Example**

Karen Mitchell is the Medical Affairs Director at Northgate Health, a mid-sized regional hospital network. She is 47 years old and has been in medical affairs for 18 years. Karen is responsible for ensuring all clinical education content meets regulatory and peer-review standards. She is cautious about adopting new technology platforms after a previous vendor failed to meet audit trail requirements. Karen is time-constrained and will end conversations that feel unfocused. She is open to new solutions but needs to see evidence of content accuracy, version control, and a clear implementation path before she will involve her IT or legal teams. Her main pain point is that her current LMS cannot produce audit-ready reports.

## Persona Concerns

Persona Concerns define the specific issues, worries, or questions the persona raises during the conversation. These concerns drive the flow of the roleplay and ensure the learner must respond to realistic challenges.

### What to include

* **List three to five concerns:** Concerns should be specific and actionable, phrased as concerns or questions. Avoid vague concerns such as "worried about cost" — write "concerned that the annual license cost will exceed the department's discretionary budget without CFO approval."
* **Focus each concern on a single topic:** One concern per issue keeps the conversation manageable and ensures each challenge is clearly assessed.
* **Specify when the concern comes up:** Indicate the point in the conversation when the persona raises the concern. For example: a persona worried about data privacy may raise it when asked for verification information. 
* **Define what's good enough to proceed:** Describe what would allow the conversation to move forward. For example: the learner reassures the persona that data is protected, provides a reference, or offers to send documentation.
* **Align with context and background:** Concerns should follow naturally from the conversation context and persona background so they feel organic and consistent.

### Format to use

Write each concern using this structure:

**Concern** → When it comes up → What's good enough to move forward

**Example**

**Concern 1 — Clinical content accuracy:** Comes up when the learner describes the content authoring process. Good enough: the learner explicitly states that content is authored by medical professionals, peer-reviewed, and linked to primary literature or recognized clinical guidelines.
**Concern 2 — Audit trail and compliance:** Comes up when the learner mentions reporting capabilities. Good enough: the learner confirms that the platform produces exportable, time-stamped audit logs that meet regulatory requirements.
**Concern 3 — Implementation burden:** Comes up when the learner proposes next steps. Good enough: the learner outlines a clear, low-effort onboarding path and confirms whether IT or legal involvement is required and at what stage.

Once you have filled in the relevant information, select **Save**. The text so far is saved.

## Review and save your changes

After filling in all three fields, review the complete persona by selecting **Preview** on the **Edit Role-Play** screen. The preview runs a short live session so you can hear how the persona sounds and whether the concerns appear at the right points in the conversation.

When you are satisfied, select **Save** to store your changes, or **Publish** to add the roleplay to the **Content Library**.

>[!NOTE]
>
>Changes to persona settings take effect immediately for any unpublished roleplay. If you edit a roleplay that has already been published and assigned to learners, republish it to apply the updated persona to future sessions.

## Best practices

1. **Write the Conversation Context first:** It sets the frame for everything else — persona background and concerns should follow naturally from it.
2. **Use real-world language in the background:** If your organization has a real customer persona or buyer profile, draw from it directly. The closer to reality, the more useful the practice.
3. **Test concern timing with Preview:** A concern that appears too early or too late disrupts the flow of the conversation. Use Preview to confirm each concern is triggered at the right moment.
4. **Avoid overlapping concerns:** If two concerns cover the same topic, the persona may raise the same objection twice or skip one entirely. Keep each concern distinct.
5. **Revisit after the first learner cohort completes the simulation:** Review session recordings and topic breakdown scores to see which concerns were most frequently missed. Then, sharpen the concern wording to make them more explicit or better timed.
