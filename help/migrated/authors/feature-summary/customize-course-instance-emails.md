---
description: Learn how authors customize course-level and instance-level emails in Email Builder with an administrator layout, and fix common issues
jcr-language: en_us
title: Customize course and instance emails in Email Builder
exl-id: 06499e3f-0610-4983-83f2-3e8b578fc8bf
---

## Customize course and instance emails in Email Builder

Customize course-level and instance-level emails in Adobe Learning Manager with Email Builder and a layout that your administrator provides.

As an author, you can customize emails for a course or for a specific instance of a course. Both procedures start from a layout that your administrator provides.

### Customize a course-level email

1. Open the course.
2. Select **Email Templates**.
3. Select **Course email layout**.
4. Customize the email content. To set fonts, colors, rows, and buttons.
5. Save the template.
6. Publish the course.

### Customize an instance-level email

Use an instance-level email when different cohorts need different messages. You manage these cohorts through course instances.

1. Open the course instance.
2. Open **Email Builder**.
3. Select an available layout, or inherit the layout that the instance already uses.
4. Update the message content.
5. Save the template.

>[!NOTE]
>
>When both exist, instance-level emails override course-level templates.

### Use the Title variable and an image for email headers 

Use the Title variable with an Image component to build the email header instead of the Banner component. The Banner component's image doesn't appear in some email clients, such as Outlook. 

The Title variable, EmailTitle, works like the existing ChannelName variable. Each email has its own default title value. 

To add a title header: 

1. Add an Image component for the header image. 
2. Add a Text component and insert the title variable from the variables dropdown in the component's configuration pane. 
3. Center-align the Text component. In the global layout, place it in the top header. 

Individual emails use the header from the global layout by default. In an individual email, you can edit the Text component to: 

1. Replace the variable with custom text 
2. Add text before or after the variable and keep `EmailTitle` 

If you add an image to the Banner component, Email Builder shows a warning that the image might not appear correctly in some email clients. The warning suggests using an Image component and the title variable instead.  

### Troubleshooting

**You can't select a layout.** 
Layout inheritance depends on the parent layouts that are available. Ask your administrator to create an account layout.

**Your email doesn't show recent layout changes.** 
The template might be unlinked from its layout. Unlinked templates no longer receive layout updates.

**Learners in an instance receive a different email than the course email.** 
Instance-level emails override course-level templates. Review the instance-level template.

**You don't see Email Builder for your course or instance emails.** 
Adobe enables Email Builder in phases. Ask your administrator to confirm that Email Builder is enabled for your account.

**Your banner image doesn't appear in the email.** 
Some email clients, such as Outlook, don't display the Banner component's image. Remove the Banner component, add an Image component, and add a Text component that uses the title variable. 
