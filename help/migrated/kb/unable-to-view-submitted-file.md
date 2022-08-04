---
jcr-language: en_us
title: Unable to view file submissions in Adobe Learning Manager
contentowner: nluke
---


# Unable to view file submissions in Adobe Learning Manager {#unable-to-view-file-submissions-in-adobe-learning-manager}

# **Issue**

An instructor is unable to view the file submissions that a learner has uploaded.

# **Description**

Instructors are unable to view files that learners have uploaded in the **Submission Activity Module**.

For example, a learner had enrolled for an instance named **Test instance**&nbsp;of a course, as shown below:

![](assets/test-instance.png)

The learner then opens the course and uploads a file in the Activity module.

When the instructor tries to approve the submission, the instructor is unable to do so.

![](assets/activity.png) 

# **Cause**

`If there is no instructor in the course instance in which the learner is enrolled, the issue appears.`

# Resolution

To check if an instructor is added to the course instance, perform the steps below:

1. Navigate to the course settings.
1. In the **Manage **section, click **Instances.**
1. In the instance** **where the learner is enrolled, click **Sessions**.

   ![](assets/check-instructor.png)

   There is no instructor assigned to this session.

1. Click **Edit. **Add the instructor**&nbsp;**who approves the file submission.

   ![](assets/assign-instructor.png)

1. Save the changes.
