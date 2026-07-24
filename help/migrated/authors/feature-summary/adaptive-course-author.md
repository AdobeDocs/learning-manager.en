---
description: As an author, learn how to create adaptive courses for your learners.
jcr-language: en_us
title: Adaptive courses for authors
contentowner: mmanuel
---

# Adaptive courses for authors 

## Create and configure an adaptive course

Build a course with per-module visibility and completion rules so different learners see and complete different content based on their user groups.

>[!NOTE]
>
>The adaptive course type is available only if **Visibility and completion rules** has been enabled for your account. If you don't see the option to create an adaptive course, ask your administrator to enable adaptive learning. 

### Create an adaptive course

1. Sign in to Adobe Learning Manager as an author.

    ![](assets/ac-author-001.png)

2. In the left navigation, select **Courses**. Then select **Add**.
3. Enter the name of the course, description, and other details.
4. Select the **Content visibility and completion rules** toggle.

    ![](assets/ac-author-002.png)

5. Select **Yes** on the confirmation dialog.

    ![](assets/ac-author-003.png)

    **Add modules to an adaptive course**

    Add the required modules. Add content modules by uploading content, selecting from the content library, or adding classroom or virtual classroom sessions.

    **Module types that support adaptive rules (content modules):**

    * Self-paced e-learning
    * Classroom sessions
    * Virtual classroom sessions
    * Activity modules

    **Module types that do NOT support adaptive rules:**

    * **Pre-work modules:** Shown to all learners before the core content begins. No visibility or completion rules can be set.
    * **Test-out modules:** Available to all learners. Completing a test-out completes the entire course regardless of content module status. No visibility or completion rules can be set.
    * **Job aids:** Visible to all enrolled learners at all times.

6. Select **Add**.

### Configure visibility and completion rules for each module

After adding a content module, configure its adaptive rules:

1. Select the module you want to configure.
2. In the module settings, locate the **Visibility and completion rules** section.

    ![](assets/ac-author-004.png)

3. Select **Add rules** to add the user groups that can see this module.

    ![](assets/ac-author-005.png)
    
    ![](assets/ac-author-006.png)

    Learners in these groups see the module in the course, but don't need to complete it unless they're also in Mandatory.

4. Select **Save**.
5. Repeat for every content module in the course.

**Key rules:**

* If any group makes a module mandatory, it's mandatory for that learner.
* You must configure at least one module as **Mandatory** for least one user group before you can publish. The system blocks publication until this condition is met.

### Course in a draft state

When a course is in the draft state, it represents the phase where the entire adaptive structure can be fully designed, configured, and refined before being locked for learners. At this stage, authors can define whether the course should function as an adaptive course or a regular course, and this decision remains reversible until the course is published. This makes the draft phase critical, as it is the only point where the core adaptive nature of the course can be established or changed.

![](assets/ac-author-007.png)

In draft, authors have complete control over the course structure. They can add, remove, and reorder modules freely to shape the intended learning flow. At the same time, they can configure adaptive behavior at a granular level by defining visibility rules for each module. These rules determine which user groups can access specific modules, enabling the course to later deliver personalized learning experiences. Alongside visibility, authors can also define completion rules, marking modules as mandatory or optional for different user groups. The system requires that at least one module be mandatory to ensure meaningful completion criteria.

The draft state also allows unrestricted editing of adaptive logic. Authors can iteratively add, modify, or remove rules without any system constraints, making it possible to experiment with different configurations before finalizing the course. In addition to adaptive setup, all standard course elements remain editable, including course metadata such as title and description, as well as the underlying learning content, including SCORM modules or other assets.

It is important to understand that adaptive configuration in draft applies only to core course modules. Other components, such as pre-work or test-out content, do not support adaptive rules and remain unaffected by visibility or completion configurations.

Finally, the draft state serves as the last opportunity to validate the course setup before publishing. Once the course is published, the adaptive configuration becomes permanent and cannot be reverted.

### Preview as Learner

Selecting **Preview as Learner** shows all modules in the course regardless of user group rules. This gives authors and administrators a complete view of the course structure. Learners in production see only the modules their user groups make visible.

### Publish an adaptive course

Publishing an adaptive course follows the same workflow as publishing a regular course.

After configuring all modules and their rules, select **Publish**.

Once published, the course is available for enrollment. Learners see only the modules configured for their user groups when they open the course.

>[!IMPORTANT]
>
>Once published, you cannot switch the course from Adaptive to Regular or vice versa. Verify your configuration before publishing.


### Update a published adaptive course

You can update a published adaptive course at any time. Changes take effect for enrolled learners in near-real time.

Note that you can no longer change the visibility settings in the adaptive course. You cannot make the course a non\-adaptive one. 

![](assets/ac-author-008.png)

>[!NOTE]
>
>A learner cannot be waitlisted in switching instance, enrollment will be blocked.

### Add or modify modules

1. Open the published course.
2. Select **Edit**.
3. Add, edit, or remove modules and adjust their visibility and completion rules.
4. Republish the course.

**Impact:**

| Change | Effect on enrolled in-progress learners |
|---|---|
| New mandatory module added (visible to a learner's user group) | A module is added to their completion requirement. If the module is a classroom or virtual classroom session with no remaining seats, the learner is waitlisted on that module. |
| Module removed or made hidden for a learner's user group | Module removed from their completion requirement. If this was the last mandatory module, the course auto-completes for the learner. |
| Module changed from mandatory to optional for a learner's user group | Module remains visible; learner no longer needs to complete it for course completion. |
| New mandatory module added (learner has already completed the course) | Module becomes visible to the learner but they do not automatically get a seat or access it. The new module becomes accessible only when a refresh completion is triggered. |

### Instance switching behavior

A learner who switches instances of an adaptive course carries forward their progress:

* Modules they have already completed remain completed in the new instance.
* Seats are consumed only for non-completed visible modules in the new instance.
* They cannot be waitlisted when no seats are available for an instance. Enrollment will be blocked.

## Manage seat limits and waitlists in adaptive courses

Adaptive courses in Adobe Learning Manager enforce seat limits at the individual classroom or virtual classroom session level. Unlike regular courses, where a full session blocks the entire enrollment, an adaptive course enrolls the learner immediately and waitlists them only on the specific sessions where no seats are available. The learner can access all other modules without interruption.

### How seat limits work in adaptive courses

When a learner enrolls in an adaptive course that includes classroom or virtual classroom modules, the system checks seat availability only for sessions that are visible to the learner based on their user groups.

* If all visible classroom or virtual classroom sessions have available seats, the learner is enrolled and has full access immediately.
* If one or more visible sessions have no available seats, the learner is enrolled and immediately waitlisted on those specific sessions only. They can start and progress through all other modules right away.

The following table describes all seat and waitlist scenarios for adaptive courses.

| Condition at enrollment | Result |
|---|---|
| All visible CR/VC sessions have available seats | Enrolled with full access to all modules |
| One or more visible CR/VC sessions are full | Enrolled; waitlisted on full sessions only; all other modules accessible immediately |
| Learner already enrolled; author adds new mandatory CR/VC session with no seats | Learner waitlisted on the new session; existing progress and access unaffected |
| Learner unenrolls | All held seats freed immediately; next waitlisted learners cleared in enrollment-date order |
| User group change removes a session from the learner's visible set | Seat freed immediately |
| Learner completes the course; new mandatory CR/VC session becomes visible | Module visible but no seat automatically assigned. Learner must trigger refresh completion to access the session. |
| Admin or instructor allocates seats | All waitlisted CR/VC sessions for that learner are cleared simultaneously |

### View the waitlist

1. Open the adaptive course in the admin view.
2. Select **Learners**.
3. Select the **Waitlist** tab.

The Waitlist tab lists learners who are waitlisted on one or more modules. For adaptive courses, the report is at the course-instance-module level rather than the course-instance level, because a learner can be in progress on some modules while waitlisted on others simultaneously.

### Clear the waitlist and allocate seats

When a seat becomes available, due to a learner unenrolling, a seat limit increase, or manual allocation, waitlisted learners are cleared in enrollment-date order (earliest enrollment date first).

To manually allocate seats for one or more learners:

1. Open the adaptive course.
2. Select **Learners** > **Waitlist** tab.
3. Select the checkbox next to the learner or learners you want to allocate seats for.
4. Select **Allocate Seats**.

Selecting Allocate Seats clears the selected learner from the waitlist on all waitlisted sessions simultaneously, not just the session you are currently viewing. The system assumes the seat has been physically or virtually arranged for the learner.

**Waitlist clearance triggers:**

Waitlist is automatically processed when any of the following occur:

* A learner unenrolls from the course (freeing their seat on all held sessions)
* The seat limit for a session is increased
* A learner switches instances
* An administrator or instructor allocates seats

>[!NOTE]
>
>When you create a new instance of an adaptive course, the **Notify waitlisted learners** option is not available. This is expected behavior and differs from regular courses.

In a regular course, the waitlist is tracked at the instance level, so the system can prompt you to notify waiting learners when a new instance opens up. In an adaptive course, waitlists are tracked at the individual classroom or virtual classroom **session** level, not the instance level. There is no instance-level waitlist to notify when a new instance is created, so the prompt does not appear, and no automatic notifications are sent.

## Trigger refresh completion for an adaptive course

Refresh completion in Adobe Learning Manager allows a learner's adaptive course completion to be re-evaluated when their learning requirements change. This is relevant when a learner's user group changes, when an author updates module rules, or when a learner wants to retake an adaptive course under their current profile.

### What refresh completion does

In an adaptive course, a learner's set of mandatory modules is determined by their user groups at the time they complete the course. If their user groups later change, or if the author adds new mandatory modules, the learner may need to complete additional content to meet the requirements of their new profile.

Refresh completion does two things:

1. Rolls back the learner's existing course completion if they now have new mandatory modules that are incomplete.
2. Creates a new record in the Learner Transcript representing the updated completion requirement.

![](assets/ac-author-009.png)

The original completion record is preserved on the Learner Transcript as a historical entry. Previously completed modules remain completed. The learner does not need to repeat them unless they are specifically newly mandatory modules that were not visible or not completed before.

### When refresh completion applies

**Scenario 1: User group change adds new mandatory modules**

A learner completes an adaptive course. Their user group is later changed, and the new user group makes previously hidden or optional modules mandatory.

* The existing completion entry remains on the Learner Transcript.
* If the learner has new uncompleted mandatory modules, a new Learner Transcript row is created and the course shows as in-progress.
* The learner must complete the new mandatory modules to achieve a new completion.

**Scenario 2: User group change results in no new mandatory modules**

A learner completes an adaptive course. Their user group changes, but the new user group's requirements are already met by their existing completions.

* The course remains in a completed state.
* No new Learner Transcript row is created.
* No action is required from the learner.

**Scenario 3: Learner-initiated retake**

A learner who has already completed an adaptive course can choose to retake it to complete it under their current user group profile. This is useful when a learner's role has changed since their original completion.

1. The learner opens the completed adaptive course.
2. The learner selects the option to retake or restart the course.
3. The course is re-evaluated using their current user groups to determine the new mandatory module set.
4. A new Learner Transcript row is created.

**Scenario 4: Test-out module behavior**

If a learner completed a test-out module before refresh completion was triggered, the test-out completion is still valid after refresh. Once the system evaluates course completion (triggered by any module completion or learner action), the course will auto-complete again because the test-out is already done, unless the course has additional mandatory content modules that are now required and incomplete.

>[!NOTE]
>
>If a new classroom or virtual classroom session is added to the adaptive course after a learner has completed it via test-out, and a refresh completion is subsequently triggered, the learner may not automatically appear in the **Attendance & Scoring** tab or **Waitlist** for the new session. This occurs because the test-out completion keeps the course in a completed state, and seat assignment logic is not re-triggered. If you need to track a test-out learner's attendance for a newly added session, allocate their seat manually from the **Waitlist** tab. Note that test-out modules are not the recommended approach for adaptive courses.

**Scenario 5: Administrator-triggered refresh**

An administrator can trigger a refresh completion on behalf of a learner if the learner's profile has changed and the administrator determines that the existing completion record no longer reflects current requirements.

>[!CAUTION]
>
>If the adaptive course is part of a recurring certification, refresh completion applies only to the learner's enrollment in the root certification cycle. Subsequent recurred cycles contain a separate instance of the adaptive course that is not affected by the refresh. Learners enrolled in a recurring cycle do not see module updates, nor do their completions roll back. If your organization uses adaptive courses in recurring certifications, communicate this limitation to administrators before triggering refresh completions

1. Open the learner's profile or the course's Learner tab in the admin view.
2. Locate the learner's enrollment.
3. Select **Refresh Visibility and Completion**.

ALM re-evaluates mandatory modules based on the learner's current user groups and rolls back the completion if new mandatory modules exist.
