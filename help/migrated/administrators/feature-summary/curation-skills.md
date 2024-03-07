---
jcr-language: en_us
title: Map skill with skill domains
description: To auto curate a post that is posted by a user by the AI-enabled Curation Engine for a particular skill domain, the user's enterprise must have their customized skills to be mapped to the supported skill domains present in the Learning Manager LMS.
contentowner: kuppan
---


# Map skill with skill domains

To auto curate a post that is posted by a user by the AI-enabled Curation Engine for a particular skill domain, the user's enterprise must have their customized skills to be mapped to the supported skill domains present in the Learning Manager LMS.

While creating a skill, an Administrator can map it with the most relevant skill domains that Learning Manager supports. This will further be considered in Auto Curation process. Learning Manager LMS lists the following skills:

* Supply chain management
* Accounting
* Scientific research and engineering
* Computer security
* Strategic management
* Social media
* Medicine
* Finance
* Workplace safety
* Soft skills
* Business law
* Management
* Human resource management
* Technical communication
* Business ethics
* Customer relationship management
* Information technology
* Production and manufacturing
* Marketing
* Quality management
* Business process
* Learning
* Design
* Analytics
* Sales

>[!NOTE]
>
>According to the algorithm, if the confidence score is less than 50%, the content is marked for manual curation.


To add a skill domain, follow the steps below:

1. On the left pane of the Administrator app, click **[!UICONTROL Skills]**.
1. To add a skill, click **[!UICONTROL Add]** on the top right of the page.
1. In the **[!UICONTROL Add Skill]** dialog, add a skill and a description of the skill.
1. In the **[!UICONTROL Skill Domain]** section, add the skill domains. As you enter a domain, the domains get added. These domains are populated from the list mentioned above.

   ![](assets/skill-domain-mapping.png)

   *Add the skill domains in the Skill Domain section*

1. To save the changes, click **[!UICONTROL Save]**.

When a user posts a content in a board, the content gets curated and is approved or rejected, depending on the confidence score against the mapped skill to the board.

<!--![](assets/content-uploaded.png)-->

Depending on whether the content being uploaded has a confidence score of more than 50%, the content gets uploaded in the board. If your content meets the criteria, then you get to see a notification that says that the content has been successfully curated and is now available in the board.

![](assets/curation-notification.png)

*View notifications depending on the confidence score*

