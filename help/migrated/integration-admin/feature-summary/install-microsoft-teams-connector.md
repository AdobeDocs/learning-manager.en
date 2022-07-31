---
description: Install Microsoft Teams connector in Adobe Learning Manager
jcr-language: en_us
title: Install Microsoft Teams connector in Adobe Learning Manager
contentowner: saghosh
---


# Overview

Microsoft® Teams® is a persistent chat-based collaboration platform that completely supports document sharing, online meetings, and other features for business communications.

Adobe Learning Manager uses a virtual classroom connector that can be used to integrate Microsoft Teams meetings&nbsp;with&nbsp;Learning Manager.

Microsoft Teams connector connects Learning Manager and Microsoft Teams systems to enable automatic virtual meeting synchronization. The following list describes the Microsoft Teams connector capabilities:

**Set up virtual sessions using Microsoft Teams**

This connector helps integrate your Adobe Learning Manager account with your Microsoft Teams account. Once integrated, the connector enables an Author in Learning Manager to use Microsoft Teams as the technology service provider for the Virtual Classroom modules created in Learning Manager.

**Allow Microsoft Teams to authenticate learners when entering virtual classroom**

This connector helps setup Microsoft Teams meeting organizer from Learning Manager&nbsp;while&nbsp;creating a meeting. The Meeting Organizer can manage lobby to restrict or admit entry into a meeting as well as control other meeting options provided by Microsoft Teams.

**Use&nbsp;automated user completion syncing**

The automated user completion syncing process allows a Learning Manager Administrator to automatically fetch the completion records and recording URL for the&nbsp;Microsoft&nbsp;Teams meeting.

# Roles in Microsoft Teams

If you're organizing a meeting with multiple participants, you can assign roles to each participant so that a participant can know what he/she can&nbsp;do&nbsp;in the meeting.

There are two roles to choose from:&nbsp;**presenter&nbsp;**and&nbsp;**attendee**.

For more information,&nbsp;see&nbsp; [Roles in a Teams Meeting- Microsoft](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

# Set up Microsoft Teams connector

**Note:** Items&nbsp;marked <Developer/Optional>&nbsp;below are optional and mostly for setting up trial/developer&nbsp;tenants&nbsp;with Microsoft&nbsp;in case the user&nbsp;does not&nbsp;have&nbsp;a&nbsp;production tenant.&nbsp;These are optional since they mostly would have already been performed by your Team’s Administrator.

## Create developer E5 Microsoft account&nbsp;<Developer/Optional>

You can access&nbsp;Microsoft&nbsp;Teams connector if you have&nbsp;Office 365 E3&nbsp;or&nbsp;Office 365 E5. The recommended option is&nbsp;Office 365 E5.&nbsp;

* `Visit the` [Microsoft plans page](https://www.microsoft.com/en-in/microsoft-365/enterprise/compare-office-365-plans?&ef_id=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&OCID=AID2100137_SEM_CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&lnkd=Google_O365SMB_Brand&gclid=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE) `. On the webpage, you can either buy E3 or E5 account or click Try for Free.`

* Provide the required information and create an account.

**Note:**&nbsp;The account must&nbsp;use&nbsp;the format&nbsp;“<username>@<company name>.onmicrosoft.com.”

# Create application for&nbsp;Microsoft&nbsp;Teams connector

1. Visit&nbsp;the&nbsp; [Microsoft Azure® portal](https://portal.azure.com/).
1. Sign in with the Microsoft E5 account that&nbsp;you&nbsp;created in the previous section.
1. Search for&nbsp;**Azure Active Directory**.&nbsp;
1. Click&nbsp;**App Registrations**.&nbsp;
1. Click&nbsp;**New Registration**,&nbsp;enter the following details, and register the application:

   1. **Name&nbsp;**—&nbsp;Any name of your choice.
   1. **Supported account types**&nbsp;—&nbsp;Accounts in any organizational directory (Any Azure Active&nbsp;Directory - Multitenant).&nbsp;
   1. **Redirect URI (optional)**&nbsp;—&nbsp;Optional&nbsp;field indicating the&nbsp;reply&nbsp;URL.

1. In the&nbsp;**Essentials&nbsp;**column, note the following IDs, which will&nbsp;be further&nbsp;used during&nbsp;the integration:&nbsp;

   1. **Application (client) ID**
   1. **Directory (tenant) ID**

1. Search for&nbsp;client credentials and click&nbsp;**Add a certificate or secret**.
1. Click&nbsp;**New Client secret**&nbsp;and add the following details:&nbsp;&nbsp;

   1. **Description&nbsp;**—&nbsp;Enter any name.
   1. **Expires&nbsp;**—&nbsp;Set to any value (recommended&nbsp;value is&nbsp;24&nbsp;months. Ensure that new client credentials are generated once the previous one expires).

Note the&nbsp;client secret, which&nbsp;will be further used during the integration.

# Get access permission for&nbsp;Microsoft&nbsp;Teams connector

1. Visit the&nbsp; [Microsoft Azure portal](https://portal.azure.com/).&nbsp;
1. Sign in with the Microsoft E5&nbsp;that you created earlier.&nbsp;
1. Search for&nbsp;**Azure Active Directory**.
1. Click&nbsp;**App Registrations**.
1. Click the app that you created in the previous section.
1. Click&nbsp;**API permissions**.
1. Click&nbsp;**Add a permission**.
1. Select&nbsp;**Microsoft Graph > Application permissions**&nbsp;and add the following permissions:

   1. User.Read&nbsp;(This will&nbsp;be present by default)&nbsp;
   1. Calendars.ReadWrite&nbsp;
   1. Directory.Read.All&nbsp;&nbsp;
   1. Directory.ReadWrite.All&nbsp;&nbsp;
   1. OnlineMeetings.Read.All&nbsp;&nbsp;
   1. OnlineMeetings.ReadWrite.All&nbsp;&nbsp;
   1. OnlineMeetingArtifact.Read.All&nbsp;&nbsp;
   1. User.Read.All&nbsp;&nbsp;
   1. User.ReadWrite.All
   1. Chat.Read.All
   1. Chat.ReadWrite.All

1. Click&nbsp;**Grant admin access for Adobe**.&nbsp;
1. Click&nbsp;**App roles > Create app role**.&nbsp;
1. Enter the following values:&nbsp;

   1. **Display name**&nbsp;—&nbsp;Name of&nbsp;the&nbsp;API/Permission name (For example,&nbsp;Calendars.ReadWrite).
   1. **Allowed member types**&nbsp;—&nbsp;Specify both&nbsp;users and applications&nbsp;(Users/Groups + Applications).&nbsp;
   1. **Value&nbsp;**—&nbsp;Name of&nbsp;the&nbsp;API/Permission name (For example,&nbsp;Calendars.ReadWrite).
   1. **Description&nbsp;**—&nbsp;Name of&nbsp;the&nbsp;API/Permission name (For example,&nbsp;Calendars.ReadWrite).
   1. **Do you want to enable this app role?&nbsp;**—&nbsp;Select&nbsp;this checkbox.

1. &nbsp;Repeat the&nbsp;preceding&nbsp;steps for all the nine API/Permissions that were added.

# **Configure access policy by using&nbsp;PowerShell scripts  
**

To configure the application access policy for Microsoft Teams connector by running PowerShell scripts, follow the procedure described in this&nbsp; [document](https://docs.microsoft.com/en-us/graph/cloud-communication-online-meeting-application-access-policy).

This enables the connector to access Microsoft Teams online meetings.

**Note: **In the above document,&nbsp;execute Optional step 5&nbsp;as well&nbsp;to ensure that any active user can be granted the role of the organizer from&nbsp;within the Learning Manager&nbsp;Author app. If this step is not executed, users&nbsp;will&nbsp;not have&nbsp;the&nbsp;required&nbsp;access&nbsp;permissions&nbsp;to&nbsp;be&nbsp;organizers and the meeting creation will fail (Microsoft APIs consider the organizer to be the creator of&nbsp;a&nbsp;Teams meeting).

# Set up&nbsp;Microsoft&nbsp;Teams connector in Learning Manager

1. `Sign in to Learning Manager as an Integration Admin.`  

1. `In the Connectors page, select Microsoft Teams connector and click **Connect**.`  

1. `Enter these values:`

   1. `**Connection Name** — Give the name that author will see while creating the session.`  
   
   1. `**Microsoft Teams Tenant Id** — Enter the value determined earlier.`  
   
   1. `**Microsoft Teams Client Id** — Enter the value determined earlier.`  
   
   1. `**Microsoft Teams Client Secret** — Enter the value determined earlier.`  
   
   1. `**Microsoft Teams Admin User Email **— Enter the default organizer email. This user (typically a service user) would be the meeting creator in case no explicit organizer is selected from the Learning Manager Author app.`

# Allocate licenses to users&nbsp;<Developer/Optional>

1. `Visit` [https://admin.microsoft.com/#/homepage](https://admin.microsoft.com/#/homepage) `.`  

1. `Click **Users > Active Users**.`  

1. `Click **More actions for Users** for the users to whom you want to provide access to Microsoft Teams. `  

1. `Click **Manage Product Licenses**. `  

1. `Enable License for Office 365 E5 without audio conferencing.`

# Record a session

The API used for recording a session is a protected API. To access the API, you must request access from Microsoft. For more information, see this&nbsp; [document](https://docs.microsoft.com/en-us/graph/teams-protected-apis).

In the document,

*“To request access to these protected APIs, complete the following&nbsp; [request form](https://aka.ms/teamsgraph/requestaccess). We review access requests every Wednesday and deploy approvals every Friday, except during major holiday weeks in the U.S. Submissions during those weeks will be processed the following non-holiday week. To verify whether your request has been approved, test your application access on the next applicable Monday.”*

For learners, the recording URL is displayed on the VC course overview page.

After 30 minutes of completing a course, the attendance for the learner gets marked.

# Frequently Asked Questions&nbsp;

+++Who is an Organizer and a Presenter?

See the&nbsp; [documentation](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)&nbsp;from Microfsoft for different roles and capabilities that are supported by Microsoft Teams.

+++

+++Should an organizer be a registered user in both Learning Manager and Microsoft Teams? 

Yes, the organizer should also be part of both Learning Manager and Microsoft Teams. Moreover, the&nbsp;organizer must be a part of the same Microsoft tenant, which is configured in the Integration admin app.

+++

+++Should a presenter be a registered user in both Learning Manager and Microsoft Teams? 

Yes, the presenter should also be part of both Learning Manager and Microsoft Teams.&nbsp;The presenter must have an Azure Active directory ID (can be part of the same tenant as the organizer or part of any other tenant). Moreover, even anonymous users (users who login with just the username and not part of Active Directory) can also be made presenters by the organizer/existing presenters&nbsp;during the meeting.&nbsp;

+++

+++Microsoft Teams has meetings, webinars, and live events. Which one does the Teams connector support? 

At present, the&nbsp;Teams connector supports only Meetings&nbsp;in&nbsp;Microsoft Teams. For more information, see this&nbsp; [document](https://docs.microsoft.com/en-us/microsoftteams/quick-start-meetings-live-events).&nbsp;

+++

