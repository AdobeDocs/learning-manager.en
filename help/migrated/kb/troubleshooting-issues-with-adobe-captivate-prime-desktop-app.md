---
description: This document contains basic troubleshooting tips to solve some of the typical problems that encounter while installing and using Adobe Learning Manager desktop application.
jcr-language: en_us
title: Troubleshooting issues with Adobe Learning Manager desktop app
contentowner: kuppan
---
This document contains basic troubleshooting tips to solve some of the typical problems that encounter while installing and using Adobe Learning Manager desktop application.

# I am unable to do the following {#iamunabletodothefollowing}

+++I am unable to download Adobe Learning Manager desktop application

1. Check your Internet connection and firewall settings.
1. In Social Learning, click **New Post** to create a post. If you do not have a board, create a board first.&nbsp;
1. Click any one of the following post button options that appear to create content like Screen Shot, Record Audio, Record Video, Learning Manager Gallery. You are redirected to Adobe Learning Manager desktop application page from where you can download Adobe Learning Manager desktop application for your desktop.
1. You require a valid Adobe Learning Manager account that has Social Learning enabled by your administrator. Your administrator might have also disabled downloads through the web browser. Contact your Adobe Learning Manager administrator for more information on downloading the Adobe Learning Manager desktop app.

+++

+++I am unable to install Adobe Learning Manager desktop application

1. Make sure that your system meets the minimum system requirements. See [System requirements for Adobe Learning Manager App for desktop](../learners/adobe-captivate-prime-app-for-desktop/adobe-captivate-prime-desktop-app-system-requirements.md).
1. Clean up any previous installation of Adobe Learning Manager desktop application. For more information, see&nbsp; [How to clean previous installations](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#HowtocleanuppreviousinstallationsofAdobeCaptivatePrimedesktopapp) for more information.
1. For errors during installation process, see [How to find application logs](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtofindapplicationlogs). Contact your Adobe Learning Manager desktop application administrator for more help.

+++

+++I am unable to launch Adobe Learning Manager desktop application

1. Make sure that Adobe Learning Manager desktop application is downloaded and installed.
1. In Social Learning, click **New Post** (if you do not have a board, then create a board). Click any one of the following post button options that appear – Take a Screenshot, Audio Recording, Video Recording, Adobe Learning Manager Gallery. You are redirected to a page from where you can launch Adobe Learning Manager desktop application.
1. In case the app does not launch, you can also launch it from the Start Menu on Windows, or from Launchpad on Mac OS X.

+++

+++I am unable to log in to my account in Adobe Learning Manager desktop application

1. Make sure that you are connected to the Internet and your firewall settings do not block Adobe Learning Manager desktop application.
1. Make sure that you have a valid Adobe Learning Manager learner account with Social Learning enabled.
1. If you are still unable to log in, quit and relaunch the Adobe Learning Manager desktop application, and then retry.
1. For more Help, contact your Adobe Learning Manager administrator.

+++

+++I am unable to see my webcam / microphone listed in Adobe Learning Manager desktop application

1. Ensure that your webcam / microphone is properly plugged-in to the system and is functioning properly.
1. Ensure that you have installed the latest drivers for your webcam / microphone. Some devices do not function properly without dedicated drivers.
1. Reset application preferences, and then relaunch Adobe Learning Manager desktop application and retry. For more information, see [How to reset application preferences](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtoresetapplicationpreferences).
1. If you are on Mac OS X Mojave 10.14, grant permissions to Adobe Learning Manager desktop application to access your webcam / microphone. For more information, see [How to set webcam / microphone permissions on OSX Mojave](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#HowtosetwebcammicrophonepermissionsonMacOSXMojave).

+++

+++I am unable to publish my posts from Adobe Learning Manager desktop application

1. Make sure that you have a valid Adobe Learning Manager learner account with Social Learning enabled by your Adobe Learning Manager administrator.
1. Reset application preferences, and then relaunch Adobe Learning Manager desktop application and retry. For more info, see [How to reset application preferences](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtoresetapplicationpreferences).
1. For errors while publishing, enable advanced logging. For more information, see [How to enable advanced logging](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtoenableadvancedlogging), restart Adobe Learning Manager desktop application, redo the above steps that cause the error. Send the latest application logs to your Adobe Learning Manager administrator for Help. For more information, see [How to find application logs](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtofindapplicationlogs).****

+++

+++I am unable to see or open my older projects

1. You can only see projects created with your Adobe Learning Manager account, on the same computer on which they were created.
1. Reset application preferences, and then relaunch Adobe Learning Manager desktop application and retry. For Help, see [How to reset application preferences](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtoresetapplicationpreferences).
1. For errors while opening projects, enable advanced logging. For more information, see [How to enable advanced logging](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtoenableadvancedlogging). Restart Adobe Learning Manager desktop application and redo the steps that cause the error. Send the latest application logs to your Adobe Learning Manager administrator for Help. For more information, see [How to find application logs](troubleshooting-issues-with-adobe-captivate-prime-desktop-app.md#Howtofindapplicationlogs).****

+++

# How to reset application preferences? {#howtoresetapplicationpreferences}

### Windows {#windows}

1. To open the Run dialog, press the&nbsp;**Windows + R**&nbsp;keys.
1. Type “**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**” (without quotes) and press Enter.
1. Delete the files named **preferences.json** and **preferences.xml**.

### Mac OS X {#macosx}

1. Open Finder.
1. To open the **Go To** folder dialog, Press&nbsp;**Cmd + Shift + G**&nbsp;keys.
1. Type “**~/Library/Application Support/Adobe/Learning Manager 1.0**” (without quotes) and press Enter.
1. Delete the files named **preferences.json** and **preferences.xml**.

# How to find application logs? {#howtofindapplicationlogs}

### Windows {#application-logs}

1. To open the Run dialog box, Press&nbsp;**Windows + R**&nbsp;keys.
1. Type “**%TEMP%\\elthor**” (without quotes) and press Enter.
1. Sort the folders by the **Date Modified** and open the most recent folder. This folder contains the latest application logs.

### Mac OS X {#MacOSX-1}

1. Open **Finder**.
1. To open the **Go To Folder** dialog box, press&nbsp;**Cmd + Shift + G**&nbsp;keys.
1. Type “**/var/folders**” (without quotes) and press Enter.
1. Search for “**elthor**” in the search bar and open the folder.
1. Sort the folders by the **Date Modified **and open the most recent folder. This folder contains the latest application logs.

# How to enable advanced logging? {#howtoenableadvancedlogging}

### Windows {#Windows-1}

1. To open the Run dialog, press&nbsp;**Windows key + R**.****
1. Type “**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**” (without quotes) and press Enter.****
1. Take a backup of file **preferences.json**, and then open it in a text editor.****
1. Search for the key **debugMode** and change the value property of this key to “**true**” (without quotes).

### Mac OS X {#MacOSX-2}

1. Open Finder.
1. To open the **Go To Folder** dialog, press&nbsp;**Cmd + Shift + G**.
1. Type “**~/Library/Application Support/Adobe/Learning Manager 1.0**” (without quotes) and press Enter.
1. Take a backup of file **preferences.json**, and then open it in a text editor.
1. Search for the key **debugMode** and change the value property of this key to “**true**” (without quotes)

# How to set webcam / microphone permissions on Mac OS X Mojave? {#howtosetwebcammicrophonepermissionsonmacosxmojave}

1. Click **System Preferences** icon in Dock.
1. Click **Security & Privacy** > **Privacy.**
1. Click **Webcam and Microphone options** and ensure that Adobe Learning Manager check box is selected. If you do not see Adobe Learning Manager listed, first install and launch Adobe Learning Manager desktop application.

# How to clean up Adobe Learning Manager for desktop updates cache? {#howtocleanupadobecaptivateprimefordesktopupdatescache}

### Windows {#clean-previous-installation}

1. To open the Run dialog, press&nbsp;**Windows key + R**.
1. Type “**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**” (without quotes) and press Enter.
1. Delete the folder named **updates**.

### Mac OS X {#MacOSX-3}

1. Open Finder.
1. To open the **Go To Folder** dialog, press&nbsp;**Cmd + Shift + G**.
1. Type “**~/Library/Application Support/Adobe/Learning Manager 1.0**” (without quotes) and press Enter.
1. Delete the folder named **updates**.

# How to clean up Adobe Learning Manager for desktop temp folder? {#howtocleanupadobecaptivateprimefordesktoptempfolder}

### Windows {##clean-previous-installation-1}

1. To open the Run dialog, Press&nbsp;**Windows key + R**.
1. Type “**%TEMP%**” (without quotes) and press Enter.
1. Delete the folder named “**elthor**”.

### Mac OS X {#MacOSX-4}

1. Open Finder.****
1. To open the **Go To Folder** dialog, press&nbsp;**Cmd + Shift + G**&nbsp;keys.
1. Type “**/var/folders**” (without quotes) and press Enter.
1. Search for “**elthor**” in the search bar.
1. Delete the folder named “**elthor**”.

# How to locate Adobe Learning Manager for desktop projects? {#howtolocateadobecaptivateprimefordesktopprojects}

### Windows {#Windows-2}

1. To open the Run dialog, press&nbsp;**Windows key + R**.
1. Type “**~/Documents/My Adobe Learning Manager Projects**” (without quotes) and press Enter.
1. You or your Adobe Learning Manager administrator might have changed the default projects folder location. Contact your administrator for more help to locate and clean up projects.

### Mac OS X {#MacOSX-5}

1. Open Finder.
1. To open the **Go To Folder** dialog, press&nbsp;**Cmd + Shift + G**&nbsp;keys.
1. Type “**~/Documents/My Adobe Learning Manager Projects**” (without quotes) and press Enter.

   You or your Adobe Learning Manager administrator might have changed the default projects folder location. Contact your administrator for more Help to locate and clean up projects.

# How to clean up previous installations of Adobe Learning Manager desktop app? {#howtocleanuppreviousinstallationsofadobecaptivateprimedesktopapp}

### Windows {#Windows-3}

1. To open the **Run dialog, **press**&nbsp;Windows keys + R**.
1. Type regedit and search “**HKEY_LOCAL_MACHINE \\SOFTWARE\\Classes\\Installer\\**” (without quotes) or&nbsp;“**HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData\\S-1-5-18\\Products\\**”&nbsp; (without quotes) and press Enter.
1. Find the folder named Adobe Learning Manager and find the previous installation. Delete the registry entry.&nbsp; You can find the key by pressing the F3 key.

### Mac OS X {#MacOSX-6}

Move the files from the following path “**/Applications/Adobe Learning Manager/Users/Shared/Adobe/Learning Manager Assets/1.0**” to trash and then empty the trash.
