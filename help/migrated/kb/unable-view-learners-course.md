---
jcr-language: en_us
title: Unable to view learners in a course
description: The Learners tab of a course does not display any learner enrolled in Adobe Learning Manager. However, if you generate a report, you can view the enrolled learners in the report.
contentowner: saghosh
---


# Unable to view learners in a course

## Issue

You are unable to view learners enrolled in a course.

## Description

The Learners tab of a course does not display any learner enrolled. However, if you generate a report, you can view the enrolled learners in the report.

![](assets/no-learners.png)

*No learner displayed*

## Cause

If a learner is enrolled through a higher Learning Object (Learning Program or Certification), then the learner will be visible on the higher Learning Object's Learner tab. The learner will not be searchable under the course's Learners tab.

**How to view which Higher Learning Object the Learner is enrolled to?**

You can check this information on the Learning Transcript report. To generate a Learner Transcript, follow the steps below:

1. Log in as an Administrator.
1. Click **[!UICONTROL Reports]** > **[!UICONTROL Custom Reports]** > **[!UICONTROL Excel Reports]** > **[!UICONTROL Learner Transcript]**.  

1. Enter the name of the **[!UICONTROL Learner]** and specify the **[!UICONTROL Date]** range.
1. Expand the section **[!UICONTROL Advanced Options]** and select the option **[!UICONTROL Enable module level information]**.  
1. Click **[!UICONTROL Generate]**.

   On the Learner Transcript, you can view which higher Learning Object the learner is enrolled through.
