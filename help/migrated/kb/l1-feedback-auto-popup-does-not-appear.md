---
jcr-language: en_us
title: L1 feedback auto popup does not appear
description: How to resolve 'L1 feedback auto popup does not appear' error
contentowner: saghosh
---


# L1 feedback auto popup does not appear

## Issue

The L1 feedback auto-popup does not appear for a learner after completing the course.

## Cause

Sometimes it can happen that a Learner may not receive the L1 feedback after completing a particular course or may receive a message as shown below:

![](assets/l1-feedback.png)

*Unable to receive L1 feedback*

This can happen due to the following reasons:

1. Feedback is not set to appear after course completion.
1. Reminders are turned off.
1. A reminder is scheduled to appear after a certain amount of time.

## Resolution

1. Ensure that the option "Show questionnaire immediately after Course completion" is enabled in **Course** > **Instances** > **L1 Feedback**.
   <!--![](assets/l1-feedback.png)-->
1. As Admin, navigate to **Settings > Feedback**. Check when is the reminder scheduled. In case it is scheduled for **After course** completion, change the option to **On course** completion.
1. Enable the following email templates: **Email Templates > Reminders & Updates > Request Learner's Feedback for Course**. In case the option disabled, enable it, and then test.  
1. If the above steps do not work, delete the reminder present in **Admin > Settings > Feedback**. Create one for 'On Course Completion' and set the recurrence according to the requirement.
