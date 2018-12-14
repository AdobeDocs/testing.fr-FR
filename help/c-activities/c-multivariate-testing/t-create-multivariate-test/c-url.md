---
description: The Activity URL determines the page that is used in the test, and that
  opens when the test is designed.
keywords: Targeting
seo-description: The Activity URL determines the page that is used in the test, and
  that opens when the test is designed.
seo-title: Activity URL
solution: Target
title: Activity URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Activity URL{#activity-url}

The Activity URL determines the page that is used in the test, and that opens when the test is designed.

When prompted during activity creation, enter the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Create Activity]**.

>[!NOTE]
>
>[!DNL Target] does not differentiate between URL protocols ( [!DNL https] and [!DNL http]). As a result, [!DNL `https://www.adobe.com`] and [!DNL `http://www.adobe.com`] both match.

By default, the Visual Experience Composer opens the page that is specified in your Account Preferences. You can specify a different page during activity creation.

To display a different page after the Visual Experience Composer opens, click **[!UICONTROL Configure]** and select **[!UICONTROL URL]**, then enter the URL in the Activity URL box.

![](assets/url-config.png)

Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

Additional rules can be based on any of the following:

* URL
* Domain
* Path
* Hash (#) Fragment
* Query
* mbox Parameter

Additional rules can be joined to the Activity URL with AND or OR. All rules you add are evaluated against each other with AND.

Click **[!UICONTROL Save]** when you have finished.

>[!NOTE]
>
>If you entered a URL for a site that does not include the Target Standard JavaScript code, you cannot select page elements.

By default, the [!UICONTROL Visual Experience Composer] does not allow changes to elements containing JavaScript, such as rotating banners. You can toggle off **[!UICONTROL Render using JavaScript]** if you want to be able to alter those elements using the [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>If you change the URL after making changes to a page for one or more experiences, the experience is reset using the new page and the changes you made are lost.

