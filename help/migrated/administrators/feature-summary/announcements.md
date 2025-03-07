---
jcr-language: en_us
title: Announcements
description: An announcement is a multimedia message (text, image or video) that an Administrator broadcasts to a defined set of users.
exl-id: 313ac2c6-05c0-4941-8d71-9c664099bb5c
---
# Announcements

An announcement is a multimedia message (text, image or video) that an Administrator broadcasts to a defined set of users.

Administrator can broadcast announcements to learners informing them about the occurrence of an event or an activity. Announcement can be a combination of text, images, or videos. You can link learning objects like courses, learning programs and certifications to an announcement.

There are four types of announcements:

* Notification
* Masthead
* Recommendation
* Email

## Notification {#notification}

1. As an Administrator user, click Announcements at the left pane.
1. Click Add at the upper-right corner of the page.
1. From the Type drop-down list, select the option **As Notification**.

![](assets/as-notofocation.png)

*Customize the notification*

1. In the Message field, add the message for the announcement. You can also add a URL for announcements here. However, you must add the URL in the HTML form. 

   For example,  `code <a href="http://www.w3schools.com" target="_blank">Visit W3Schools</a>.`

   When you specify the target as blank, then when a user clicks the announcement URL, the link opens in a new tab. If you do not specify the target, the link opens in the same browser.

1. Optionally add attachments such as images or video files for the announcement.
1. Choose the target user groups or the target learning objects. You can choose only one of them for an announcement.

   Start typing the user group name in the text box and choose from the drop-down list. Similarly, choose the training by typing the object name in the text-box.

1. Click Advanced Settings from the dialog box. You can perform the following actions:

   * Make this announcement a sticky announcement by selecting the Enable Sticky Announcement checkbox.
   * Select the delivery time for the announcement.

1. Select **[!UICONTROL On a date]** if you want to schedule announcement for a later date and click the text area adjacent to it. A calendar pop-up appears, from which you can choose the start date. Choose the end date by following the same steps.
1. Click **[!UICONTROL Save]**.
1. In Drafts tab, click settings icon  adjacent to an announcement and click send.

If the multimedia attachment is of large size, it may take time to upload. After you click Save, you would receive a pop-up with a message as your upload is being processed. You will receive a notification after the attachment is uploaded successfully.

## Masthead {#masthead}

When you choose this option, any media file that you choose features as a masthead on the Learner homepage. The masthead acts as a call to action for the learners it is intended for.

Admins can add alt text for all mastheads to improve accessibility for learners. This allows learners with special needs to use screen readers to read the alt text and understand the image. You can select multiple languages and provide alt text for each language. Make sure to add the alt text in the respective languages.

To add the masthead, follow these steps:

1. Log in as an **[!UICONTROL Admin]**.
2. Select **[!UICONTROL Announcements]** > **[!UICONTROL Add]**.
3. Select **[!UICONTROL As Masthead]** from the Type dropdown menu.
 
   ![](assets/announcement.png)
   _Create an announcement_

4. Select the language and upload the image.

   >[!NOTE]
   >
   >You can select multiple languages and provide alt text for each language. Make sure to add the alt text in the respective languages.

5. Enter the suitable text in the **[!UICONTROL Alt Text]** field.
6. In the **[!UICONTROL Action Button]** field, add a URL to redirect learners when they click the button on the masthead.
7. Select the target user groups or the target learning objects. You can choose only one of them for an announcement.
8. In the **[!UICONTROL Advanced Settings]** section, you have the following options:

   * Select **[!UICONTROL Immediately]** if you want the announcement to be posted right then.
   * Select **[!UICONTROL Never]** if you do not want your announcement to expire.
   * Select the **[!UICONTROL Start]** and **[!UICONTROL End]** dates for the announcement.
9. Select Save and publish the announcement.

**Is there a limit on the number of live Masthead Announcements?**

You will only see the most recent 10 Masthead announcements.

## Recommendation {#recommendation}

When you choose this option, any training that you choose gets recommended to specified user groups. The recommendations are driven by a Machine learning algorithm.

![](assets/recommendation-announcement.png)

*Select recommended training to be displayed to a learner*

1. Choose the training that you'd like to recommend to learners. You can add upto 10 trainings.

   Learners will see only the unenrolled trainings in Recommendation by Organization. Based on the catalog visibility, the learner has access to see the training.

1. Choose the target user groups or the target learning objects. You can choose only one of them for an announcement.

   Start typing the user group name in the text box and choose from the drop-down list. Similarly, choose the training by typing the object name in the text-box.

1. In the Advanced Settings section, you have the following options:

   * Click **[!UICONTROL Immediately]** if you want the announcement to be posted right then.
   * Click **[!UICONTROL Never]** if you do not want your announcement to expire.
   * Select the **[!UICONTROL Start]** and **[!UICONTROL End]** dates for the announcement.

   <!--![](assets/advanced-settings.png)-->

When you click **[!UICONTROL Save]**, you can either publish the announcement right away or publish it later. The announcement, till then, will be in a draft state.

* Mastheads/Recommendations do not trigger any notifications.
* Mastheads/Recommendations do not appear in announcements report.

## Draft, scheduled and sent list {#draftscheduledandsentlist}

In Administrator login, you can view all the announcements in three tabs such as Drafts, Scheduled and Sent.

<!--![](assets/three-tabs-announcement1.png)-->

### Draft {#draft}

In Drafts tab, you can view all the announcements that are created by an Administrator but not yet broadcast or not yet scheduled for broadcast.

By default, all the announcements are set for immediate broadcast. If you choose settings>send option for an un-scheduled announcement, then it is broadcast immediately. To schedule an announcement broadcast , you have to choose the start and end date in Advanced settings.

### Scheduled {#scheduled}

In Scheduled tab, you can view all the announcements that are scheduled for broadcast at a later date.

### Sent {#sent}

In Sent tab, you can view all the announcements that are broadcast already.

## As Email

Use this option to send targeted ad-hoc emails to learners of a selected user group or to learners enrolled in specific training.

![Admin creates an email announcement](assets/email-announcement-admin.png)

*Wend targeted ad-hoc emails to learners*

*Admin creates an email announcement*

1. Select **[!UICONTROL Type as Email]**.
1. Enter the email subject and the message body.
1. In the Target section, you can either:

   * Select a user group OR
   * Select a course. If the course has multiple instances, you can select the required instance.

1. Click **[!UICONTROL Save]**.
