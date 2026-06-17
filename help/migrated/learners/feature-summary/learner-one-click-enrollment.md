---
description: One click enrollment allows learners to click on any deep link to a module shared by admins and access the content immediately without going through multiple steps to click enroll and then start the course. It saves time and improves the course access.
jcr-language: en_us
title: Use one-click enrollment in Adobe Learning Manager
contentowner: mmanuel
---

# One-click enrollment in Adobe Learning Manager

Receive the deep link from your administrator via email, chat, or another messaging platform to enroll in a training module or course. Select the link to enroll instantly and launch the module, with no additional steps.

## Enroll a learner and redirect the learner to the course

Note the following scenarios and their corresponding actions. As a learner, if you click the deep link which was sent to you, one of the following will happen depending on the scenario you're in:

| SN | Scenario | Action |
| --- | --- | --- |
| 1 | Single-module course and unordered | You'll be auto-enrolled and the player opens. You have to press Play to play the video. |
| 2 | Multi-module course and unordered | You'll be auto-enrolled and land on the particular  module to which the deep link is linked. You have to press Play to play the video. |
| 3 | Multi-module course and ordered | You'll land on the Overview page with a message that says that you have to complete the preceding courses before you start the current one in case you have not finished the preceding ones. In this case, you'll be auto-enrolled and land on the first module of the course. |
| 4 | Course has prerequisites | If prerequisites are complete, you can launch the module in player. Press Play to play the video. If they are not complete, the following message appears "Cannot skip pre-requisite Courses. Please complete all the pre-requisite courses before starting this course. |
| 5 | Course with waitlist | You'll be enrolled. You'll land in the course overview page, and you'll be added to the waitlist. You'll also see a message that the course is waitlisted. |
| 6 | If you're already enrolled in the course for which deep link is generated. | You'll land on the module and the player will launch. Press Play to play the video. |

## Authentication status and deep link behavior

In addition to the above scenarios, there are two more user behavior that are related to the authentication (logged-in and logged-out) status.

* If you click a deep link and if you are not logged in to Adobe Learning Manager, you'll be redirected to the login page. Log in and the deep link will redirect you to the particular module.

* If you click a deep link and if you are logged in to Adobe Learning Manager, you'll be redirected to the module directly.

## Immersive support for mobile and web 

The following scenarios are applicable to both mobile and web versions of Adobe Learning Manager.

* If you do not have the desktop version of Adobe Learning Manager and you receive a deep link, selecting the link will redirect you to the login page of Adobe Learning Manager in your browser if you are not logged in to the web or mobile version.
* If you do not have the desktop version of Adobe Learning Manager and you receive a deep link, selecting the link will redirect you directly to the module of Adobe Learning Manager in your browser if you are already logged in to the web or mobile version.

## Browser-restricted auto-play

When you click a deep link, it redirects you to a module or a login page if you are not logged in. If the module is a video, the player will not play the video automatically. In all cases, the browser prevents the player from playing the video automatically. You have to press Play manually to play the video. 
