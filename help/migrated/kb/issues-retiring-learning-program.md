---
jcr-language: en_us
title: Issues with retiring a Learning Program
contentowner: nluke
---


# Issues with retiring a Learning Program {#issues-with-retiring-a-learning-program}

`Learning Manager Learning Programs are renamed to Learning Paths. This change happens immediately after the October 2021 release and the terminology of Learning Path is reflected for all roles.`

# **Issue**

A Learning Program automatically gets retired.

# **Cause**

There are situations where a Learning Program has retired without an Administrator/Author retiring the LP explicitly.

This issue occurs because a Learning Program is a collection of courses. The higher order trainings retire, if any of the courses within it contains a retired instance or the course instance retires.

# **Resolution**

To check the course that contains a retired instance, follow the steps below:

1. Log in as an administrator and launch the relevant Learning Program.  

1. Click **Instances **> **Courses**. The page lists all the courses that are a part of this Learning Program. You will be able to see the course that contains a retired instance.&nbsp;

   ![](assets/retired-instance.png)

1. Once you have figured out the course instance that has retired, click&nbsp;**Courses **> **Open the course**.&nbsp;  

1. Click **Instances. **On the retired instance, click **Edit **and then edit the completion date to a future date to which you want the instance to retire.&nbsp;

   ![](assets/completion-date.png)

1. Once completed, click the drop-down as shown in the image below. Then click **Reopen Instance**.

   ![](assets/re-open-instance.png)

1. Visit the relevant Learning Program. Click **Instances **and execute the previous step to reopen the instance of the Learning Program.

&nbsp; &nbsp; &nbsp;  