---
title: Non-logged in experience for learners
description: Adobe Learning Manager native portal will support a non-logged way of accessing the training site. With this mode enabled, learners can discover and access the training site and check out various courses and content available. The non-logged in experience enables learners to browse courses without being logged in to a portal.
---
# Non-logged in experience for learners

Adobe Learning Manager native portal will support a non-logged way of accessing the training site. With this mode enabled, learners can discover and access the training site and check out various courses and content available.

The non-logged in experience enables learners to browse courses without being logged in to a portal.

For the non-logged in homepage to be enabled, the Integration Admin must enable and configure the [Training Data Connector](/help/migrated/integration-admin/feature-summary/connectors.md#training-data-access).

The training can then be exported from the connector.

>[!NOTE]
>
>Ensure that the option Native Learning Manager is selected. 

The Administrator can modify and configure the homepage, which is meant for non-logged in users.

>[!IMPORTANT]
>
>Adobe Learning Manager Learner APIs allow you to create a custom learning experience for your users. The usage of these APIs need a valid user token and are to be used only for the purpose of workflows where there is a fully licensed/registered Learner. They are not to be used, as is, for any sort of data retrieval to support any non-logged in user/shared users or any other such cases. Non logged in use cases require special handling. Reach out to the Solution Architecture team, in case you have any questions on the appropriate use of these APIs and ensure that a Solution Architect has vetted a solution before you deploy it.


## Launch the homepage options

On the Adobe Learning Manager homepage, select **Branding**. Then, on the left pane, select Non-logged in Homepage.

![homepage options](assets/non-logged-in-homepage.png)

*Select the option Non-logged in Homepage*

## Add a banner

Add a banner for any marketing announcement or feature the trending topic of the day. Select **Add banner**.

![banner](assets/add-banner-image.png)

*Add a banner*

Browse to the location of the image to be used as the banner. Then provide a link as an action button on the banner image. 

## Add categories

This component can be used to filter catalog by tags, skills, and catalog. This section contains a header and description for each category. Upon clicking, the user is redirected to the catalog page with the applied filters.  

Select **[!UICONTROL Add category]**. Then enter the details for the category. 

![add category](assets/add-category.png)

*Add the categories*

Save the category. The category is added to the section.

## Add a catalog

Add a catalog for non-logged in users so that they can browse all the training on the platform.

![add catalog](assets/add-catalog.png)

*Add a catalog*

All exported training will be present.

## Unsupported features

* Job aids will not be exported. However, learners can see them after logging in. 
* Sort By in the catalog component. 
* Default view setting used in admin app (Settings > General > List View). 
* Star rating/effectiveness. 
* Card icon setting. 
* Relevant skills and tags setting. 
* Learner app view that is shown catalog-wise. 
* Training overview pages - Clicking on the card redirects to Sign Up, after which a user is redirected to the training overview page / instance page.
* All enabled catalogs will be present. Any learner not having access to a catalog is unable to see the catalog and training in it after logging in.
