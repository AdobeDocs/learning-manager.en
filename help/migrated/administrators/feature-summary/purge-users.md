---
description: Know more about purging user data in Learning Manager.
jcr-language: en_us
title: Purge users
contentowner: dvenkate
exl-id: 4449146c-6247-44fb-b695-a12023c31dc6
---
# Purge users

Know more about purging user data in Learning Manager.

## Overview {#overview}

Use the purge user feature to remove personal identifiable information and learning records of the user from Learning Manager. Note that Delete and Purge User are two different features. While a deleted user can be restored, all user data and learning records associated with a purged user cannot be restored.

Purge user action can have the following results:

* If a user is purged, the links in import logs does not work to avoid the download of old CSVs and bringing back the user data again into the system.
* If an Author is purged, his name is replaced by the name of the administrator who purged that user.
* If Instructors are purged, they are removed from sessions. Administrator has to replace/add instructors for such sessions.
* Purging a user in Learning Manager does not remove the user in any external applications (third-party systems or other applications written by you). Contact external application owners to get the users removed from such applications.
* If a purged user is referred in the configuration settings of a connector, the connector is disabled. The connector needs to be reconfigured by the administrator to resume.

<!---### Manage users

In this training, you will learn how to assign and remove roles, send a welcome email, and delete and purge users. 

[![button](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&sdid=4X3B8VJ2&mv=display&mv2=display#/course/7555586)

If you're unable to launch the training, write to <almacademy@adobe.com>.-->

## How to purge users

To purge users, follow these steps:

1. As an Administrator, select **[!UICONTROL Users]** from the left pane. The **[!UICONTROL Internal Users]** page opens.
1. Delete the users you want to purge. To delete, select one or more users using the checkbox. Open the **[!UICONTROL Action]** drop-down and select **[!UICONTROL Delete User.]**
1. In the left pane, select **[!UICONTROL User Cleanup]**. The **[!UICONTROL User Cleanup]** page appears with the list of deleted users. Use the radio buttons to select the user to purge. You can only purge one user at a time.

   ![](assets/purge-1.png)

   *Select a user to purge*

1. Open the **[!UICONTROL Actions]** drop-down menu and select **[!UICONTROL Purge User]**. 

   ![](assets/purge-2.png)

   *Select the Purge User option*

1. A dialogue box appears seeking confirmation. Once purged, all user data and learning records associated with the selected user is deleted permanently. Once purged the action cannot be undone. To confirm, click **[!UICONTROL Purge]**.

   ![](assets/purge-3.png)

   *Confirmation message after purging a user*

1. Once you confirm and click Purge, the purge request is accepted. You receive a notification once the action is complete. A purge request ID is also provided. You can provide this ID to the CSM to track the request.

>[!NOTE]
>
>Once the deleted user is added back to the system, the previous roles (e.g. Administrator, Manager, Author, Instructor etc.) will not be retained.They will be added with the learner role. 

## Bulk purge of users

You can select the first 50 users and purge the users in one shot. This allows administrators to select 50 users at once and purge them together. This helps administrators when they wish to purge users in bulk. It's always a best practice to check the users who are selected for purging. This is important to ensure only the correct set of users are getting purged. 

![](assets/bulk-purge-users.png) 

*Purge users in bulk*

## Filter deleted users before purging

Adobe Learning Manager allows administrators to permanently remove users who have already been deleted from the platform. This process, called purging, helps organizations maintain a clean learner database, comply with data retention policies, and prevent any unauthorized access to user data.
This is particularly useful for maintaining data hygiene and ensuring that old, unused user data is removed from the system. 
Purging users is essential for complying with data privacy guidelines or maintaining a sanitized datastore by removing redundant records.

### Filter deleted users by month

You can filter deleted users by selecting a specific month and then permanently delete them.

To filter the deleted users using deletion month:

1. Select **[!UICONTROL Users]** in the administrator home page and then select **[!UICONTROL User Cleanup]**.
2. Select the **[!UICONTROL Select Deletion Month]** date picker and select the date.
 
   ![](assets/deletion-date.png)
   _Select the month when the users were deleted_

   The list of users deleted in the selected month appears.
   
   ![](assets/list-of-user-deleted.png)
   _List of deleted users displayed for selected month_

### Sort deleted users by month

You can sort the filtered users by their **[!UICONTROL Unique User ID]** and **[!UICONTROL Date deleted]**.

1. In the list of deleted users, sort the users according to their user IDs or deletion date.
   
   ![](assets/sort-by-date.png)
   _User list filtered by Unique User ID_

2. Select one or multiple users.
3. Select **[!UICONTROL Actions]** and then select **[!UICONTROL Purge User]**.
4. Select Purge on the confirmation message to delete the user records permanently from Adobe Learning Manager.

   ![](assets/select-purge.png)
   _Final confirmation before permanently purging users_

>[!NOTE]
>
>Purging users permanently removes their data. Double-check your selection before proceeding.

+++Read about the results of Purge User action

<table>
 <tbody>
  <tr>
   <th><strong>Purge using Learning Manager UI- Enterprise</strong></th>
   <th> </th>
  </tr>
  <tr>
   <td>Delete selected user from the requesting enterprise account.<br></td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Delete all users from all Trial accounts whose email, adobe_id matches selected users email.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Delete all users from all Trial accounts whose email, adobe_id matches selected users email and he/she is the creator of the trial account.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Delete User's email from all the other fields of the requesting Enterprise account and All Trial Accounts.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Notify initiator of deletion confirmation.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td><strong>Purge using Learning Manager UI- Non-Enterprise</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Delete Selected User from the requesting Trial Account.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Delete all users from all Trial accounts whose email, adobe_id matches selected users email.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Delete all users from all Trial accounts whose email, adobe_id matches selected users email and he/she is the creator of the trial account.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Delete User's email from all the other fields of the All Trial Accounts.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Notify initiator of deletion confirmation.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td><strong>Purge other users- Enterprise (individuals who are not internal or external Learning Manager users)</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Delete selected user from all other fields of the requesting Enterprise account and All Trial Accounts.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>User deletion from accounts.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Notify initiator of deletion confirmation. </td>
   <td>Yes</td>
  </tr>
  <tr>
   <td><strong>Purge</strong> <strong>other users- Non-Enterprise (individuals who are not internal or external Learning Manager users)</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Delete selected user from all other fields of All Trial accounts.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>User deletion from accounts.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Notify initiator of deletion confirmation.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td><strong>Purge using Adobe IMS- Enterprise</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Notify Enterprise administrator about the request.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Check Email fields for sending notifications.</td>
   <td>No</td>
  </tr>
  <tr>
   <td><strong>Purge using Adobe IMS- Non-Enterprise</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Delete all users having the provided AdobeID/Email from All Trial Accounts.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Delete all users of a Trial account if the provided Email/AdobeId was the creator of the Account.</td>
   <td>Yes</td>
  </tr>
  <tr>
   <td>Delete the select email id from all other fields of all Trial Accounts.</td>
   <td>Yes</td>
  </tr>
 </tbody>
</table>

+++

## Frequently Asked Questions {#frequentlyaskedquestions}

+++How many days does it take for a purge request to complete?

A request to purge users takes a maximum of 30 days to complete.
+++

+++Can you perform a bulk purge in Adobe Learning Manager?

Yes, you can perform a purge in bulk. However, you can only perform a bulk purge of 50 users.
+++

+++Can I restore a purged user?

No. Once purged, all user data is permanently deleted and cannot be recovered.

+++
