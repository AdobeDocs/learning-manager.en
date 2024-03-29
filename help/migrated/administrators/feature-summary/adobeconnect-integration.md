---
jcr-language: en_us
title: Adobe Connect integration
description: Authors can create virtual classroom courses with Adobe Connect during course creation process. To enable Adobe Connect for your Learning Manager account, you need to contact the Administrator of your organization.
contentowner: jayakarr
exl-id: 13458f93-9ea7-4aab-8b33-3c4f4dd5886d
---
# Adobe Connect integration

Administrators of an organization can configure the settings of Learning Manager account to enable Adobe Connect integration.

## Configure Adobe Connect {#configureadobeconnect}

1. In Administrator login, click **[!UICONTROL Settings]** at the left pane to view the basic information about your company. Click **[!UICONTROL Adobe Connect]** on the left pane.

   ![](assets/left-pane.png)

   *Select Adobe Connect in the left pane*

1. Click **[!UICONTROL Configure Now]** link in **[!UICONTROL Adobe Connect Configuration]** section.

   <!--![](assets/configure-now-connect.png)-->

1. Provide your company's Adobe Connect domain name and log in credentials.

   ![](assets/adobeconnect-config.png)

   *Add domain name and credentials*

   A sample Adobe Connect URL: mycompany.adobeconnect.com  
   You need to provide email id of the Adobe connect account's Administrator. 

   Only Adobe hosted connect accounts are supported in Learning Manager. Example; '.adobeconnect.com'.

1. Click **[!UICONTROL Integrate].**

   After authenticating the email id, Learning Manager displays the message as Connect is successfully integrated. You can start viewing your virtual classroom courses using Adobe Connect automatically.

   Adobe Connect account administrator should accept the Terms and Conditions of using Adobe Connect. If this is not accepted, your login authentication may fail. After creating the Adobe Connect account, log in to the account once. During first time login, a terms and conditions page appears.

   <!--![](assets/mail-confirmation.png)-->

## Add virtual classroom session information {#addvirtualclassroomsessioninformation}

If the author of a virtual classroom course has not provided the session information, then Administrator can include the session details.

In Administrator login, click the VC course name. Click **[!UICONTROL Instances]** on the left pane and click **[!UICONTROL Session Details]**.  Click the Edit icon at the right corner of the Session Details page to add the session information.

![](assets/session-creation-admin.png)

*Add virtual classroom session information*

With the integration of Adobe Learning Manager and Adobe Connect for creating virtual classroom modules or sessions, your Connect account should support Meeting rooms with adequate number of rooms and concurrent users for your use case. These meeting rooms are used to host Learning Manager virtual classroom modules. A new Connect meeting room is dynamically created by Learning Manager for each virtual classroom module or session within Learning Manager.

You must purchase Adobe Connect separately, apart from Adobe Learning Manager.

## Learners attendance {#learnersattendance}

If the host of Virtual classroom course do not attend the session, then attendance does not register automatically for learners who attended the session. In such scenarios, Administrator can record the attendance manually.

Click the virtual classroom course, click Attendance on the left pane of the following page and record the attendance.
