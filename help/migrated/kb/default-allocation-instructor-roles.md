---
jcr-language: en_us
title: Default allocation of instructor roles to user groups in Learning Manager 
contentowner: nluke
---


# Default allocation of instructor roles to user groups in Learning Manager  {#default-allocation-of-instructor-roles-to-user-groups-in-learning-manager}

# Issue

All users who are allocated to a session are assigned the role of an instructor.

# Description

There are scenarios where a session may require multiple instructors, or an Administrator/Author assigns a user group to a session. This results in all users in the user group being assigned the role of an instructor.

# Cause&nbsp;

As roles cannot be branched during bulk assignment of users in a user group, the instructor role gets assigned to all users.

# Solution

Create custom user groups to filter the user roles assigned to a session. To remove the assigned instructor roles in a user group, perform the following steps:

1. Log in as an Administrator. In the left panel, click **Email Templates**.  

1. To avoid email triggers for the changes to be made, click **Disable All**.

   ![](assets/instructor-disable-all.png)

1. Navigate to **Users **> **User group**. Click **Add**.&nbsp;

   ![](assets/instructor-usergroups.png)

1. Create a custom User group in the Add User Group window as follows:&nbsp;

   * Enter a name for the custom group in the **Name **field.&nbsp;  
   
   * Under **Include Learners** field, add the User group for which you want to filter the instructors .  
   
   * Under **Exclude Learners** field, add the users for whom you want to retain the instructor role.

   ![](assets/instructor-add-ug.png)

   The above steps create a list of users to be added in the inclusion set and remove specific users (instructors) mentioned in the exclusion set.&nbsp;

1. Click to **Save **the changes made.&nbsp;&nbsp;  

1. Search for the created custom user group by going to **Users **> **Internal**.&nbsp;

   ![](assets/instructor-custom-ug.png)

1. Click the check box to select all users in the group.&nbsp;

   ![](assets/instructor-bulk-ug.png)

1. Click **Actions **> **Remove Role** > **Remove Instructor**.&nbsp;

Ensure that any email triggers that were disabled in step 2 are re-enabled once completed.&nbsp;  
