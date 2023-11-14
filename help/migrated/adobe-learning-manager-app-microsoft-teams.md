---
description: Adobe Learning Manager App for Microsoft Teams
jcr-language: en_us
title: Adobe Learning Manager App for Microsoft Teams
contentowner: saghosh
---


# Adobe Learning Manager App for Microsoft Teams {#adobe-learning-manager-app-for-microsoft-teams}

## How to set up&nbsp;  
{#addtextandotherelements}

Setting up ALM on MS Teams involves three steps and needs assistance from the ALM Administrator and Microsoft Azure Administrator. In some organizations, the Azure Administrator and MS Teams Administrators are not the same, and therefore require additional MS Teams Administrators as well.

**ALM Admin – Integration Admin role approves Teams app**

After the Integration Admin approves the MS Teams app, the Adobe Learning Manager app willl available in the MS Teams app store, and your learners can access it. However, the app will not have notifications, silent login, and the app will not be pinned for the learners in MS Teams.

For more information, see [Integration Admin role approves Teams app](#Integration_Admin_role_approves_Teams_app).&nbsp;

**Microsoft Azure Admin approves the permission for ALM app in Azure dashboard&nbsp;**

The Azure administrator will have to approve the permissions required for the ALM app. This will allow that ALM app to send notifications to MS Teams and allow silent login. In silent login, users need not log in separately to Adobe Learning Manager on the browser.

For more information, see [Azure admin approves the permissions](#Microsoft_Azure_Admin_approves_permission_for_ALM_app_in_Azure_dashboard).

**MS Teams admin creates a policy for ALM teams&nbsp;&nbsp;**

The MS Teams Admin in their Admin Center should pin the ALM app for all their users and allow it as a global policy. In case ALM is only used by a certain group in the company, then the MS Teams administrator must choose a custom policy and apply it to that specific group only.

For more information, see&nbsp; [MS Teams admin creates a policy](#create_policy).

## Integration Admin role approves Teams app&nbsp;  
{#Addtextandotherelements-1}

Follow the steps below:&nbsp;

1. On the Integration Administrator app, select **[!UICONTROL Applications> Featured Apps]**, and select **[!UICONTROL ALM Teams app]**.&nbsp;

   ![](/content/dam/help/en/learning-manager/integration_admin_featured_apps.jpg)

1. On the upper-right corner of the screen, select **[!UICONTROL Approve]**.&nbsp;

   ![](/content/dam/help/en/learning-manager/integration_admin_approval_form.jpg)

1. Select **[!UICONTROL OK]**on the dialog box that appears.&nbsp;

   ![](/content/dam/help/en/learning-manager/integration_admin_approved_dialog_box.jpg)

1. Once approved, you will be able to see ‘ALM Teams App’ in the External Apps section.&nbsp;

   ![](/content/dam/help/en/learning-manager/integration_admin_external_apps.jpg)

Now, users can access the ALM app on MS Teams.&nbsp;

## Microsoft Azure Admin approves the permission for ALM app in Azure dashboard  
{#Addtextandotherelements-2}

Follow the steps below:&nbsp;

1. As an Azure Admin, navigate to the Manage Azure Active Directory section in the Azure dashboard.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_azure.jpg)

1. Paste the following link in a separate browser window:  
   [https://login.microsoftonline.com/<tenantIdTobeReplaced>/oauth2/authorize?client_id=8d349d9f-bf59-4ece-8022-a41e87d81903&response_type=code&redirect_uri=https://learningmanager.adobe.com](https://login.microsoftonline.com/%3CtenantIdTobeReplaced%3E/oauth2/authorize?client_id=5562e319-2396-47f9-9cd1-b3913effe9f9&response_type=code&redirect_uri=https://learningmanager.adobe.com)&nbsp;  

1. In the above link, replace <tenantIdTobeReplaced> with the tenant id available in the Overview page below. Enter the new URL.&nbsp;  

1. Add Adobe Learning Manager app to your Azure applications.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_azure_dashboard.jpg)

1. Select the Enterprise Applications tab and select All Applications. You will see ALMTeamsApp listed there.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_azure_enterprise_applications.jpg)

1. Click the app and navigate to the Permissions tab.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_azure_ALMTeamsNonProdApp.jpg)

1. In the Permissions tab, select ‘ **[!UICONTROL Grant admin consent for MSFT]**’ to give ALM teams app permissions.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_azure_ALMTeamsNonProdApp_permissions.jpg)

1. Select **[!UICONTROL Accept]**.

   ![](/content/dam/help/en/learning-manager/microsoft_azure_ALMTeamsNonProdApp_permission_request.jpg)

1. Once granted, these permissions will give the ALM app to allow silent logins and send notifications to the learners in the MS Teams app.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_azure_ALMTeamsNonProdApp_permission_request_granted.jpg)

## MS Teams admin creates a policy for Teams app  
{#Addtextandotherelements-3}

Follow the steps below:&nbsp;

1. As an MS Teams admin, in the Admin Center, create a policy for adding the Teams app to your learners’ Teams app.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_teams_admin_center.png)

1. Navigate to the section, Setup Policies. Create a Global policy and select **[!UICONTROL Add apps]** in Pinned Apps sub-section.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_teams_admin_center_add_installed_apps.png)

1. In the dialog that follows, search for **[!UICONTROL Adobe Learning Manager]**, and add the app. This adds Adobe Learning Manager in the Installed Apps section.&nbsp;

   ![](/content/dam/help/en/learning-manager/microsoft_teams_admin_center_installed_apps.png)

1. Save this policy. This makes the app available to everyone in the organization.&nbsp;

Alternatively, admins can create a custom policy instead of a global policy. Add Adobe Learning Manager to that custom policy, and then apply the custom policy to only those set of users who need to access ALM.&nbsp;  

