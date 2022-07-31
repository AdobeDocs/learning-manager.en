---
jcr-language: en_us
title: Unable to achieve a skill after completing a course
contentowner: nluke
---


# **Issue**

A learner, even after completing a course, does not obtain a skill. The skills&nbsp;that are assigned to that course remain as **In Progress** for the learner.

# **Cause**

This issue occurs if the **Credits Required** to achieve this skill is greater than the **Credits Earned** by the learner after completing the course.&nbsp;

# **Solution**

Check the current **Skill Credits **and **Point **required information to achieve the skill. Follow the steps below:

1. For the learner, generate a **Learner Transcript** report.
1. While generating the Learner Transcript, click **Advanced** **Options**,&nbsp;and check the option **Include Skills data and summary sheets**.

   ![](assets/advanced-options.png)

1. Open the downloaded Learner Transcript report.&nbsp;
1. Navigate to the **Skills transcript** sheet. Here, you can view the **Credits Required** and **Credits Earned** by the Learner.&nbsp;

   For example, in the example below, the credits required to achieve the skill for a course is 50. But, the learner has achieved only one credit.

   ![](assets/skill-transcript.png)

1. To check credits assigned to a particular skill, log in as an Admin, and navigate to **Skills** tab, as shown below:

   ![](assets/skill.png)

1. To check the number of credits assigned to a course, log in as an author, and open the course. Click **Settings** > **Course Skills** as shown below:

   ![](assets/course-skills.png)

