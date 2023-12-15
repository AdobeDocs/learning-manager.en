---
jcr-language: en_us
title: User gets auto deleted in Learning Manager
description: A user gets deleted from Learning Manager, however, the Administrator never performed any such action.
contentowner: nluke
---


# User gets auto deleted in Learning Manager {#user-gets-auto-deleted-in-learning-manager}

## Issue

A user gets deleted from Learning Manager, however, the Administrator never performed any such action.

## Cause

In Adobe Learning Manager, there is an option that allows you to delete a user if he/she has not logged into the system for a certain amount of time.

## How to change/apply the setting?

### For Internal Learners

1. Log in as an **Administrator**.
1. Under **Configure**, click **Settings** > **General**.
1. In the General settings page, see for the option **Auto-delete Internal Users**.
1. Click **Edit** to enter the number of days in the field, to auto delete a Learner if they have not accessed the system. 

   ![](assets/cp-autodelete-internal.png)

   *Edit the number of days*

>[!NOTE]
>
>   Leave the field blank in case you do not want to delete users automatically.


1. Click **Save** to retain the settings made.

### For External Learners:

1. Log in as an **Administrator**.
1. Under **Manage**, click **Users** > **External**.
1. Click the name of an External User for which the setting needs to be applied.

   This opens the **Edit External Registration Profile** window.

1. Click **Advanced Settings** at the bottom left corner.

   ![](assets/cp-autodelete-external.png)

   *Select the option Advanced Settings*

1. In the **Login Requirement** field, enter the number of days to auto delete a learner if they have not accessed the system. 
1. Click **Save** to retain the settings made.
