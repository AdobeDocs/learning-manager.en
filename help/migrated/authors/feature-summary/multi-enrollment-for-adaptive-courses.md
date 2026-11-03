---
description: Learn how to turn on multi-enrollment for adaptive courses, manage seat limits and waitlists, and understand enrollment rules in learning paths
jcr-language: en_us
title: Multi-enrollment for adaptive courses
exl-id: e2a52964-fe9d-4a71-a020-68201f75f9f0
hide: true
---

# Multi-enrollment for adaptive courses

## Overview

Multi-enrollment lets a learner enroll in more than one instance of the same course at the same time. In Adobe Learning Manager, you can now turn on multi-enrollment for adaptive courses.

## About multi-enrollment in an adaptive course

An adaptive course shows each learner only the modules that match their user groups. With multi-enrollment turned on, a learner can take several instances of that course, such as sessions in different months.

Adaptive courses track waitlists at the module level, not the instance level. A learner can be in progress on some modules and waitlisted on others at the same time. For example, a course has two instances, and each instance has a seat limit of one. The first learner enrolls in both instances and takes both seats. A second learner who enrolls in both instances is waitlisted in both.

## Enable multi-enrollment for an adaptive course

1. Sign in to Adobe Learning Manager as an author.
2. In the left navigation, select **Courses**. Open an adaptive course or create one.
3. Add the modules. For each content module, select **Add rules** to set the user groups that can see it and the user groups for which it is mandatory.
4. Select **Save**. The multi-enrollment option becomes available.
5. Turn on the **Multi-enrollment** toggle.
6. Create the instances you need. For classroom and virtual classroom sessions, set the seat limits.
7. Select **Publish**.

Learners can now enroll in more than one instance of the course.

## Seat limit and waitlist behavior

Adaptive courses enforce seat limits for each classroom or virtual classroom session. A learner is enrolled immediately and is waitlisted only on the sessions that are full. The learner can start all other modules right away.

| Condition                                                                | Result                                                                                                   |
|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| All visible sessions have available seats                                    | The learner is enrolled with full access to all modules.                                                     |
| One or more visible sessions are full                                        | The learner is enrolled and waitlisted on the full sessions only.                                            |
| You add a mandatory session with no seats to a course with enrolled learners | The learner is waitlisted on the new session. Existing progress and access are unaffected.                   |
| A user group change removes a session from the learner's visible modules     | Adobe Learning Manager frees the seat immediately.                                                           |
| A learner switches to another instance                                       | Completed modules stay completed. Seats are used only for visible modules that the learner hasn't completed. |

## Enrollment and completion rules for adaptive learning paths

Authors can now add adaptive courses to adaptive learning paths in Adobe Learning Manager. Enrollment, waitlisting, and completion follow rules that combine the section settings and the course settings that your authors configure.

### How an adaptive learning path evaluates a learner

Adobe Learning Manager evaluates visibility at the section level and at the course level. The section rule decides whether a learner sees a section and the adaptive courses in it. The module rules inside each adaptive course then decide whether the learner is enrolled in the course.

A change to a learner's user groups or to the path structure doesn't enroll the learner in an adaptive learning path on its own. Enrollment in the path still requires an enrollment action or a learning plan.

### Enrollment evaluation rules

When you enroll a learner in an adaptive learning path, Adobe Learning Manager checks the path in this order:

| Order | Check                        | Result                                                                                                                                                 |
|-----------|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1         | Section visibility               | Adobe Learning Manager checks a course for enrollment only if its section is visible to the learner.                                                       |
| 2         | Course eligibility               | If the course has no mandatory module for the learner, the learner isn't enrolled in the course. The course doesn't count toward learning path completion. |
| 3         | Sections with no eligible course | If a section contains only adaptive courses and the learner is eligible for none of them, Adobe Learning Manager skips the section.                        |
| 4         | Learning path enrollment         | If none of the mandatory sections apply to the learner, the learner isn't enrolled in the learning path.                                                   |

If the learner is already enrolled in an instance of the course that belongs to the learning path instance, Adobe Learning Manager uses that enrollment.

After enrollment, the following rules apply:

* A learner who was skipped for a course isn't enrolled in it later, even if user groups or course settings change.

* A user group change or a course change can unenroll a learner from an adaptive course. If no mandatory content remains in the path, the learner is unenrolled from the path.

* A change that opens a section that was skipped can enroll the learner in the adaptive courses in that section.

### Waitlist behavior in adaptive learning paths

Waitlisting works at the session level, not the instance level. This applies to adaptive courses in learning paths as well.

| Scenario                                                                     | Behavior                                                                                                                     |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| No adaptive course in the path has a classroom or virtual classroom module       | No waitlisting applies.                                                                                                          |
| A course has a classroom or virtual classroom module and no instance is selected | The course defaults to **No instance**. The learner can enroll in any instance and is waitlisted only on sessions that are full. |
| An instance is selected before enrollment                                        | The learner is enrolled in that instance and is waitlisted only on sessions that are full.                                       |

To manage waitlisted learners, open the adaptive course and select **Learners** > **Waitlist** tab. For an adaptive course in a Flex learning path, waitlisted learners appear only on the **Waitlist** tab of the course and not under the learning path.

### Refresh completion and rollback behavior

Adobe Learning Manager doesn't revoke completion automatically when user groups or rules change. A completed learner stays completed until you refresh completion.

* Run **Refresh Completion** on the learning path. You can't refresh an adaptive course on its own for learners who take it through the path.

* Each adaptive course recalculates first, based on the learner's current mandatory modules. The learning path then recalculates based on the current mandatory sections and the refreshed course states.

* If the course or path is no longer complete, the learner's status changes to in progress. The original completion remains on the Learner Transcript as a historical record.

* A completion rollback finds the adaptive courses whose modules changed because of a user group change or a republish. It recalculates those courses and then the learning path. The job status shows **Success** when the rollback finishes.

Waitlisting is tracked at the module level. A learner can be waitlisted on a full session in more than one instance. For example, a course has two instances with a seat limit of one each. The first learner enrolls in both instances and takes both seats. A second learner who enrolls in both instances appears on the **Waitlist** tab of each instance.

### Allocate seats to waitlisted learners

When a learner unenrolls, an author increases a seat limit, or a learner switches instances, Adobe Learning Manager clears the waitlist in enrollment-date order. You can also allocate seats manually.

1. Open the adaptive course.
2. Select **Learners** > **Waitlist** tab.
3. Select the checkbox next to each learner you want to allocate seats for.
4. Select **Allocate Seats**.

Adobe Learning Manager clears each selected learner from the waitlist on all waitlisted sessions at once, not only the session you are viewing. The system assumes you have arranged the seat for the learner.
