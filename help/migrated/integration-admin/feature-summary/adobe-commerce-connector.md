---
description: Learn on how to integrate Adobe Commerce connector
jcr-language: en_us
title: Adobe Commerce connector
contentowner: mmanuel
---

# Adobe Commerce connector in Adobe Learning Manager

## Adobe Commerce connector

>[!NOTE]
>
>This feature is available only if Adobe Learning Manager is sold as an **add-on** to Adobe Experience Manager. The connector can also be enabled for **trial** accounts.

Adobe Learning Manager integrates with Adobe Commerce, an extensible and scalable eCommerce solution that lets you deliver multi-channel commerce experiences for B2B and B2C customers. Use the Adobe Commerce connector to connect Adobe Learning Manager with Adobe Commerce to enable paid training and eCommerce capabilities within your learning platform.

When the connector is enabled, Learning Manager sends training data to Adobe Commerce so learners can purchase courses, learning paths, or certifications. The connector also collects purchase information to validate transactions and grant learners access to their training.

## Prerequisites

Before you set up the Adobe Commerce connector, ensure the following:

- Enable [RabbitMQ](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/start/overview) or any other messaging broker.
- Enable [CRON](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/start/overview#cron_consumers_runner) jobs.

To enable these, edit the following files:

- .magento.app.yaml
- .magento/services.yaml
- .magento.env.yaml

Other setup requirements:

- Override options limit using a custom module. This step is optional but recommended for large datasets.
- Enable all **asynchronous APIs**. Large training datasets are exported asynchronously. When Learning Manager calls Adobe Commerce APIs, requests are queued and processed by a consumer that creates products on the commerce side. Asynchronous processing must be enabled because it is not available by default in Adobe Commerce.
- Add a **return link** to Learning Manager on the payment success page in Adobe Commerce.
  - Use this [return URL](https://learningmanager.adobe.com/app/learner#/postPayment): 
- Change **indexing** from **On Save** to **Scheduled**. See the [Knowledge Base](https://experienceleague.adobe.com/en/support?support-tab=home#home) for more information.
- Apply the required **patches**. See [Apply patches documentation](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/start/overview) for instructions.
- Configure **Fastly** for Adobe Commerce on cloud infrastructure (Staging and Production). See [Set up Fastly](https://devdocs.magento.com/cloud/cdn/configure-fastly.html) for more information.

## Configure the connector

To configure Adobe Commerce Connector:

1. Log in to Adobe Learning Manager as an integration administrator.
2. Hover over the **Adobe Commerce** connector tile and select **Connect**.

   ![](assets/adobe-commerce-connector1.png)
      _Select Connect to configure Adobe Commerce connector_

3. Type the following details:

   - Connection Name
   - Access Token
   - Adobe Commerce URL
   - Store Code
4. Select the Type of interface from the following:

   - Native Learning Manager
   - Custom-made using AEM Sites

   ![](assets/adobe-commerce-connector2.png)
      _Type the required details for Adobe Commerce configuration_

5. Select **Connect**.

## Set pricing for training

Once the connection is enabled:

- Authors can set prices for courses, learning paths, or certifications.
- After publishing, learners can buy training through Adobe Learning Manager or a custom AEM site.

## Purchase flow

### Native Adobe Learning Manager

- Learners log in to Adobe Learning Manager to buy a course, learning path, or certificate.
- When learners click Buy Now, they are redirected to Adobe Commerce to complete the payment.
- After payment, learners are prompted to return to Adobe Learning Manager to start the training.
- Learners must log in separately to Adobe Commerce to complete the purchase.
- Learners receive purchase confirmation emails from both Learning Manager and Adobe Commerce. Adobe Commerce emails can be enabled or disabled as needed.

### Custom AEM Sites

When using custom AEM sites:

- Learners can browse and buy courses through the AEM site.
- The AEM site uses metadata synced from Adobe Learning Manager for search and display.
- Both logged-in and guest users can browse. However, only logged-in users can purchase.
- After login, learners can add courses to their cart, preview details, and complete the purchase.

## Export courses to Adobe Commerce

### Schedule export

To schedule the export:

1. Select **Export Training Metadata** and then select **Configure Schedule**.
2. Select **Enable training metadata export using this connection**.
3. Select **Enable schedule** and set the **start date**, **time**, and **interval**.

   ![](assets/adobe-commerce-connector3.png)
         _Enable the scheduled export_

4. Select **Save**.

### On demand export

After authors set prices for training, the integration administrator must export the training data:

1. Select **Export Training Metadata** and then select **On Demand**.
2. Select the date range.
3. Select **Execute** to export.

   ![](assets/adobe-commerce-connector4.png)
            _Create on-demand export_

4. Upon success, priced courses and learning paths are moved to Adobe Commerce for purchase.
