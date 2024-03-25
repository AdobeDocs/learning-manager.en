---
jcr-language: en_us
title: White labeling in Adobe learning Manager Mobile app
description: White labeling is a practice of rebranding an app or service with your own brand and customizing it as if you were the original creator. In Adobe Learning Manager, you can apply white labeling to the mobile app, so you can rebrand the app, and make the app available to your users under your own brand.
contentowner: saghosh
exl-id: f37c86e6-d4e3-4095-9e9d-7a5cd0d45e43
---
# White labeling in Adobe learning Manager Mobile app

Adobe Learning Manager mobile app now supports white labeling – which means that you can now release the app under your own branding.

## How you should start preparing to launch your white-labeled app

To deploy and manage your own white labeled app, follow the steps:

  1. Prepare the assets (like splash screen image), and the text so both can be used in the app and the description on the app/play store.

  1. Assign a technical resource who is capable of:
  
  * Generating the push notification certificate files.
  * Signing the app binaries provided by the ALM team.
  * Uploading and managing the publishing process. The publishing process requires communication between your app manager and app/play store teams that your app complies with all publishing guidelines. From ALM, you will receive a fully compliant app binary.

## Overview

White labeling is a practice of rebranding an app or service with your own brand and customizing it as if you were the original creator. In Adobe Learning Manager, you can apply white labeling to the mobile app, so you can rebrand the app, and make the app available to your users under your own brand.

## What can be customized

The following can be customized:

### Fields

<table>
    <tbody>
    <tr>
   <td>
    <p>Account Id</p></td>
   <td>
    <p>The ID of your account. Note that the white labeled app will not be accessible to learners who belong to any other account.</p></td>
  </tr>
  <tr>
   <td>
    <p>Additional Account Ids</p></td>
   <td>
    <p>Add multiple accounts (sub-domains) if you want. Add the sub-domains as comma-separated without spaces. For example, acc01,acc02,acc03, and so on.<br> <b>Note:</b> You need to add the account id when specifying the sub-domains.</br> </p></td>
  </tr>
  <tr>
  <td>
  <p>App Name</p></td>
  <td>
  <p>The name that you want to use for the app.</p></td>
  </tr>
  <tr>
  <td>
  <p>App Short Name</p></td>
  <td>
  <p>In cases where the name of app is lengthy, give the app a short name that appears on the device.</p></td>
  </tr>
   <tr>
  <td>
  <p>Internal App Name</p></td>
  <td>
  <p>The name with which the OS identifies the app. The format that is usually used is: com.company-name.product-name.</p></td>
  </tr>
  <tr>
  <td>
  <p>Internal App name-iOS</p></td>
  <td>
  <p>Name the app differently if your users are on iOS. We recommend using the same name for both iOS and Android.</p></td>
  </tr>
  <tr>
  <td>
  <p>App Icon</p></td>
  <td>
  <p>The app icon as png. This icon displays on your app. The format to name is account-id_appIcon.png.</p></td>
  </tr>
  <tr>
  <td>
  <p>App splash screen</p></td>
  <td>
  <p>For the splash screen of your app, provide an image (png), that appears when your users launch the app. The format to name is account-id_splashIcon.png.</p></td>
  </tr>
  <tr>
  <td>
  <p>Client ID and Client Secret</p></td>
  <td>
  <p>The Integration Admin of your account provides the details, while registering the app. The Integration Admin must use the following:<ul><li>learner:read,learner:write as role</li><li>internal app name://redirect as redirect URL</li></ul></p></td>
  </tr>
  <tr>
  <td>
  <p>Account logo</p></td>
  <td>
  <p>The URL that hosts your organization's logo. Provide a cpcontents link as the account logo. The URL needs to be web encoded.</p></td>
  </tr>
  <tr>
  <td>
  <p>App store id for the app (iOS)</p></td>
  <td>
  <p>The ID required for implementing the force update. The App needs to know the learner should be redirected to the App store, to update the app.</p></td>
  </tr>
   <tr>
  <td>
  <p>Google play store id for the app (Android)</p></td>
  <td>
  <p>The ID required for implementing the force update.</p></td>
  </tr>
  <tr>
  <td>
  <p>Hostname for deep linking</p></td>
  <td>
  <p>To host your deep links, use learningmanager. If you want to use another hostname URL as a deep link, provide the URL of the host. For example, learningmanager.adobe.com.</p></td>
  </tr>
    </tbody>
</table>

>[!NOTE]
>
>Provide the data to your CSAMs so they can add it into your customized app binary.


#### Update site association to handle custom deeplinks

If you're using a custom domain or learningmanager\*.adobe.com as host, you need not take any action. However, if you use a custom solution or specific hostname for the URLs, add the site-association files.

>[!CAUTION]
>
>If the files are not present, the deeplinks will not work. Ensure the files are present.


Refer the following links for more information:

* [Android](https://learningmanager.adobe.com/.well-known/assetlinks.json)
* [iOS](https://learningmanager.adobe.com/.well-known/apple-app-site-association)

## Generate push notifications

Sending push notifications to Android and iOS apps require two different mechanisms.

* For iOS, generate the push notification certificates.
* For Android, provide a server key generated from the Firebase project. 

Follow the instructions below to set up the projects in Firebase:

### Push notifications on iOS

In iOS app development, a push notification certificate is a cryptographic credential issued by Apple that allows a server to securely send push notifications to an iOS device through Apple's Push Notification service (APNs).

The certificate ensures secure communication between your server (or provider) and Apple's APNs when sending push notifications to iOS devices.

Both Android and iOS use Firebase Cloud Messaging (FCM) as the service for sending push notifications to devices.

### How to generate the certificate on iOS

Follow the procedure:

1. Generate or download the **Push notification certificate** and private key (.p12). For more information, see the [Apple developer document](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_certificate-based_connection_to_apns).

1. Install the p12 file after the file is downloaded. Use the password to install in your **Keychain access**.

1. Navigate to **My certificates** and export the certificate. Ensure that you select the mime type .cer.

1. Once you have the p12 file and cer file are available, run the following commands:

```
- openssl pkcs12 -in privatekey.p12 -out myapnappkey.pem -nodes –clcerts

- openssl x509 -in privatekey.cer -inform DER -out myapnsappcert.pem 

- openssl s_client -connect gateway.sandbox.push.apple.com:2195 -cert myapnsappcert.pem -key myapnappkey.pem 
```

If you can connect to the server, the certificate you've created is valid. From the myapnappkey.pem file, copy the certificate and private key values.

### Push notifications on Android

Set up a project in Firebase and share the server key with the CSAM.

Contact the CSM team and get the files added to the SNS services on AWS. Users will have to get the entry registered in the SNS service for the push notification, which will require them to share the certificates generated above for validation.

>[!NOTE]
>
>For Android, the user needs to provide the server key from the Firebase project they create for Android for adding the entry in the SNS service.


## Create project in Firebase

### Android

Re-use the same project that you'd created in the steps above for push notifications.

[Add the project](https://learn.microsoft.com/en-us/xamarin/android/data-cloud/google-messaging/firebase-cloud-messaging) in Firebase and retrieve the ***google-services.json*** file.

### iOS

[Add the project](https://firebase.google.com/docs/ios/setup) to Firebase and retrieve the ***GoogleService-Info.plist*** file.

>[!IMPORTANT]
>
>Send the files to the Adobe Learning Manager CSAM team to include to the build of your app binary file.


## Generate the signed binaries

### iOS

```
sh""" xcodebuild -exportArchive -archivePath Runner.xcarchive -exportPath "ipa_path/" -exportOptionsPlist ./deviceAppBuildScripts/${ExportFile} 

mv ipa_path/*.ipa "${env.AppName}_signed.ipa" """ 
```

>[!NOTE]
>
>You'll need XCode 15.2 or higher to build the signed binaries.


## Android

```
sh""" ~/Library/Android/sdk/build-tools/30.0.3/apksigner sign --ks $storeFile --ks-pass "pass:$store\_password" --ks-key-alias $key\_alias --key-pass "pass:$key\_password" --out app-release-signed.apk -v app-release.apk """
```

>[!NOTE]
>
>You'll require Android sdk build-tools to build the signed binaries.

**What's next**

After generating the binaries, push the binaries into Play Store or App Store.

## How do I apply the changes

Sends the required assets and files to the CSM team. The CSM team then fills the [form](https://forms.office.com/r/bJRRaRBvSh) with the required changes and attaches the required assets. The team will then review and inform the engineering teams of the changes. The engineering team will then generate a build and share with the CSM team.

The CSM team will share the build with the customer.

## What cannot be customized

- Update Password screen
- Creating an account screen
