---
jcr-language: en_us
title: Module is marked incomplete on course completion in Adobe Learning Manager
description: Even after a learner completes a course in Adobe Learning Manager, the module is marked as incomplete.
contentowner: nluke
---


# Module is marked incomplete on course completion in Adobe Captivate Prime

## Issue

Even after a learner completes a course in Adobe Captivate Prime, the module is marked as incomplete.

## Cause

SCORM 2004 defines the success and completion criteria and sends the statements for both separately.

For example, let there be a content set with a **Completion Criteria** of 100% slide views and **Success Criteria** set as "Quiz is Passed".

A learner, completes the course, but fails the quiz. In this case, the progress is 100%, but the module is marked as incomplete as the learner fails to meet the **Success Criteria**.

## Solution

The issue is related to the reporting **Preferences** set for the project. The author must verify the criteria set for the completion and success of the course.

If there are any changes required, the author can do so using a content authoring tool, such as Adobe Captivate. The author can then update the module accordingly.

![](assets/scorm.png)
