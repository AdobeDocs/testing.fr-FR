---
description: Use the mobile preview link to perform easy end-to-end QA for mobile
  app activities and enroll yourself into different experiences right on your device
  without any special test devices.
keywords: qa;preview;preview links;mobile;mobile preview
seo-description: Use the mobile preview link to perform easy end-to-end QA for mobile
  app activities and enroll yourself into different experiences right on your device
  without any special test devices.
seo-title: Target mobile preview
solution: Target
title: Target mobile preview
topic: Advanced,Standard,Classic
uuid: 313150fa-a7ec-46fe-9166-742a5c246a72
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Target mobile preview{#target-mobile-preview}

Use the mobile preview link to perform easy end-to-end QA for mobile app activities and enroll yourself into different experiences right on your device without any special test devices.

>[!NOTE]
>
>This feature will be turned on in the UI for all customers after October 12, 2017. The mobile preview feature requires that you download and install the appropriate 4.14 (or later) version of the Adobe Mobile SDK.

## Overview {#section_981D6FA4AEE64098809EA606E89E4A5E}

The mobile preview functionality lets you fully test your Mobile app activities prior to launching them live.

## Prerequisites {#section_A763C564C9E84B0EB448237B5B1E4068}

1. **Use a supported version of the SDK:** The mobile preview feature requires that you download and install the appropriate 4.14 (or later) version of Adobe Mobile SDK in your corresponding apps.

   For instructions to download the appropriate SDK, see:

   * **iOS:** [Before You Start](https://marketing.adobe.com/resources/help/en_US/mobile/ios/requirements.html) in the *iOS SDK 4.x for Experience Cloud Solutions* guide.
   * **Android:** [Before You Start](https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html) in the *Android SDK 4.x for Experience Cloud Solutions* guide.

1. **Set up a URL scheme:** The preview link uses a URL scheme to open your app. You must specify a unique URL scheme for the preview.

   The following illustration is an example on iOS:

   ![](assets/mobile-preview-url-scheme-ios.png)

   The following illustration is an example on Android:

   ![](assets/Android_Deeplink.png)

1. **Track Adobe DeepLink**

   **iOS:** In the app delegate, call `[ADBMobile trackAdobeDeepLink:url` when the delegate is asked to open the resource with the URL scheme that was specified in the previous step.

   The following code snippet is an example:

   ```
   - (BOOL) application:(UIApplication *)app openURL:(NSURL *)url 
                options:(NSDictionary<NSString *,id> *)options { 
   
       if ([[url scheme] isEqualToString:@"com.adobe.targetmobile"]) { 
           [ADBMobile trackAdobeDeepLink:url]; 
           return YES; 
       } 
       return NO; 
   } 
   ```

   **Android:** In the app , call `Config.trackAdobeDeepLink(URL);` when the caller is asked to open the resource with the URL scheme that was specified in the previous step.

   ```
    private Boolean shouldOpenDeeplinkUrl() { 
        Intent appLinkIntent = getIntent(); 
        String appLinkAction = appLinkIntent.getAction(); 
        Uri appLinkData = appLinkIntent.getData; 
        if (appLinkData.toString().startsWith("com.adobe.targetmobile")) { 
            Config.trackAdobeDeepLink(appLinkData); 
            return true; 
        } 
        return false; 
     }
   ```

   To make Mobile Preview work for Android, you must also add the following code snippet in [!DNL AndroidManifest.xml]:

   ```
   <activity android:name="com.adobe.mobile.MessageFullScreenActivity" />
   ```

## Generating a Preview Link {#section_D9D58173FFF34E9BB75EBF357273F128}

1. In the Target UI, click the **[!UICONTROL More Options]** icon (three vertical ellipses), then select **[!UICONTROL Create Mobile Preview]**.

   ![](assets/mobile-preview-create.png)

1. Select the activities that you want to preview, then click **[!UICONTROL Generate Mobile Preview LInk]**.

   >[!NOTE]
>
>Only form-based AB and XT activities can be selected.

   ![](assets/mobile-preview-select-activities.png)

1. Specify your app's URL scheme.

   This needs to be the same as what is present in your iOS or Android app. Repeat this process separately for iOS and Android, if required.

   ![](assets/mobile-preview-enter-url-scheme.png)

1. Click **[!UICONTROL Generate Mobile Preview Link]**, then copy the link.

   ![](assets/mobile-preview-generate-and-copy.png)

## Preview on Your Device {#section_521F0D46F3DE4A2A98283A1B73FF69F6}

Open the link in a mobile browser on a device where you have your app installed. This app can be the production app that you downloaded from the Apple App store or the Google Play store. It doesn't have to be a special build. If you have an active preview link, you will be able to view the experiences on device.

1. Open the link in your mobile browser.

   Share the link that you copied in the previous step from the Target UI to your mobile device in a convenient way, for example using text, email, or Slack.

   <table id="table_F853E79832954A87850BDDAF36D88A7F"> 
    <tbody> 
    <tr> 
    <td colname="col1"> <p> <img id="image_D6C60AC753FA4296B440B8C5F6BB5603" href="assets/mobile-preview-open-deeplink.png" /> </p> </td> 
    <td colname="col2"> <p> <img id="image_F1459ADE032F4B12880385F0CF6218FA" href="assets/mobile-preview-open-app.png" /> </p> </td> 
    </tr> 
    </tbody> 
    </table>

   Your app opens and starts the Target Mobile Preview Mode.

1. Select the combination of experiences that you want to see, then click **[!UICONTROL Launch Experiences]**.

   <table id="table_6123AAE2EE9D426CA477BD71B4361489"> 
    <tbody> 
    <tr> 
    <td colname="col1"> <p> <img href="assets/mobile-preview-experience-selection-1.png" id="image_C9AA4C0525A449AA91A253BDD177A1DC" /> </p> </td> 
    <td colname="col2"> <p> <img id="image_CE9638C68F184AE1AA66A0CDE9AA3770" href="assets/mobile-preview-experience-result-1-france.png" /> </p> </td> 
    <td colname="col3"> <p> <img id="image_92CB96E9A4274216B7A328F2B49FAEF3" href="assets/mobile-preview-experience-result-1-shipfree.png" /> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p> <img id="image_E7117C66BA534B2B87F1BDBA20E9EC5A" href="assets/mobile-preview-experience-selection-2.png" /> </p> </td> 
    <td colname="col2"> <p> <img id="image_3E880BB6C6D34F1EAC64C21CE07A9267" href="assets/mobile-preview-experience-result-2-aus.png" /> </p> </td> 
    <td colname="col3"> <p> <img id="image_2B419DDBD58B4C0CB4E5A967FCA50922" href="assets/mobile-preview-experience-result-2-10off.png" /> </p> </td> 
    </tr> 
    </tbody> 
    </table>

## Limitations {#section_4E9BDED0F718485292527EFB508305BD}

* The view must load again for the new content to display after the [!UICONTROL Launch Experiences] button is clicked. The easiest way is to switch to a different screen and then come back to the screen where you are expecting the change to happen.
* Mobile preview is not supported for Android versions earlier than API-19 (KitKat).