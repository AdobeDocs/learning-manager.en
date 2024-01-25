---
jcr-language: en_us
title: Default allocation of instructor roles to user groups in Learning Manager 
description: Default allocation of instructor roles to user groups in Learning Manager 
contentowner: nluke
preview: true
---


# Default allocation of instructor roles to user groups in Learning Manager 

## Issue

All users who are allocated to a session are assigned the role of an instructor.

## Description

There are scenarios where a session may require multiple instructors, or an Administrator/Author assigns a user group to a session. This results in all users in the user group being assigned the role of an instructor.

## Cause 

As roles cannot be branched during bulk assignment of users in a user group, the instructor role gets assigned to all users.

## Solution

Create custom user groups to filter the user roles assigned to a session. To remove the assigned instructor roles in a user group, perform the following steps:

1. Log in as an Administrator. In the left panel, click **[!UICONTROL Email Templates]**.  
1. To avoid email triggers for the changes to be made, click **[!UICONTROL Disable All]**.

   ![](assets/instructor-disable-all.png)

1. Navigate to **Users** > **User group**. Click **[!UICONTROL Add]**. 

   ![](assets/instructor-usergroups.png)

1. Create a custom User group in the Add User Group window as follows: 

   * Enter a name for the custom group in the **[!UICONTROL Name]** field.
   * Under **[!UICONTROL Include Learners]** field, add the User group for which you want to filter the instructors.  
   * Under **[!UICONTROL Exclude Learners]** field, add the users for whom you want to retain the instructor role.

   ![](assets/instructor-add-ug.png)

   The above steps create a list of users to be added in the inclusion set and remove specific users (instructors) mentioned in the exclusion set. 

1. Click **[!UICONTROL Save]** the changes made.    
1. Search for the created custom user group by going to **[!UICONTROL Users]** > **[!UICONTROL Internal]**. 

   ![](assets/instructor-custom-ug.png)

1. Click the check box to select all users in the group. 

   ![](assets/instructor-bulk-ug.png)

1. Click **[!UICONTROL Actions]** > **[!UICONTROL Remove Role]** > **[!UICONTROL Remove Instructor]**. 

Ensure that any email triggers that were disabled in step 2 are re-enabled once completed.   
