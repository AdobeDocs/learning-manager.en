---
jcr-language: en_us
title: Unable to achieve a skill after completing a course
description: A learner, even after completing a course, does not obtain a skill. The skills that are assigned to that course remain as In Progress for the learner.
contentowner: nluke
exl-id: d9c1e2a2-351d-4d6f-b2e6-f9e9278e6523
---
# Unable to achieve a skill after completing a course

## Issue

A learner, even after completing a course, does not obtain a skill. The skills that are assigned to that course remain as **In Progress** for the learner.

## Cause

This issue occurs if the **Credits Required** to achieve this skill is greater than the **Credits Earned** by the learner after completing the course. 

## Solution

Check the current **Skill Credits** and **Point** required information to achieve the skill. Follow the steps below:

1. For the learner, generate a **Learner Transcript** report.
1. While generating the Learner Transcript, click **[!UICONTROL Advanced Options]**, and check the option **[!UICONTROL Include Skills data and summary sheets]**.

   ![](assets/advanced-options.png)

   *Select the option Include Skills data and summary sheets*

1. Open the downloaded Learner Transcript report. 
1. Navigate to the **[!UICONTROL Skills transcript]** sheet. Here, you can view the **[!UICONTROL Credits Required]** and **[!UICONTROL Credits Earned]** by the Learner. 

   For example, in the example below, the credits required to achieve the skill for a course is 50. But, the learner has achieved only one credit.

   ![](assets/skill-transcript.png)

   *View required credits*

1. To check credits assigned to a particular skill, log in as an Admin, and navigate to **Skills** tab, as shown below:

   ![](assets/skill.png)

   *Launch Skills tab*

1. To check the number of credits assigned to a course, log in as an author, and open the course. Click **[!UICONTROL Settings]** > **Course Skills** as shown below:

   ![](assets/course-skills.png)

   *View Course Skills*
