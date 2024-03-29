---
description: Target Standard can be integrated with Adobe Scene7 to provide Digital
  Asset Management (DAM) in the Content Library.
seo-description: Target Standard can be integrated with Adobe Scene7 to provide Digital
  Asset Management (DAM) in the Content Library.
seo-title: Scene7 settings
solution: Target
subtopic: Getting Started
title: Scene7 settings
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Scene7 settings{#scene-settings}

Target Standard can be integrated with Adobe Scene7 to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>Integrating Target with Scene7 enables delivery of assets (as part of activities) uploaded to the Adobe Experience Cloud assets folder. This integration does not enable access to all assets uploaded in Scene7 for delivery in Target activities.

If you have a Scene7 account, you can supply your Scene7 credentials. If you do not have a Scene7 account, reach out to your Adobe representative who can configure this functionality with a free Scene7 account dedicated for your Target account. This account can be used for purposes restricted for use in Target only. This service is made available to customers for workflows needing image-swap functionality.

If this setting is not configured, the Swap Image offer option within the activity creation workflow is not available. After this setting is configured, the option to swap/change image offers is available in both the [Visual Experience Composer (VEC) and in the Form-Based Experience Composer](../c-experiences/c-experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). You can then leverage image offers with images that have been uploaded from the Adobe Experience Cloud for use in Target activities.

If you want to reference a public image URL directly in an offer or custom code during activity creation, you should deploy the image to your own web servers and use your own URL in the code. There is no way to obtain the published URL of an image uploaded into the Experience Cloud to consume directly or outside of targeting workflows using Adobe Target. This functionality is not allowed, as per contract.

Note that the storage URL and the final Scene7 publish URLs of images are different and one must NOT create offers using the storage link of images as delivery will not work in such cases. One must use the image offers capability as explained in our help documentation.

To integrate with Scene7, you need to specify some of your Scene7 information.

1. Click **[!UICONTROL Setup]** > **[!UICONTROL Scene7 Settings]**.
1. Specify the following Scene7 account information:

   **Scene7 region:** The region for your Scene7 account: North America, Europe, or Asia.

   **Scene7 adhoc folder:** The location for content that resides outside the target folder and are manually uploaded to Scene7.

   **Scene7 email address:** The email address used to log in to Scene7.

   **Scene7 password:** The password used to log in to Scene7.
1. Click **[!UICONTROL Submit]**.
