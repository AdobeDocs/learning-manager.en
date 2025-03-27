---
jcr-language: en_us
title: Customize learner homepage
description: An Administrator can customize the learner's home page and make it more modern, content driven, and personalized to a learner.
contentowner: saghosh
exl-id: 1551d240-fa07-4b7b-a06e-61b2bd3bff74
---
# Customize learner homepage

## Overview {#overview}

An Administrator can customize the learner's home page and make it more modern, content driven, and personalized to a learner.

The personalized approach offers a widget-based way of building a Learner Home page, which the admin of the organization can configure in the admin user interface in a WYSIWYG manner.

The experience is driven by a personalized training recommendations from an AI-driven algorithm that analyses third-party content for industry skills, incorporates peer activity, and learners' areas of interest using explicit and implicit data.

### Customize learner homepage

In this training, you will explore ways to customize the Learner Homepage.

[![button](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&sdid=4SC98Z83&mv=display&mv2=display#/course/8318825)

If you're unable to launch the training, write to <almacademy@adobe.com>.

## Configure the learner homepage {#configurethelearnerhomepage}

On the **Branding** > **Learner Homepage** page, an Administrator can customize the homepage experience of a learner, so that when the learner signs into the learner app, he/she sees a completely revamped look and feel.

Admins can set the UI (look and feel) from the Admin app (**Branding** > **Learner Home Page** tab).

Admins can switch to Immersive UI Widget view, customize widgets/features accordingly, and then enable the immersive UI. 

The **Learner Homepage** screen contains these sections:

## Immersive layout option {#immersivelayoutoption}

To view the layout of an immersive-driven page, enable the option **Immersive**. You can toggle this option in **Branding > General**.

In previous versions, the Learner Homepage options was in Settings.

Here are the options that you can set:

**Homepage Experience:** Enable either **Classic** or **Immersive**. If you choose Immersive, the following options appear:

* **Training Type:** Choose either **Industry** or **Custom Aligned**. Custom trainings are created in-house. Industry-aligned trainings include off-the-shelf content from third-party providers.

![](assets/select-homepage-experience.png)

*Set the home page experience by selecting Industry or Custom Aligned*

The option **Enable learner to explore Areas of Interest** is available to both Classic and Immersive experience.

<table>
 <tbody>
  <tr>
   <td>
    <p><b>If you choose Custom...</b></p></td>
   <td>
    <p><b>If you choose Industry Aligned...</b><br></p></td>
  </tr>
  <tr>
   <td>
    <p>You can choose at most one Internal and External active field.</p></td>
   <td>
    <p>You can choose at most five and at least one field. By default, the option <b>Profile </b>is selected.</p></td>
  </tr>
 </tbody>
</table>

If there are less than 1000 learners, the entire account is considered as a single scope. This is specifically for the Custom Training type. If the account has less than 1000 users, it considers the complete account as its scope.

>[!NOTE]
>
>The check-box **Explore skills** has been moved to Settings > General.

This will be enabled and grayed out if Immersive experience is chosen. This check-box will be enabled only for Classic experience.

![](assets/option-immersive.png)

*Learner homepage settings*

The immersive layout is the default for all new accounts. The layout is controlled by widgets that an Admin can enable or disable. Based on how the widgets are positioned, the same is reflected on the learner homepage.

Here are the widgets that you can enable/disable.

Using this, you can preview the Learner UI before the learner UI goes live.

For existing accounts, the option **Immersive** will be **OFF**. It is enabled for new account with Social and Gamification ON.

![](assets/immersive-layout-widgets.png)

*Preview the learner UI*

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Widget</b></p></td>
   <td>
    <p><b>Description</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Masthead</p></td>
   <td>
    <p><b>What is a Masthead and how do I customize the Learners Masthead? </b><br></p>
    <p>It's a welcome banner for learners. The banner can be an image or a video. You can target the masthead to specific user groups and a learner views the Masthead as soon as he/she lands on the homepage. A User Group may see multiple hero images or videos according to the target plan set by the Admin. </p>
    <p>Here's how an Administrator uploads a banner:</p>
    <ol>
     <li>On the left panel, click <b>Announcements</b>.<br></li>
     <li>On the upper-right corner of the page, click <b>Add</b>.</li>
     <li>From the <b>Type </b>drop-down list, choose <b>As Masthead</b>.</li>
     <li>Write a message that will feature in the masthead.</li>
     <li>Upload an image or a video.</li>
     <li>Choose target audience. Select a user group or training where the masthead will be displayed.</li>
     <li>Save the masthead announcement.</li>
    </ol></td>
  </tr>
  <tr>
   <td>
    <p>My Learning</p></td>
   <td>
    <p>Shows the Learning Objects, which are recently visited by the learner. </p></td>
  </tr>
  <tr>
   <td>
    <p>Calendar</p></td>
   <td>
    <p>Displays various upcoming Classroom and Virtual Classroom training trainings for the learners by month. Ones that the learner can enroll into or has already been enrolled into are displayed, including manager approved trainings. </p></td>
  </tr>
  <tr>
   <td>
    <p>Enrollments showing deadline</p></td>
   <td>
    <p>Displays enrollments that are overdue, have upcoming deadlines, or are on track. </p></td>
  </tr>
  <tr>
   <td>
    <p>Gamification</p></td>
   <td>
    <p>Displays the leaderboard based on learning activities.</p></td>
  </tr>
  <tr>
   <td>
    <p>Social Learning</p></td>
   <td>
    <p>Lists activities and posts by users who are in the same user scope as learner. </p></td>
  </tr>
  <tr>
   <td>
    <p>Recommended by organization</p></td>
   <td>
    <p>When enabled, this widget recommends trainings to specific user groups. Each User group can be targeted one or more trainings and the target plan would be based on a time frame. <br></p>
    <ul>
     <li>
      <p>Firstly, the Admin <a href="announcements.md#recommendation">creates an announcement</a> of type <b>As Recommendation</b> and then selects the requisite training and uses groups. A learner belonging to a user group will get to see the recommended training.</p></li>
     <li>
      <p>Secondly, the Admin can also decide if the recommendations kick in immediately or on a specified date.</p></li>
    </ul></td>
  </tr>
  <!--<tr>
   <td>
    <p>Recommendation based on area of interest</p></td>
   <td>
    <p>Displays Learning Objects based on the learner's chosen area of interest. The recommendation is driven by a Machine Learning algorithm.</p></td>
  </tr>-->
  <tr>
   <td>
    <p>Browse by catalog<br></p></td>
   <td>
    <p>Displays catalogs as tiles on the homepage. </p></td>
  </tr>
  <!--<tr>
   <td>
    <p>Recommendation based on peer activity<br></p></td>
   <td>
    <p>Displays training based on what a learner's peers are taking. This is again driven by a Machine Learning algorithm.</p></td>
  </tr>-->
 </tbody>
</table>

After you save the changes, the learner homepage reflects all the changes. 

When the learner signs in to the learner app via a browser, they can see the following immersive layout:

<table>
 <tbody>
  <tr>
   <td>
    <p><strong>Home page</strong></p><img src="assets/home-page1.png"></td>
   <td>
    <p><strong>My Learning List</strong></p><img src="assets/learning-list.jpg"></td>
   <td>
    <p><strong>View catalog</strong></p><img src="assets/catalog-new.jpg"></td>
  </tr>
 </tbody>
</table>

*View Immersive layout for various sections on the home page*

## Classic layout option {#classiclayoutoption}

The User Interface layout that has always existed till now, is now referred to as Classic Layout. When you choose this option, the learner homepage view reverts to the classic layout. 

![](assets/classic-layout.png)

*Preview the classic layout*

## Configure recommendation settings {#configurerecommendationsettings}

On **Branding** > **General**, you can configure recommendation scopes for internal and external learners, and enable learners choose skills on the learner homepage.

On the **General** page, you have the following options:

<table>
 <tbody>
  <tr>
   <td>
    <p>Organization Name</p></td>
   <td>
    <p>The name of the organization which the learner belongs to.</p></td>
  </tr>
  <tr>
   <td>
    <p>Subdomain</p></td>
   <td>
    <p>The subdomain of the organization.</p></td>
  </tr>
  <tr>
   <td>
    <p>Logo Styling</p></td>
   <td>
    <p>This is how your logo and company name will appear on Learning Manager.<br></p></td>
  </tr>
  <tr>
   <td>
    <p>Themes</p></td>
   <td>
    <p>The theme applied to Learning Manager.</p></td>
  </tr>
  <tr>
   <td>
    <p>Customize</p></td>
   <td>
    <p>Adobe Learning Manager allows you to customize your account to provide a richer experience to your users.<br></p></td>
  </tr>
  <tr>
   <td>
    <p>Learner Homepage</p></td>
   <td>
    <p>Choose either <b>Classic </b>or <b>Immersive</b>. If you choose Immersive, then other options appear.</p></td>
  </tr>
  <tr>
   <td>
    <p>Training type<br></p></td>
   <td>
    <p>Choose either <b>Custom </b>or <b>Industry Aligned</b>. If there are less than 1000 learners, the entire account is considered as a single scope. The recommendation is based on all learners.<br></p></td>
  </tr>
  <tr>
   <td>
    <p>Recommendation Scope Setting<br></p></td>
   <td>
    <p>Choose one or more active fields. For <b>Custom</b>, you can choose at most one active field. For <b>Industry Aligned</b>, you can choose at most five active fields.<br></p></td>
  </tr>
  <tr>
   <td>
    <p>Enable learner to explore Areas of Interest</p></td>
   <td>
    <p>Only for Classic experience. Choose <b>Yes </b>or <b>No</b>.<br></p></td>
  </tr>
  <tr>
   <td>
    <p>Prompt users to select Areas of Interest (Skills) <br></p></td>
   <td>
    <p>Only for immersive experience. Choose <b>Yes</b> or <b>No</b>. <br></p></td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>For the new account, the Learner Homepage, Training Type, and Recommendation Scope settings will not be visible.

