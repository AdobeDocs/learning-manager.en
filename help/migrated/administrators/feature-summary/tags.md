---
description: Learn how to manage tags on Learning Manager.
jcr-language: en_us
title: Tags
contentowner: dvenkate
---


# Tags {#tags}

Administrators can now manage tags in Learning Manager. Use better tagging and manageable data base to help learners search better and get to appropriate search results quickly. You can manage redundant, misspelled, and irrelevant tags using this feature. You can also add, edit, delete, append, or replace tags.

The list of Learning Objects associated with the tag can be viewed by clicking on the count provided next to each tag. The list shows the number of Courses, Learning Programs, Certificates, Job Aids, and Content Groups. Click on any of these options to view the list.

You can sort the tags based on usage or alphabetical order using the **[!UICONTROL Sort By]** option.

## Add/ Delete/ Edit tags {#adddeleteedittags}

1. As an Administrator, on the left navigation panel, click **[!UICONTROL Tags]**. The **[!UICONTROL Tag Management]** page opens.
1. To add a new tag, click **[!UICONTROL Add]**. The Add button is available on the top right corner of the page. If there are no existing tags, the **[!UICONTROL Add]** button will also be available in the middle of the **[!UICONTROL Tag Management]** page.

   While adding multiple tags, separate them using (,) or (;). A tag name can contain a maximum of 50 characters. 

1. To delete an existing tag, select the tag by clicking on the checkbox. You can select multiple tags  upto  fifty in number to delete at once. To delete, follow this step:

   * Select the tags to be deleted > open the **[!UICONTROL Action]** drop-down menu > select **[!UICONTROL Delete]**.

1. You can only edit a single tag at a time. To edit a tag, follow this step:

   * Select the tag to edit > open the **[!UICONTROL Actions]**drop-down menu > click **[!UICONTROL Edit]**.

   The **[!UICONTROL Edit Tag]** dialogue box appears. Enter the new tag name and click **[!UICONTROL Save]**.

   If the tag name you entered already exists, Prime shows a warning message. No two tags with the same name can exist.

## Replace tags {#replacetags}

1. Select the tags you want to replace. You can select up to 50 tags at once. Open the **[!UICONTROL Actions]** drop-down menu and select **[!UICONTROL Replace.]**
1. The **[!UICONTROL Replace Tags]**dialogue box appears showing the selected tags.  

1. In the **[!UICONTROL Name for replaced tags]** option, enter the name of the new tag you wish to replace the selected tags with. You can either replace them with an existing tag from the drop-down or add a new tag.

   Semicolon or comma cannot be a part of the tag name.  Note that tags without semicolons and display of error messages while using such tags as part of some LO will not be handled for migration scenarios.

1. Click **[!UICONTROL Replace]**.

## Append tags {#appendtags}

In case of Append operation for tags, the new/existing tag will be appended to all the list of  LOs  and content groups which are associated with the selected tags.

1. Select the tags you want to append. You can select up to 50 tags at once. Open the Actions drop-down menu and select **[!UICONTROL Append.]**
1. The  **[!UICONTROL Append Tags]** dialogue box appears showing the selected tags.
1. You can append an additional tag to all the learning with the selected tags by entering the name of the **[!UICONTROL New Tag]** or from the drop-down list of the existing tags. The new tag will be appended to all the associated learning across Learning Manager.

   Semicolon or comma cannot be a part of the tag name. If used, Prime will show an error message. Note that tags without semicolons and display of error messages while using such tags as part of some LO will not be handled for migration scenarios.

1. Click **[!UICONTROL Append]**.

## Settings {#settings}

As an  Administrator  you can provide permission to the Author to create tags by clicking on the settings option.

![](assets/unknown-1.jpeg)

* When a user has permission to create tags and selects existing tags which are invalid at present,

  An error message appears suggesting that the selected tag is no more valid. New tags will get created by removing unsupported characters. In this case, Author should be able to see his old tags getting changed into new tags before he saves.

* If the user does not have the permissions to create new tags, an error message appears that the selected tag is no more valid. Authors can contact the Administrators to modify invalid tags.  

  Authors cannot create or save invalid tags. They can remove invalid tags and add any other existing valid tag and proceed.
