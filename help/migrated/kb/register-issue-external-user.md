---
jcr-language: en_us
title: Unable to register as an External User
description: External learners are unable to register to a profile in Adobe Learning Manager.
contentowner: nluke
exl-id: b1a9ecb6-75a8-44f7-b169-f77d7a4f6c2c
---
# Unable to register as an External User

## Issue

External learners are unable to register to a profile.

## Error

Email id is already registered. Please use a different email.

![](assets/cp-register-profile.png)

*Error message of an already registered email*

## Description

There are scenarios where a user is unable to register to an External Profile. The user receives the above error while signing up.

## Cause

This issue occurs under one of the below scenarios:

* The user is already registered to another external profile.
* The user is already an internal learner.
* The user is in a deleted state.

## Resolution:

**Scenario 1:** The user is already registered to another External Profile.

1. Log in as an Administrator.
1. Under **Manage**, click **[!UICONTROL Users]** > **[!UICONTROL External]**.
1. Open the Profile which the user is already a part of by clicking the Seats Used

   ![](assets/cp-seats-used.png)

   *Open profile of user*

1. Select the User, click **[!UICONTROL Actions]** > **[!UICONTROL Change Profile]**.

   ![](assets/cp-change-profile.png)

   *Change profile of user*

   This opens a window to select a new profile as below.

   ![](assets/cp-select-profiles.png)

   *Select user profile*

1. Once selected, click **[!UICONTROL Change]**.

**Scenario 2:** The user is present as an Internal Learner.

1. Log in as an Administrator.
1. Under **Manage**, click **[!UICONTROL Users]** > **[!UICONTROL Internal]**.
1. Click to open a Learner profile and click the Edit icon.

   ![](assets/cp-internal-learner.png)

   *Open an internal learber profile*

1. Change the email address of the Learner or add *_old* to the existing email address. This will free up the email address.

   For example, If the email address of the Learner is *<abc@adobe.com>,* change it to *<abc_old@adobe.com>*

1. Click **Save** to retain the changes made.

**Scenario 3**: The user is in a deleted state.

1. Log in as an Administrator.
1. Under **Manage**, click **[!UICONTROL Users]** > **[!UICONTROL User Cleanup]**.
1. Select the Learner and click the Edit icon.

   ![](assets/cp-deleted-learner.png)

   *Edit user email address*

1. Change the email address of the Learner or add *_old* to the existing email address. This will free up the email address.

   For example, If the email address of the Learner is **<abc@adobe.com>**, change it to **<abc_old@adobe.com>**.
