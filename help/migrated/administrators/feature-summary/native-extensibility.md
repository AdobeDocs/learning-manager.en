---
title: Native extensibility
description: Set up custom experiences within the native version of Adobe Learning Manager, allowing you not to use headless for less complicated cases.
---
# Native extensibility

You can set up custom experiences within the native version of Adobe Learning Manager, allowing you not to use headless for less complicated cases. You can also create custom apps and place them at various points in the native version of the learner, manager, admin, author, or instructor workflows.

Adobe Learning Manager supports 15 invocation points across Admin, Author, Learner, Manager, and Instructor App.

## Create an extension

1. As an Admin, in the left panel, select **[!UICONTROL Native Extensions]**.
1. Select Add an extension.
1. Type the name of the extension in the **[!UICONTROL Name]** field.
1. Type the description of the extension in the **[!UICONTROL Description]** field.
1. Select an invocation point. An invocation point is any location in Adobe Learning Manager where a link or button can be inserted on a custom app. The following invocation points are available:

   For this example, select **[!UICONTROL Admin]**, **[!UICONTROL Author: Course]**, **[!UICONTROL Learning Path]** - **[!UICONTROL Instances]** - **[!UICONTROL Instance row]**.

   ![extension image](assets/list-native-extensions.png)
   *Select invocation point*

1. Type the extension label that will appear on the UI in the **[!UICONTROL Extension Label]** field.
1. Type the URL where you want to host the extension in the **[!UICONTROL URL]** field.
1. In the Open In dropdown, select whether to launch the extension in a modal or in a new tab.
1. Select the size of the modal. The options are available if you've selected In-app modal in the previous step.

   To maintain the accessibility inside the popup, the extension app needs to be sent to the event once they are on the last focusable element on their website, and then the user selects the TAB key. This is needed to keep the focus inside the popup to support accessibility.

   ```
   window.parent.postMessage({*}

   { type: 'ALM_EXTENSION_APP', eventType: 'trapFocusInModal' }

   ,{}'');
   ```

1. Set the scope of the extension. The following scopes are available:

   * **[!UICONTROL All Courses, Learning Paths and Certifications]**: This extension will be enabled for all Courses, Learning Paths and Certifications. Along with Admins, Authors can disable it for some Courses, Learning Paths and Certifications.
   * **[!UICONTROL Selected Courses, Learning Paths and Certifications]**: This extension will be disabled for all Courses, Learning Paths and Certifications. Along with Admins, Authors can enable it for some Courses, Learning Paths and Certifications.

1. Select the **[!UICONTROL Activate]** toggle to make the extension active. Once active, the extension will appear on the specified invocation point according to the scope.
1. Select **[!UICONTROL Save]** in the upper-right corner of the page to create the extension.

## Access the extension as Administrator

1. As an Admin, select **[!UICONTROL Learning Paths]** in the left toolbar.
1. Select a course > **[!UICONTROL View Learning Path]**.
1. Select **[!UICONTROL Instances]** in the left panel.
1. Select **[!UICONTROL More]** in the Instances section. The extension appears in the Instances section.

   ![instances image](assets/instances-extension.png)
   *Select the extension*

   When you select the extension, the extension appears in the modal.

## Access the extension as Author

1. As an Admin, select **[!UICONTROL Learning Paths]** in the left toolbar.
1. Select a course > **[!UICONTROL View Learning Path]**.
1. Select **[!UICONTROL Instances]** in the left panel.
1. Select **[!UICONTROL More]** in the Instances section. The extension appears in the Instances section.

   ![instances image](assets/instances-extension.png)
   *Access extension as an author*

   When you select the extension, the extension appears in the modal.

## View all extensions

As an Admin, you can view all extensions on the Native Extensions page. To see the list, select Native Extensions in the left panel of the app.

![view extensions image](assets/view-extensions.png)
*View all extensions*

## Enable or disable an extension

As an Author, on the Settings page of a Course, you can enable or disable an extension for a Course, Certification, or a Learning Path.

![activate extension image](assets/activate-extension.png)
*Activate an extension*

## Share an Access key

You must share the Access key if you are configuring an enrollment extension.

This is very important because if this key is not generated and shared across, the authentication for the enrollment will fail, and learners will not be able to enroll themselves in the courses.

Access key must be shared for enrolling in course or Learning Path and certificates.

In the Settings tab, generate the key.

![share key image](assets/share-extension.png)
*Share the access key*

## Download extension report

There are two ways to download this report.

**Extension configuration report**

1. In the Native Extensions page, select **[!UICONTROL Extension Configuration Report]**.

   ![report image](assets/extension-config-report.png)
   *Download extension report*

   The report gets generated. 

1. Select OK.

   ![generating report image](assets/generating-report.png)
   *Generating the report*

   The report contains the following fields:

   * Extension Name           
   * Invocation Point           
   * Label   
   * Open in URL     
   * Scope  
   * Activate
   * LO Unique ID   
   * Training Id       
   * Training Type   
   * Training Name

**Reports page**

1. In **[!UICONTROL Reports]** > **[!UICONTROL Custom Reports]**, select **[!UICONTROL Extension Configuration Report]**.

   ![reports page image](assets/extension-report-page.png)
   *Download teh report from Reports page*

The state must be in the range **0 - 4294967295**, while configuring the enrollment state.
