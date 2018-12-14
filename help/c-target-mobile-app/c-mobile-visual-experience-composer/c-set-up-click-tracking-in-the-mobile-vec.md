---
description: Information about how Target mobile customers can track when a user clicked
  an element.
keywords: mobile vec;mobile visual experience composer;mobile experience composer
  options;mobile experience options;target view;clicks;click tracking;track
seo-description: Information about how Target mobile customers can track when a user
  clicked an element.
seo-title: Set up click tracking in the Mobile VEC
solution: Target
title: Set up click tracking in the Mobile VEC
topic: Standard
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Set up click tracking in the Mobile VEC{#set-up-click-tracking-in-the-mobile-vec}

Information about how Target mobile customers can track when a user clicked an element.

>[!NOTE]
>
>The Visual Experience Composer for Native Mobile Apps is currently offered as a Beta feature available to select customers to obtain feedback to help us improve the feature before making it available to all customers. Please talk to your Customer Success Manager or Adobe Client Care to participate in this Beta program.

After views are set up and the SDK is integrated in a mobile app. No steps are needed in the Mobile SDK. The workflow for setting up click tracking is similar to the functionality provided in the Web domain.

1. When setting your goals on the Goals & Settings page for your activity , select the [!UICONTROL Conversion] success metric.

   ![](assets/mobile-vec-clicktrack1.png)

1. For the action, select **[!UICONTROL Clicked an Element]**, then click **[!UICONTROL Select Elements]**.

   Your mobile app opens in the Mobile Visual Experience Composer (VEC).

   ![](assets/mobile-vec-clicktrack2.png)

1. Select any elements that you want to track.

   See the [!UICONTROL Considerations] section below for tips on selecting elements.

   ![](assets/mobile-vec-clicktrack3.png)

1. Click the check mark at the top of the screen to save your selections.

You can also edit and change the click selections or delete them if you need to start fresh.

![](assets/mobile-vec-clicktrack4.png)

When an activity entrant clicks a selected element, that click is counted as a conversion.

## Considerations {#section_916EF60AC56A4764931B21BEA0C8B87B}

There are several things to consider when selecting elements:

* If you select more than one element, if an entrant clicks any one of the chosen elements, the click is counted. To count each item separately, set up individual success metrics for each element.
* Click events are sent to Target as soon as the user clicks the element.
* While selecting elements, only those elements that have the click handler attached are allowed to be selected. Other elements won't be available for selection.
* You can browse to any section of the app, but make sure that [views](../../c-target-mobile-app/c-mobile-visual-experience-composer/c-mobile-visual-experience-composer.md#section_9B3941F6EE854F87917611D2A8AF8868) are defined for the section where you are selecting elements for click tracking.
* While editing an activity, if the device is already selected in Step1, you don't need to select the device again. However, if you land directly on the click track page, you will be shown the device selection screen to select an authorized device.

