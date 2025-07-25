---
jcr-language: en_us
title: White labeling in Adobe learning Manager Mobile app
description: White labeling is a practice of rebranding an app or service with your own brand and customizing it as if you were the original creator. In Adobe Learning Manager, you can apply white labeling to the mobile app, so you can rebrand the app, and make the app available to your users under your own brand.
contentowner: saghosh
exl-id: f37c86e6-d4e3-4095-9e9d-7a5cd0d45e43
---
# White labeling in Adobe learning Manager Mobile app

Adobe Learning Manager mobile app now supports white labeling, which means that you can now release the app under your own branding.

ALM will make available updated white labeled binary files according to the following timelines:

1. For major releases to the mobile app, files will be made available two weeks in advance.
2. For any planned updates for urgent fixes, files will be made available one week in advance.
3. For unplanned, urgent & immediate fixes, files will be made available on a best effort basis.

Binaries will be made available in the customer's designated folders. Contact your CSMs to access the files. The customer is responsible for timely publishing and related processes.  

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
    <p>Account Id</p>
   </td>
   <td>
    <p>The ID of your account. Note that the white labeled app will not be accessible to learners who belong to any other account.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>Additional Account Ids</p>
   </td>
   <td>
    <p>Add multiple accounts (sub-domains) if you want. Add the sub-domains as comma-separated without spaces. For example, acc01,acc02,acc03, and so on.<br> <b>Note:</b> You need to add the account id when specifying the sub-domains.</br> </p>
   </td>
  </tr>
  <tr>
   <td>
    <p>App Name</p></td>
   <td>
    <p>The name that you want to use for the app.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>App Short Name</p>
   </td>
   <td>
    <p>In cases where the name of app is lengthy, give the app a short name that appears on the device.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>Internal App Name</p></td>
   <td>
    <p>The name with which the OS identifies the app. The format that is usually used is: com.company-name.product-name.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>Internal App name-iOS</p>
   </td>
   <td>
    <p>Name the app differently if your users are on iOS. We recommend using the same name for both iOS and Android.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>App Icon</p>
   </td>
   <td>
    <p>The app icon as png. This icon displays on your app. The format to name is account-id_appIcon.png. The app icon's dimensions are 512 × 512 pixels.<div>Please note that Apple does not allow Alpha channel in app icons. So, make sure to remove the Alpha channel from the asset before submitting it.</div></p>
   </td>
  </tr>
  <tr>
   <td>
    <p>App splash screen</p></td>
   <td>
    <p>For the splash screen of your app, provide an image (png), that appears when your users launch the app. The format to name is account-id_splashIcon.png. The dimensions of the square-based splash screens are 1052 × 1052 pixels and circle-based splash screens are 768 x 768 pixels.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>Client ID and Client Secret</p>
   </td>
   <td>
    <p>The Integration Admin of your account provides the details, while registering the app. The Integration Admin must use the following:<ul><li>learner:read,learner:write as role</li><li>internal app name://redirect as redirect URL</li></ul></p>
   </td>
  </tr>
  <tr>
   <td>
    <p>Account logo</p>
   </td>
   <td>
    <p>The URL that hosts your organization's logo. Provide a cpcontents link as the account logo. The URL needs to be web encoded.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>App store id for the app (iOS)</p>
   </td>
   <td>
    <p>The ID required for implementing the force update. The App needs to know the learner should be redirected to the App store, to update the app.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>Google play store id for the app (Android)</p>
   </td>
   <td>
    <p>The ID required for implementing the force update.</p>
   </td>
  </tr>
  <tr>
   <td>
    <p>Hostname for deep linking</p>
   </td>
   <td>
    <p>To host your deep links, use learningmanager. If you want to use another hostname URL as a deep link, provide the URL of the host. For example, learningmanager.adobe.com.</p>
   </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Provide the data to your CSAMs so they can add it into your customized app binary.


#### Update site association to handle custom deep links

If you're using a custom domain or learningmanager\*.adobe.com as host, you need not take any action. However, if you use a custom solution or specific hostname for the URLs, add the site-association files.

>[!CAUTION]
>
>If the files are not present, the deep links will not work. Ensure the files are present.


Refer the following links for more information:

* [Android](https://learningmanager.adobe.com/.well-known/assetlinks.json)
* [iOS](https://learningmanager.adobe.com/.well-known/apple-app-site-association)

## Get your team ID for the App Store

To get your Team ID:

1. Log in to your **[!UICONTROL Apple Developer]** account.
2. Select **[!UICONTROL Membership Details]** at the top of the page and copy your Team ID.

This ID is required to add the white labeled app entry in the metadata files to enable deep linking.

## Get the SHA-256 fingerprint for Android

The SHA-256 fingerprint for the Android signing certificate is required when adding the white labeled app entry.

To generate SHA-256 fingerprint:

1. Run the following command:

```
keytool -list -v -keystore <keystore/jks file> -alias <aliaskey> -storepass <storepassword> -keypass <keypassword>
```

In the output, find Certificate fingerprints, then copy the SHA-256 value. Share this fingerprint as needed for your deep linking configuration.

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

For Android, the user needs to provide the services.json file from the Firebase project for adding the entry in the SNS service.

Create a project in Firebase and share the services.json file to the CSM team. This file is needed for token-based entry in the SNS. Note that the server key is no longer used. See [Create project in Firebase](#create-project-in-firebase). 

To download the services.json file, follow these steps:

1. Log in to the **Firebase** console.
1. Go to **Project settings** and select **Cloud Messaging**.
1. Find **Firebase Cloud Messaging API** and select **Manage Service Accounts**.
1. In the **Service cccounts** page, select the **Service Accounts** in the left panel.
1. Find your project entry, and select **Manage details** under actions.

   >[!NOTE]
   >
   >   The project entry format will be <-accountname->@appspot.gserviceaccount.com.

1. Go to the **Keys** tab and select **Add Key**.
1. If there is no key, select **Create new key** and select **JSON** as the key type. This will generate and download the JSON file.
1. If there is already a key, select **Upload existing key**, paste the key, and upload it. This will generate and download the JSON file.

<!-- Set up a project in Firebase and share the server key with the CSAM.-->

Contact the CSM team and share the JSON file for adding the entry to the SNS services on AWS. Users will have to get the entry registered in the SNS service for the push notification, which will require them to share the certificates generated above for validation.

## Create project in Firebase {#create-project-in-firebase}

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

<!--```
sh""" xcodebuild -exportArchive -archivePath Runner.xcarchive -exportPath "ipa_path/" -exportOptionsPlist {ExportFile} 

mv ipa_path/*.ipa "${env.AppName}_signed.ipa" """ 
```-->

The `<root>` folder contains the **Runner.xcarchive.zip** file. Run the below commands to generate the signed binary:

1. Run the following command to unzip the archive:

   ```
   unzip Runner.xcarchive.zip
   ```

2. Navigate to the app directory:

   ```
   cd Runner.xcarchive/Products/Applications/Runner.app
   ```

3. Copy the mobile provisioning file:

   ```
   cp <path>/<mobile-provisioningfile>.mobileprovision embedded.mobileprovision
   ```

4. Run the following command to update your signing information to the framework library:

   ```
   codesign -f -s "Distribution Certificate Name" Frameworks/*
   ```

5. Return to the `<root>` folder (where Runner.xcarchive.zip is located):

   ```
   cd <root>
   ```

6. Export the archive using xcodebuild:

   ```
   xcodebuild -exportArchive -archivePath Runner.xcarchive -exportPath ipa_path/ -exportOptionsPlist <path>/<ExportOptions-file>.plist
   ```
   
7. Locate the .ipa file in the ipa_path folder.
8. Upload the .ipa file to `Diawi` website.
9. Once fully uploaded, select the **[!UICONTROL Send]** button.
10. After completion, you will receive a QR code and a link.
11. Open the QR code or link directly in Safari.

   If the device is included in the provisioning profile, the installation should proceed on the device.

>[!NOTE]
>
>You'll need XCode 15.2 or higher to build the signed binaries.


### Android

**For apk file**

>[!IMPORTANT]
>
>Before running the `apksigner` command, execute the following commands to export your keystore password and key alias password as environment variables: 
>
>```
>export KS_PASS=your_keystore_password
>export KEY_PASS=your_key_password
>```

```
sh""" <path>/apksigner sign --ks $storeFile. --ks-pass env:KS_PASS --ks-key-alias $key_alias --key-pass env:KEY_PASS --out app-release-signed.apk -v app-release.apk """

```

>[!NOTE]
>
>The path to the `apksigner` tool typically looks like this: ~/Library/Android/sdk/build-tools/30.0.3/apksigner.

**For aab file**

>[!NOTE]
>
>You'll require Android sdk build-tools to build the signed binaries.

The Play Store requires Android binaries in the aab format for publishing. Therefore, we will provide the unsigned .aab file.

>[!NOTE]
>
>When creating a keystore file, you need to generate a keystore password, a signing key alias, and a signing key alias password.

Follow the below steps to sign the .aab file:

Run the following command:

```
<path>/jarsigner -verbose -sigalg SHA256withRSA -digestalg SHA-256 -keystore <keystore-file> app-release.aab <signingKeyAlias>
```

>[!NOTE]
>
>The **[!UICONTROL jarsigner]** is included with Java. Ensure that you are using Java 21.

When prompted, please enter the following passwords:

* Keystore password
* password for signing key alias

You can use the provided apk. However, if you need to generate an apk from an aab file, please follow these steps:

>[!NOTE]
>
>You will need to install **[!UICONTROL bundletool]** to generate APKs.


Run the following command to create the apk file:

```
java -jar <path>/bundletool-all.jar  build-apks --bundle=app-release.aab --output=my_app.apks --mode=universal
```

To unzip the file, run the following command:

```
unzip my_app.apks -d output_dir
```

You will get the apk file from the **[!UICONTROL output_dir]** folder.

**What's next**

After generating the binaries, push the binaries into Play Store or App Store.

### Pushing the apps to the store for review

After getting the final binaries, you can upload them to the respective app stores (iOS or Android) for review. Follow these steps to upload the binaries to the app stores.

**iOS**

1. Log in to the Transporter app with your App Store credentials.
2. Select the **+** button at the left top and upload the production certificate (.ipa file).
3. If the .ipa file is correct, you will be prompted to upload the app to the App Store.
4. After the app is delivered, sign in to the App Store. Within a few hours, the binary will appear in the TestFlight section. You can enable it for final sanity testing in TestFlight before the app review and use this IPA as the binary when submitting the app for a new release.

**Android**

1. Open the Google Play Store Console.
2. Go to **[!UICONTROL Dashboard]** > **[!UICONTROL View App Releases]** > **[!UICONTROL Release Dashboard]** and then select the **[!UICONTROL Create New Release]**.
3. Upload the generated .aab file as the app bundle and type release details such as the version number and What's New information.
4. Save your changes and submit the app for review.
5. Make sure to set the app distribution to 100% (Google sets it to 20% by default).

#### Useful Links for app publishing

**Android**

[Create and set up your app](https://support.google.com/googleplay/android-developer/answer/9859152?hl=en)
[Prepare your app for review](https://support.google.com/googleplay/android-developer/answer/9859455?sjid=2454409340679630327-AP)

**iOS**

[Submit for review](https://developer.apple.com/help/app-store-connect/manage-submissions-to-app-review/submit-for-review)

## How do I apply the changes

Sends the required assets and files to the CSM team. The CSM team then fills the [form](https://forms.office.com/r/bJRRaRBvSh) with the required changes and attaches the required assets. The team will then review and inform the engineering teams of the changes. The engineering team will then generate a build and share with the CSM team.

The CSM team will share the build with the customer.

## What cannot be customized

* Update Password screen
* Creating an account screen
