---
jcr-language: en_us
title: Credly
description: Learn about Credly integration with ALM to manage and share external badges from the platform across various social media channels
contentowner: chandrum
---
# Credly

[Credly](https://info.credly.com/) is a digital credentialing platform that allows learners and organizations to earn, share, and verify professional achievements, such as badges or certifications. Learners can manage and share badges through their Credly profile on social media and other places. 

## Pre-requisite

Set up a Credly account for your organization. Add learners to Credly using their email IDs in Adobe Learning Manager. This will allow the learners to see the badges on Credly and Adobe Learning Manager.

## Add the Credly Connector to Adobe Learning Manager

Follow these steps to add the Credly Connector to Adobe Learning Manager:

1. Log in as **[!UICONTROL Integration Admin]**.
2. Select **[!UICONTROL Credly]** > **Connect** to add the **[!UICONTROL Credly]** connector to Adobe Learning Manager.

   ![](assets/connector-credly.png) 
   _Add Credly connector_

3. Type the **[!UICONTROL Connection Name]**.
4. Type the **[!UICONTROL Organization ID]** and **[!UICONTROL Authorization token]**.

   >[!NOTE]
   >
   >Each badge in Credly comes with an Organization ID and Authorization Token. Copy these values from Credly.

5. Type the **[!UICONTROL Hostname]** and select **[!UICONTROL Connect]**.

## Migrate badges from Credly

The badge.csv in Adobe Learning Manager allows you to migrate badges from the existing LMS or external systems. The badge.csv has been updated with two new columns:

* External badge ID
* External badge provider. 

External badge ID refers to the badge template ID in the Credly platform, and the external badge provider is Credly. Add these values in badge.csv and follow the steps mentioned in the [Migration manual](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/migration-manual#migrationprocedure) to migrate the csv.

## Create a skill - Admin

Once the badge has been imported into Adobe Learning Manager, admin can create this badges as a skill. To know how to create a skill, see [Create and modify Skills](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/skills-levels).

### Assign the skill/badge to the learning object- Author

The author/Admin can assign these Credly imported ALM badges to a course, learning path or certification (not just skills), and on the consumption of these learning objects, the badge will be achieved and can be viewed on Credly and ALM App.

Learners can log in to Credly and see the badges in the Credly platform. From Credly, they can share the badges on external platforms like LinkedIn and other social media.

