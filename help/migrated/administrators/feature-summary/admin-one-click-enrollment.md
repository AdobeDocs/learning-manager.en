---
description: One click enrollment allows learners to click on any deep link to a module shared by admins and access the content immediately without going through multiple steps to click enroll and then start the course. It saves time and improves the course access.
jcr-language: en_us
title: Set up one-click enrollment in Adobe Learning Manager
contentowner: mmanuel
---

# Set up one-click enrollment in Adobe Learning Manager

## How one-click enrollment works

One-click enrollment relies on two Adobe Learning Manager (ALM) capabilities working together:
Deep links provide a direct URL to a specific course or learning object within ALM. You can embed these links (which are direct URLs to modules) in emails, intranet portals, or third-party applications. If a learner is not already logged in when they click the link, ALM prompts them to authenticate and then takes them directly to the course. 

It is generally valuable when learners are in the midst of work and are using Slack or Teams or when they need to have a quick two-minute refresher training before they travel or attend a meeting or a sales call. They can access the content immediately and get trained.
The enrollment-related services automatically enrolls a learner into a course before the deep link launches the course player. This removes the manual enrollment step that would otherwise interrupt the learner's experience.

When a learner selects a one-click enrollment link, ALM enrolls them via the API in the background, then redirects them to the course using the deep link. The course player opens immediately.

>[!NOTE]
>
>Enrollment occurs at course level only, not at higher-order learning objects (learning paths or certifications).

## Generate a deep link for a module

1. Log in to Adobe Learning Manager as an administrator.
2. Select **Courses** in the left navigation pane.
    ![](assets/one-click-enroll1.png) 
3. Select a course 
4. Select **Instances**.
    ![](assets/one-click-enroll2.png) 
5. Select the **Module** section the instance whose modules' deep links you want to copy. The module details are displayed in the expanded section at the bottom of the instance.
    ![](assets/one-click-enroll3.png)
6. Navigate to the module whose link you want to copy.
    ![](assets/one-click-enroll4.png)
7. Select **Copy link**. The deep link is now copied. This deep link is a link to open the particular module in a course.

You can now use this deep link to send it to a learner. 
