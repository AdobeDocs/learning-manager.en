---
jcr-language: en_us
title: Unable to view file submissions in Adobe Learning Manager
description: Instructors are unable to view files that learners have uploaded in the Submission Activity Module.
contentowner: nluke
---


# Unable to view file submissions in Adobe Learning Manager

## Issue

An instructor is unable to view the file submissions that a learner has uploaded.

## Description

Instructors are unable to view files that learners have uploaded in the **Submission Activity Module**.

For example, a learner had enrolled for an instance named **Test instance** of a course, as shown below:

![](assets/test-instance.png)

*View instance*

The learner then opens the course and uploads a file in the Activity module.

When the instructor tries to approve the submission, the instructor is unable to do so.

![](assets/activity.png)

*Upload a file in the Activity module*

## Cause

If there is no instructor in the course instance in which the learner is enrolled, the issue appears.

## Resolution

To check if an instructor is added to the course instance, perform the steps below:

1. Navigate to the course settings.
1. In the **Manage** section, click **[!UICONTROL Instances].**
1. In the instance where the learner is enrolled, click **[!UICONTROL Sessions]**.

   ![](assets/check-instructor.png)

   *Select Sessions in the instance*

   There is no instructor assigned to this session.

1. Click **[!UICONTROL Edit]**. Add the instructor who approves the file submission.

   ![](assets/assign-instructor.png)

   *Add the instructor*
1. Save the changes.

