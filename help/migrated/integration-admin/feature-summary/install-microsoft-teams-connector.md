---
description: Install Microsoft Teams connector in Adobe Learning Manager
jcr-language: en_us
title: Install Microsoft Teams connector in Adobe Learning Manager
contentowner: saghosh
exl-id: 68092187-ac69-4727-a3dc-f3047a1e164d
---
# Install Microsoft Teams connector in Adobe Learning Manager

## Overview

Microsoft Teams&reg; is a persistent chat-based collaboration platform that completely supports document sharing, online meetings, and other features for business communications.

Adobe Learning Manager uses a virtual classroom connector that can be used to integrate Microsoft Teams meetings with Learning Manager.

Microsoft Teams connector connects Learning Manager and Microsoft Teams systems to enable automatic virtual meeting synchronization. The following list describes the Microsoft Teams connector capabilities:

**Set up virtual sessions using Microsoft Teams**

This connector helps integrate your Adobe Learning Manager account with your Microsoft Teams account. Once integrated, the connector enables an Author in Learning Manager to use Microsoft Teams as the technology service provider for the Virtual Classroom modules created in Learning Manager.

**Allow Microsoft Teams to authenticate learners when entering virtual classroom**

This connector helps setup Microsoft Teams meeting organizer from Learning Manager while creating a meeting. The Meeting Organizer can manage lobby to restrict or admit entry into a meeting as well as control other meeting options provided by Microsoft Teams.

**Use automated user completion syncing**

The automated user completion syncing process allows a Learning Manager Administrator to automatically fetch the completion records and recording URL for the Microsoft Teams meeting.

## Roles in Microsoft Teams

If you're organizing a meeting with multiple participants, you can assign roles to each participant so that a participant can know what he/she can do in the meeting.

There are two roles to choose from: **presenter** and **attendee**.

For more information, see  [Roles in a Teams Meeting- Microsoft](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

## Set up Microsoft Teams connector

>[!NOTE]
>
>Items marked <Developer/Optional> below are optional and mostly for setting up trial/developer tenants with Microsoft in case the user does not have a production tenant. These are optional since they mostly would have already been performed by your Team's Administrator.

## Create developer E5 Microsoft account <Developer/Optional>

You can access Microsoft Teams connector if you have Office 365 E3 or Office 365 E5. The recommended option is Office 365 E5. 

* Visit the [Microsoft plans page](https://www.microsoft.com/en-in/microsoft-365/enterprise/compare-office-365-plans?&ef_id=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&OCID=AID2100137_SEM_CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&lnkd=Google_O365SMB_Brand&gclid=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE). On the webpage, you can either buy E3 or E5 account or click Try for Free.
* Provide the required information and create an account.

>[!NOTE]
>
>The account must use the format `<username>@<company name>.onmicrosoft.com`.

## Create application for Microsoft Teams connector

1. Visit the  [Microsoft Azure&reg; portal](https://portal.azure.com/).
1. Sign in with the Microsoft E5 account that you created in the previous section.
1. Search for **Azure Active Directory**. 
1. Click **[!UICONTROL App Registrations]**. 
1. Click **[!UICONTROL New Registration]**, enter the following details, and register the application:

   1. **Name** - Any name of your choice.
   1. **Supported account types** - Accounts in any organizational directory (Any Azure Active Directory - Multitenant). 
   1. **Redirect URI (optional)** - Optional field indicating the reply URL.

1. In the **Essentials** column, note the following IDs, which will be further used during the integration: 

   1. **Application (client) ID**
   1. **Directory (tenant) ID**

1. Search for client credentials and click **[!UICONTROL Add a certificate or secret]**.
1. Click **[!UICONTROL New Client secret]** and add the following details:  

   1. **Description** - Enter any name.
   1. **Expires** - Set to any value (recommended value is 24 months. Ensure that new client credentials are generated once the previous one expires).

Note the client secret, which will be further used during the integration.

## Get access permission for Microsoft Teams connector

1. Visit the  [Microsoft Azure portal](https://portal.azure.com/). 
1. Sign in with the Microsoft E5 that you created earlier. 
1. Search for **Azure Active Directory**.
1. Click **[!UICONTROL App Registrations]**.
1. Click the app that you created in the previous section.
1. Click **[!UICONTROL API permissions]**.
1. Click **[!UICONTROL Add a permission]**.
1. Select **[!UICONTROL Microsoft Graph]** > **[!UICONTROL Application permissions]** and add the following permissions:

   1. Chat.Read.All
   1. Directory.Read.All
   1. OnlineMeetingArtifact.Read.All  
   1. OnlineMeetings.Read.All  
   1. OnlineMeetings.ReadWrite.All  
   1. User.Read.All
   1. OnlineMeetingRecording.Read.All

1. Click **[!UICONTROL Grant admin access for Adobe]**. 
1. Click **[!UICONTROL App roles]** > **[!UICONTROL Create app role]**. 
1. Enter the following values: 

   1. **Display name** - Name of the API/Permission name (For example, Calendars.ReadWrite).
   
   1. **Allowed member types** - Specify both users and applications (Users/Groups + Applications).
   
   1. **Value** - Name of the API/Permission name (For example, Calendars.ReadWrite).
   
   1. **Description** - Name of the API/Permission name (For example, Calendars.ReadWrite).
   
   1. **Do you want to enable this app role?** - Select this checkbox.

1. Repeat the preceding steps for all the nine API/Permissions that were added.

## Configure access policy by using PowerShell scripts

To configure the application access policy for Microsoft Teams connector by running PowerShell scripts, follow the procedure described in this  [document](https://docs.microsoft.com/en-us/graph/cloud-communication-online-meeting-application-access-policy).

This enables the connector to access Microsoft Teams online meetings.

>[!NOTE]
>
>In the above document, execute Optional step 5 as well to ensure that any active user can be granted the role of the organizer from within the Learning Manager Author app. If this step is not executed, users will not have the required access permissions to be organizers and the meeting creation will fail (Microsoft APIs consider the organizer to be the creator of a Teams meeting).

## Set up Microsoft Teams connector in Learning Manager

1. Sign in to Learning Manager as an **Integration Admin**.  

1. In the Connectors page, select Microsoft Teams connector and click **[!UICONTROL Connect]**.  

1. Enter these values:

   1. **Connection Name** - Give the name that author will see while creating the session.  
   
   1. **Microsoft Teams Tenant Id** - Enter the value determined earlier.  
   
   1. **Microsoft Teams Client Id** - Enter the value determined earlier.  
   
   1. **Microsoft Teams Client Secret** - Enter the value determined earlier.  
   
   1. **Microsoft Teams Admin User Email** - Enter the default organizer email. This user (typically a service user) would be the meeting creator in case no explicit organizer is selected from the Learning Manager Author app.

## Allocate licenses to users <Developer/Optional>

1. Visit [https://admin.microsoft.com/#/homepage](https://admin.microsoft.com/#/homepage).  
1. Click **[!UICONTROL Users]** > **[!UICONTROL Active Users]**.  
1. Click **[!UICONTROL More actions for Users]** for the users to whom you want to provide access to Microsoft Teams.   
1. Click **[!UICONTROL Manage Product Licenses]**.   
1. Enable License for Office 365 E5 without audio conferencing.

<!--## Record a session

The API used for recording a session is a protected API. To access the API, you must request access from Microsoft. For more information, see this  [document](https://docs.microsoft.com/en-us/graph/teams-protected-apis).

In the document,

*"To request access to these protected APIs, complete the following  [request form](https://aka.ms/teamsgraph/requestaccess). We review access requests every Wednesday and deploy approvals every Friday, except during major holiday weeks in the U.S. Submissions during those weeks will be processed the following non-holiday week. To verify whether your request has been approved, test your application access on the next applicable Monday."*

For learners, the recording URL is displayed on the VC course overview page.

After 30 minutes of completing a course, the attendance for the learner gets marked. -->

## Frequently Asked Questions 

+++Who is an Organizer and a Presenter?

See the  [documentation](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019) from Microfsoft for different roles and capabilities that are supported by Microsoft Teams.

+++

+++Should an organizer be a registered user in both Learning Manager and Microsoft Teams? 

Yes, the organizer should also be part of both Learning Manager and Microsoft Teams. Moreover, the organizer must be a part of the same Microsoft tenant, which is configured in the Integration admin app.

+++

+++Should a presenter be a registered user in both Learning Manager and Microsoft Teams? 

Yes, the presenter should also be part of both Learning Manager and Microsoft Teams. The presenter must have an Azure Active directory ID (can be part of the same tenant as the organizer or part of any other tenant). Moreover, even anonymous users (users who login with just the username and not part of Active Directory) can also be made presenters by the organizer/existing presenters during the meeting. 

+++

+++Microsoft Teams has meetings, webinars, and live events. Which one does the Teams connector support? 

At present, the Teams connector supports only Meetings in Microsoft Teams. For more information, see this  [document](https://docs.microsoft.com/en-us/microsoftteams/quick-start-meetings-live-events). 

+++
