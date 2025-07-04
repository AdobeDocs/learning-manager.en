---
description: Learn how to create content to align with courses as self-paced content.
jcr-language: en_us
title: Content library
exl-id: cc19eca6-6b47-44b2-ad23-2d7ad8975f65
---
# Content library

Learn how to create content to align with courses as self-paced content.

## Content library {#contentlibrary}

Content is the building block of a course. Authors create a library of content that can be aligned to courses as self-paced content. Only authors have access to this content library.

## Supported content types {#supported}

You can upload both interactive and static content in the library.

The table below shows the type of interactive and static file types that you can upload to the library.

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Interactive content</b></p></td>
   <td>
    <p><b>Content type</b></p></td>
   <td>
    <p><b>Extensions</b></p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p></p>
    <ul>
     <li>SCORM 1.2</li>
     <li>SCORM 2004</li>
     <li>AICC</li>
     <li>TinCan</li>
    </ul>
    <p></p></td>
   <td>
    <p>zip</p></td>
  </tr>
  <tr>
   <td>
    <p><b>Static content</b></p></td>
   <td>
    <p><b>Content type</b></p></td>
   <td>
    <p><b>Extensions</b></p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>Video</p></td>
   <td>
    <p>mp4, wmv, 3gp, 3g2, 3gp2, asf, avi, f4v h264, mpe, mpeg, mpg, mpg2, m4v, mov, wmv</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>Audio</p></td>
   <td>
    <p>mp3, wav, aac, m4a, wma, vorbis, pcm, eac3, amr, ac3</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>PDF</p></td>
   <td>
    <p>pdf</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>MS PowerPoint</p></td>
   <td>
    <p>pptx, ppt</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>MS Word</p></td>
   <td>
    <p>docx, doc</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>MS Excel</p></td>
   <td>
    <p>xlsx, xls</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>HTML</p></td>
   <td>
    <p>zip file</p></td>
  </tr>
 </tbody>
</table>

## Add new content in the library {#addnewcontentinthelibrary}

**Authors** can add contents in ALM. There are two types of contents in ALM: **[!UICONTROL Content]** and **[!UICONTROL Quiz]**. To learn how to add contents see [Add static content](content-library.md#addstaticcontent) and [Create a quiz](content-library.md##createaquiz).

## Add static content {#addstaticcontent}

1. Select **[!UICONTROL Content Library]** on the left pane after you log in as **Author** and select **[!UICONTROL Add]**.

   Alternatively, you can select **[!UICONTROL Create Content]** from the **[!UICONTROL Getting Started]** page.

1. In the **[!UICONTROL Name]** field, type a name for the content that you want to upload.
1. In the **[!UICONTROL Description]** field, type the description for the content. Make sure that the description you want to enter is meaningful. The character limit is 400 characters.
1. To add the content, select **[!UICONTROL Add Content File]**, and upload your resource file. When you add content for multiple languages, you cannot combine static and interactive content in a single group. Either all your content in all the locales should be static, or all the content should be interactive.

   If you want to replace the content, you can replace a static content with a different static content. The same applies to interactive content.

1. In the **[!UICONTROL Duration]** field, you can optionally type the expected time a learner would spend in this module. The duration is in minutes.

   If the learner marks a course as complete, we calculate the learning time based on the specified duration. If learner consumes the content in the player, then the time spent in the player gets is added to learning time spent. If the actual content time is less than the specified duration, the player displays the content time as is. No changes are made in this case.

1. In the **[!UICONTROL Tags]** field, type the tags for the uploaded content so that your content becomes discoverable.

   An author can use these tags to search for the content while adding the content to the course.

### Add HTML5 file type in the content library

Authors can add HTML5 content as a .zip file to self-paced content. The .zip folder should contains an HTML file named `index.html`. If there are multiple HTML files, they should all be linked, with the main file named `index.html`. Learners can view the HTML5 content in the fluidic player. Author can add this HTML5 content to the self-paced module of a course and set the completion criteria. Authors can set the criteria for completing the HTML course in one of two ways: 

* The learner can mark it as complete themselves.
* It will be marked as complete once they launch the course.

To add the HTML file type(.zip) to the content library, follow these steps.

1. In the author app, select **[!UICONTROL Create Content]** on the home page.
1. In the **[!UICONTROL Content Library]** screen, select **[!UICONTROL Add]** > **[!UICONTROL Content]**.
1. Type the name and description of the content.
1. Select the **[!UICONTROL Add Content File]** option, then browse and select the HTML files (zipped as a folder).
1. Upon the content added, you can view the content on the **[!UICONTROL Content Library]** section.
1. Select the HTML content and then select **[!UICONTROL Edit]**.
1. Select any of the following options from the **[!UICONTROL Completion Criteria]** option.
   * **[!UICONTROL On Launching content]**: The course will be marked as complete automatically when the learner launches it.
   * **[!UICONTROL Learner marks complete]**: The learner has the option to mark the course as complete in the fluidic player.

   ![](assets/completion-criteria.png)
   _Completion criteria_

1. Select **[!UICONTROL Save]**.
1. Create a course by adding this content.  For more information, view [Creating, modify, and publish courses](/help/migrated/authors/feature-summary/courses.md). 

In the learner app, if an author selects selection criteria as **[!UICONTROL On Launching content]**, then the course will mark as complete when the learner launches it. When an author chooses **[!UICONTROL Learner marks complete]**, the learner will have the option to mark the course as complete.

![](assets/completion-criteria-fluidic-player.png)
 
_Learner marks complete_

### Versioning {#versioning}

The content library also maintains versioning of your uploaded contents. If you make any change in the content, for example a PowerPoint presentation, and re-upload the PPT in the library, the version number gets incremented by one. This helps you to track changes in your content.

## Add interactive content {#addinteractivecontent}

1. Select **[!UICONTROL Content Library]** on the left pane after you log in as **Author** and select **[!UICONTROL Add]**.

   Alternatively, you can select **[!UICONTROL Create Content]** from the **[!UICONTROL Getting Started]** page.

1. In the **[!UICONTROL Name]** field, type a name for the content that you want to upload.
1. In the **[!UICONTROL Description]** field, type the description for the content. 

   >[!NOTE]
   >
   >Make sure that the description you want to enter is meaningful. The character limit is 245 characters.

1. To add the content, select **[!UICONTROL Add Content File]**, and upload your resource file. When you add content for multiple languages, you cannot combine static and interactive content in a single group. Either all your content in all the locales should be static, or all the content should be interactive.

* [Supported file types](content-library.md#supported)

   The interactive content can be a SCORM, AICC, or a Captivate published project. The file must be a zip file.

   You can also add HTML content generated from Captivate, Presenter, or Presenter Video Express. 

1. Adobe Learning Manager supports captions for video content uploaded in Adobe Learning Manager. Now, authors can upload the file containing captions, along with the video file. 

   Then, the learners can view the captions during the playback of the video module.  

   The format supported is  [Web Video Text Tracks (webVTT)](https://www.w3.org/TR/webvtt1/).

   Caption support is available for video content uploaded in Content library in Adobe Learning Manager. 

   As an author, when you'll upload a video or audio content, you can also upload the VTT file that contains the captions.

   The subtitles then appear in the Fluidic Player. The captions are also compliant to [WCAG2.0 standards](https://www.w3.org/TR/WCAG20/). 

   When you add a video content to the library, you can also add the VTT file, which **must** be a valid file.

   ![](assets/webvtt.png)

   *Add a webvtt file*

   The uploaded VTT file corresponds to the existing version of the content. Thus uploaded webVTT file does not link to the older version of content.

   In case you are creating the content in different languages, you can upload a different webVTT file for each language. Learners will be able to see the captions corresponding to the language selected during playback.

   >[!NOTE]
   >
   >   One VTT file supports one language. To support multiple languages, upload multiple video files for each content language and then upload its respective VTT file for each video file.

   As an author, every time you change the content, video or audio, Adobe Learning Manager prompts you for a new vtt file.

   After you add this content to a course, and when you preview the course as learner, you can see the captions on the video.

   On the player, toggle the CC button on the Fluidic player to display or hide the captions.

   The same view is present in the **learner app** as well as in **Preview as learner**.

   When you **add, update, or delete** the vtt file, you receive a notification.
   WebVTT support is not available for:

   1. Video announcements.
   1. Video played within the eLearning content. This is driven by the content.
   1. Video uploaded in Social Learning.
   1. Video created in Adobe Learning Manager desktop app.
   1. Video content created using migration process.
   1. Video playback in mobile app in offline mode.

1. In the **[!UICONTROL Duration]** field, you can optionally enter the expected time a learner would spend in this module. The duration is in minutes.
1. In the **[!UICONTROL Tags]** field, enter the tags for the uploaded content so that your content becomes discoverable.

### Support for shared catalog

If a seller account shares a catalog that contains the courses, and the courses contain the modules, audio or video with the subtitles, the courses must behave the same in the purchaser account.

Module propagation should work correctly from Seller to Purchaser account. This may include - edit/delete/addition of the vtt file in the module.

Once you have uploaded the content, you can see a notification by clicking the Bell icon on top-right hand corner of the page. Each time you modify a content and re-upload it, you get a notification. If you make the changes, only you get the notification, not other authors.

## Create a quiz {#createaquiz}

Create assessments within Adobe Learning Manager with the new quiz creation tool on the Content Library page. The assessments created become part of the Content Library and can be added to a "public" folder for course reusability.

1. Select Content Library in the left panel.
1. In the upper-right corner of the screen, select **Add > Quiz**.
1. In the Create Quiz page, type the quiz's name and description.
1. In the Quiz Content section, select **Add quiz question**.
1. In the Quiz question dialog, select the type of question. There are three types of questions:
   * Multiple choice question
   * True or false
   * Fill in the blank
1. Enter the question and select the correct answer.
1. Set the points for the quiz.
1. If you want the question to be answered correctly to pass the quiz, select the checkbox **Compulsorily to answer correctly to pass the quiz**.
1. Select **Save and close**.
1. Enter the points to pass the quiz in the **Passing criteria** field.
1. If you want a learner to view a correct answer, enable the toggle **Show correct answers** to learners after the quiz.
1. If you want the questions and answers to appear randomly, enable the toggles:
   * Randomize question order
   * Randomize answer option order
1. Specify a folder to add the quiz to make the quiz available to all authors.
1. In the **Duration** field, specify the time the learner must spend on the quiz.
1. Specify a tag from the list of already created tags.
1. Add a logo and background to the quiz.
1. On the upper-right corner of the page, select **Publish**.

To add the quizzes in different language, follow the please steps:

1. To add the quiz for different languages, select the **Add New Language** tab, and choose the required languages. Using this approach, you can add multi-lingual support for your content.

   ![](assets/add-new-languagetab.png)

   *Add new language for a content*

1. Repeat the content upload process for the new languages.
1. If you want to remove a language, select the **[!UICONTROL Add New Language]** tab, and clear your selection.

   After you've made the changes, click **[!UICONTROL Save]**. In the library, the new content now is available for consumption.

The quiz is added to the **[!UICONTROL Content Library]**. Like any content in the Content Library, you can retire a quiz and then delete it.


## Add to folder {#add-folder}

After an Administrator creates the content folders, you, an author, can upload a content to a content folder, so that the content is only visible to you or a select group of authors in the account. You can also make the content public and make it visible to all authors in the account.

**Example usage**

For example, agencies want to maintain full control of the content and someone overlooking the content must have access to all content. At the same time, content creators in agencies must have access to their own content only, and in some cases, access to someone else's content.

Content library with existing content (i.e. content uploaded before configuring Content folders) gets defined as **Public folder**. This folder cannot be retired or deleted. Content that is part of Public folder is accessible to all types of authors. Once Content Folders are configured, standard authors and custom authors should select the folder where the content should be placed, while uploading new content.

>[!NOTE]
>
>Public folder and private folders are mutually exclusive. This means that content **cannot** be associated with Public folder and private folder at the same time. It can either be associated to Public folder, **or** it can be associated with one or more private folders at any point of time.

When you add a content, you can choose the folder where the content will reside. 

![](assets/add-to-content-folder.png)

*Add content to folder*

If you choose **Public**, the content will be visible to all authors. All content that existed in the account that are not part of any folder will in the public folder, by default.

Note that content folders are simply virtual compartments to link the content. In case one content is placed in two folders, it means that content file is always one single file but linked to multiple folders. Thus, in case the content is updated by the custom-author-1 having access to custom-folder-1, the same updated content will also reflect in custom-folder-2 accessed by custom-author-2.

In the Content Library, there are two options for managing the content folders:

**All Folders**

It's a list that displays all folders that were created in the account.

![](assets/list-of-all-folders.png)

*View all folders*

**All Authors**

It's a list that displays the authors who've created content and uploaded it in the library.

![](assets/list-of-all-authors.png)

*View all authors*

This is available **only** when an Administrator creates a new folder.

## Move content to folder {#movecontenttofolder}

To move a public folder content to any private folder, 

1. Select **Public** folder from the **All Folders** drop-down list.

   ![](assets/list-of-public-folders.png)

   *View all uploaded content*

1. Choose the content that you'd like to move it to a folder. Then click **[!UICONTROL Actions]** > **[!UICONTROL Organize Content]** > **[!UICONTROL Move Content to Folder]**. 

   ![](assets/move-content-to-folder.png)

   *Move a selected content to folder*

1. Choose the folder where you want to move the content to. Click **[!UICONTROL Move]**.

## Copy content to folder {#copycontenttofolder}

Copying a folder means that you'd be adding a tag to the folder. The copy operation will not create copies of content, but only add an association with specified folders.

![](assets/copy-content-to-folder.png)

*Copy a folder*

## Unlink folder {#unlinkfolder}

Unlinking means to remove the content from the selected folder.

Content can be unlinked from a specified folder **ONLY** if it is also associated with other folders. If content being unlinked, is only associated with one folder, then it is advisable to use MOVE operation instead.

>[!NOTE]
>
>The organize menu, under Actions, is disabled initially. To use that, you must first select a folder in the folder drop-down list.

![](assets/unlink-a-folder.png)

*Unlink a folder*

## Add content for different languages {#addcontentfordifferentlanguages}

1. To add the content for different languages, click the **Add New Language** tab, and choose the required languages. Using this approach, you can add multi-lingual support for your content.

   ![](assets/add-new-languagetab.png)

   *Add new language for a content*

1. Repeat the content upload process for the new languages.
1. If you want to remove a language, click the Add New Language tab, and clear your selection.

   After you've made the changes, click Save. In the library, the new content now is available for consumption.

## Set completion criteria {#setcompletioncriteria}

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Static content</b></p></td>
   <td>
    <p><b>Interactive content</b></p></td>
  </tr>
  <tr>
   <td>
    <p>You can only set the <b>Completion</b> Criteria for the content for the following options:</p>
    <ul>
     <li>On Launching content</li>
     <li>Based on the Minimum percent required</li>
    </ul></td>
   <td>
    <p>You can set both <b>Completion</b> and <b>Success</b> criteria for the content for the following options:</p>
    <ul>
     <li>On Launching content</li>
     <li>Based on the Minimum percent required</li>
     <li>Quiz passed or attempted options</li>
    </ul>
    <p><b>NOTE:</b> Only HTML content from Captivate, Presenter Video Express, or Presenter can be edited.</p></td>
  </tr>
 </tbody>
</table>

After you've added the content, you can modify the completion criteria for the content. 

In Adobe Learning Manager, badges and skill are awarded based on Success  and Completion. If the learner has completed a course but is not successful, then the learner does not receive the badge and skill corresponding to the LO.

For example, if you had used Adobe Captivate to create your course and set the learning parameters on the Preferences dialog, the same settings get migrated to Adobe Learning Manager in the Completion Criteria options.

In the Completion Criteria section, you can set the options mentioned below:

**On Launching Content:** If you enable this option, you define the completion criteria for the content when a learner opens the content.

**Based on the Minimum percent required:** Set a value as minimum percentage of consumption by your learner. For example, if you set the percentage as 50, your learner can consume 50% of the content and still meet the completion criteria.

**Quiz:** Choose one of the following criteria:

* **Quiz passed:** The status is reported as Complete only if a learner passes the quiz.
* **Quiz attempted:** The status is reported as Complete if learners attempt the quiz irrespective of whether they pass or fail the quiz.
* **Quiz passed or limit reached:** The status is reported as Complete if learners pass the quiz or have taken all the attempts. For example, if the number of attempts set in the course is two, and:

  * If learners take the first attempt and pass, then the status is reported as Complete and Passed.
  * If learners take the first attempt and fail, then the status is reported as Incomplete and Failed as the attempt limit is still not reached.
  * If learners retake the quiz and fail, the status is reported as Complete and Failed.
  * If learners attempt the quiz again and pass, the status is reported as Complete and Passed.

## Set success criteria {#setsuccesscriteria}

Similarly, you can define the success criteria for the course. A success criterion indicates a learner's performance as Passed or Failed. If you had created a course in Captivate, you can set the success criteria for the course in the Preferences dialog, as shown below:

For example, you have uploaded a module that has a quiz in it. Now, you have set the Completion Criteria for that module to On Launching content and Success Criteria to Quiz Passed.

If the learner has launched the course and failed the quiz, then the course will be marked as Completed, however the Success Criteria is only be met when the learner passes the quiz.

## Content filter options {#contentfilteroptions}

### Sort according to date {#sortaccordingtodate}

Arrange the content according to when the content was modified last. You can either sort the content in ascending or descending order.

![](assets/according-to-date.png)

*Sort content by date*

### Sort according to usage {#sortaccordingtousage}

Arrange the content according to whether the content is being used in any course. In the Type drop-down, choose In Use or Unused.

![](assets/according-to-usage.png)

*Sort content by usage*

## Add Content unique id and expiry date

### What is Content unique ID

The Content unique ID is a unique code given to each content item in Adobe Learning Manager. It helps administrators and authors find and manage content easily, especially when updating or moving it between systems. This Content unique ID is also useful for integrating content with other tools like HR or compliance systems. The same Content unique ID is used across all language versions, so everything stays consistent for learners. 

* Content unique IDs must be unique across all content.
* Content unique ID cannot include spaces or special characters.
* If a duplicate Content unique ID is entered, an error will appear during creation.

### What is Expiry Date

The Expiry Date marks content that may be outdated or no longer needed. Even after the expiry date, the content stays available, but it reminds authors and administrators to check and update it if needed. Based on settings, expired content can be removed from new enrollments or archived. Like the Content unique ID, the Expiry Date works the same way for all language versions, helping keep content clean and up to date for everyone.

* Content remains available even after expiry.
* A warning appears if a past date is selected.
* The expiry field accepts any date between 1990 and 2037.

This helps organizations maintain content relevance without accidentally removing published items.

The Content unique ID and Expiry Date apply to all language versions of a content group, ensuring a consistent experience for all users, no matter the language. Authors can use the Content unique ID to quickly search for and find specific content, making it easier to manage and update training materials.

The **[!UICONTROL Training report]** now includes two new columns: **[!UICONTROL Content Expiry Date (UTC TimeZone)]** and **[!UICONTROL Content Unique ID]**, to track Content unique ID and Expiry Date. These fields can be added via UI or migration, and administrator can track them centrally through training reports.

### Add Content unique ID and Expiry Date 

Authors can add a Content unique ID and set an Expiry Date date when creating content. 

To add Content unique ID and Expiry Date:

1. Log in as an Author.
2. Select **[!UICONTROL Create Content]** or select **[!UICONTROL Content Library]** in the left panel.

   ![](assets/create-content.png)
   _Select Create Content in home page_

3. Select **[!UICONTROL Add]** and then select **[!UICONTROL Content]** in author home page.

   ![](assets/add-content.PNG) 
   _Select Add content in the Content Library_ 

4. Type the **[!UICONTROL Name]** and **[!UICONTROL Description]**

5. Select the content from the **[!UICONTROL Add Content File]** option 
6. Select the folder from **[!UICONTROL Add to Folder]** option to add the content to folder.
 
   ![](assets/add-a-new-content.png)
   _Add new content_

7. Type the ID of the uploaded content in the **[!UICONTROL Content unique ID]** field. The ID must be unique and follow the correct naming guidelines. The ID must not contain non-ASCII characters or spaces. If you enter a duplicate ID, an error message is displays.
 
   ![](assets/content-unique-id.png)
   _Field for entering a unique alphanumeric Content ID_

8. Select the Expiry Date for the content. This date does not affect content availability or learner access. You can choose any date between 1990 and 2037. If a past date is selected, a warning appears, but the content can still be published.
9. Select **[!UICONTROL Save]**. 
The uploaded content now appears in the **[!UICONTROL Content Library]**.

### Set Content unique ID and Expiry Date for languages

The Content Unique ID and Expiry Date are defined at the content group level, meaning they are set once and automatically apply to all language versions of the content.

1. Select the content in the **[!UICONTROL Content Library]**.
2. Select **[!UICONTROL Edit]**.
3. Select **[!UICONTROL Add New Language]**.
4. Select any language from the list.
5. Select **[!UICONTROL Save]**. 
The Content unique ID and Expiry Date are now displayed on the language-specific version of the content, such as German in this example.

### Search using the Content unique ID

You can use the Content Unique ID to search for content across all language versions, making it easier to locate and manage specific items. Additionally, both the Content Unique ID and Expiry Date are included in training reports for consistent tracking and reporting.

1. Launch the **[!UICONTROL Content Library]**.
2. Type the **[!UICONTROL Content unique ID]** in the search bar.
   
   ![](assets/search-unique-id.png)
   _Searching content using the Content unique ID_
3. Select the content to view or edit it.

### Content migration support 

When migrating content, you can include the **expiryDate** and **uniqueContentId** in the module_version.csv file. This ensures continuity of metadata when moving content between systems.

### Reporting changes

Two new columns, Content unique ID and Content Expiry Date, are now available in the Training Report. These fields help administrators monitor content expiration dates more effectively.

## Retire content {#retirecontent}

Once you publish a content, you cannot delete the content. You must retire the content first. When you mark a content as Retired, the content is no longer visible to learners. The content also moves to the **[!UICONTROL Retired]** section. 

To retire content, follow these steps:

* In **[!UICONTROL Content library]**, select the content you want to retire.
* Select **[!UICONTROL Action]** and then select **[!UICONTROL Retire]**.

Any content that is being used in any learning objects do not get affected. Learners can still continue to access the content.

>[!NOTE]
>
>You can also add content from the **[!UICONTROL Retired]** section, navigate to **[!UICONTROL Content Library]** and then select **[!UICONTROL Retired]**. Select **[!UICONTROL Add Content]**. For more details, see [Add static content](content-library.md#addstaticcontent).


## Search for content {#searchforcontent}

In the Content Library, you can search for a content by choosing either the name of the content or the tags associated with the content.

On the Search bar, enter the name of a course or a tag, and you can see the recommendations.

<!--![](assets/search-bar.png)-->

## Republish retired content {#republishretiredcontent}

Once you retire a content, you can republish the content and make the content appear in the Published list. For example, if you have retired version 1 of a content and want to replace that with version 2, you can move version1.pptx, for example, to the Published list, and update the file with version2.pptx. The new file becomes available for consumption in various courses.

To republish the retired content,

1. Navigate to the **Retired** tab and select the content that you want to republish.
1. Select **Action** > **Republish**.

The content now appears in the Published list.

## Update the content

Authors can update the content in the published course. 
To update the content:

1. Login as an author.
2. Select **[!UICONTROL Content Library]**.
3. Search for the content and select **[!UICONTROL Edit]**.
4. Remove older content and upload new file and publish.

This will help learners get the latest version of the content. 

Check out this [blog](https://elearning.adobe.com/2024/06/how-to-update-the-content-in-the-course/) for more information. 

### Content version control for learners who have completed a course

Adobe Learning Manager now provides authors with clearer options to manage content updates. Authors can update the content already available in a course. When a new version is added, the version number appears next to the content.

When an administrator visits a course that has updated content, they will see an Update button next to the new version. Administrators will also see clear update options to choose how the new content version is applied to learners.

|Learner state |Update Now |Update Eventually |Update Not Started |
|---|---|---|---|
|Not Enrolled |V2 |V2 |V2 |
|Yet to Start |V2 |V2 |V2 |
|In Progress |V2 * |V1 → V2 * |V1 |
|Completed |V2 * |V2 * |V1 (preserved) |

(*) Indicates that the module will be reset when the version is updated.

With Update Not Started, learners who have already completed the course continue to see the original content version (V1). This prevents unexpected playback issues and ensures a consistent experience for learners who revisit completed courses.

### Content update options

When an admin clicks **[!UICONTROL Update]**, they can choose from the following options:

* **[!UICONTROL Update all Learners now]**: Apply the content update immediately for all learners. Not Started, In Progress, and Completed learners move to the new version right away.
* **[!UICONTROL Update all Learners eventually]**: Apply the update for all learners in phases. Not Started and Completed learners receive the new version now. In Progress learners get the update after they complete the current version.
* **[!UICONTROL Update only not started Learners]**: Apply the update only to learners who have not yet started the course. In Progress and Completed learners remain on the original version.

![](assets/version-control-options.png)
_Content update options available in Update settings_


## Delete content {#deletecontent}

After you have retired a content, you can delete it.

* Navigate to the Retired tab and select the content you want to delete.
* Select Action > Delete.

Note that existing courses that use the content, which are deleted from the content library, will continue to use the content.

## Frequently Asked Questions {#frequentlyaskedquestions}

+++ How to upload a SCORM content in Adobe Learning Manager?

Create a SCORM-compliant eLearning course in any tool, such as, Adobe Captivate, and publish the content as a zip file. Then in Adobe Learning Manager, upload the zip file in the catalog, and set the completion and success criteria.
+++

+++How do I upload a new version of the same content to Adobe Learning Manager?

In Adobe Learning Manager, the content library also maintains versions of your uploaded contents. If you make any change in the content, for example, a PowerPoint presentation, and re-upload the presentation in the library, the version number gets incremented by one. This helps you to track changes in your content. A new version of the content can be applied to all Learning Objects simultaneously or you can apply individual updates for each course.
+++

+++How to edit the details of a course in a different language?
After adding a language/languages, as described in an earlier section, click each language tab, and then add/edit the course information. 

<!--![](assets/edit-course-language.png)--->
+++
