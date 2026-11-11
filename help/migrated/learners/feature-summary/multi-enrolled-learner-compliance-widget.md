---
description: Learn how the Learner Compliance widget lists every enrolled instance of a multi-enrolled course that has a deadline, and how the API supports it
jcr-language: en_us
title: Multi-enrolled courses to appear in Learner Compliance widget
exl-id: 6484c815-ecae-4a75-ba10-ef42e4ff50a6
---

# Multi-enrolled courses in Learner Compliance widget

In Adobe Learning Manager, a learner can be enrolled in more than one instance of the same course. The Learner Compliance widget now lists every enrolled instance that has a deadline, so learners see each due date instead of only the primary instance.

## What changes for multi-enrolled courses

Before this change, the Compliance widget showed only the primary instance of a multi-enrolled course. A learner who was enrolled in several instances could not see the deadlines for the others in the widget.

Now, the Compliance widget shows every instance that meets all of these conditions:

* The learner is enrolled in the instance.
* The instance has a deadline.
* The learner has not completed the instance.

Each entry displays the instance name, so learners can tell instances of the same course apart. When a learner selects an entry, Adobe Learning Manager opens that instance directly.

For example, a learner completes an initial training course. An admin later enrolls the learner in the September, October, and November editions of the same course, each with a deadline. The Compliance widget lists all three editions.

The widget counts each instance separately in each compliance category: **Overdue**, **Upcoming deadline within next 30 days**, and **On-track**.

## Instances that appear in the Compliance widget

The following table describes how the widget treats each enrollment situation.

| Enrollment situation                         | Appears in the widget         | Notes                             |
|--------------------------------------------------|-----------------------------------|---------------------------------------|
| Enrolled, instance has a deadline, not completed | Yes                               | Shown with the instance name          |
| Enrolled, instance has no deadline               | No                                | Only instances with a deadline appear |
| Instance completed                               | No                                | A completed instance is not listed    |
| Completed in all enrolled instances              | No                                | The course no longer appears          |
| One instance with a deadline and one without     | Only the instance with a deadline |                                       |
| Only one enrolled instance                       | Yes                               | The widget shows that instance        |

See [API support for multi-enrolled instances in the Learner app](/help/migrated/api-changes-dec-2026.md#multi-enrolled-compliance-widget) for API information.
