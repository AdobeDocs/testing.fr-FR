---
description: Enable or disable authentication for batch updates via API and generate
  a profile authentication token.
keywords: implementation;api;profile;profile api settings
seo-description: Enable or disable authentication for batch updates via API and generate
  a profile authentication token.
seo-title: Profile API settings
solution: Target
subtopic: Getting Started
title: Profile API settings
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Profile API settings{#profile-api-settings}

Enable or disable authentication for batch updates via API and generate a profile authentication token.

Adobe Target creates and maintains a profile for every individual user. This profile is stored on the Target edge cluster and is updated in real time after every visit, however, you can update a profile individually or in bulk via API.

For added security, you can require that the Bulk Update API call require a valid access token to be passed in the header of the request. Users with Approver permissions can generate and enable profile API authentication tokens.

**To require authentication and to generate an access token using the Target UI:**

1. Click **[!UICONTROL Setup]** > **[!UICONTROL Implementation]**.
1. Under **[!UICONTROL Profile API Settings]**, use the **[!UICONTROL Require Authentication]** drop-down list to enable or disable authentication requirements.

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate Pofile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   The token expires according to the time listed in the [!UICONTROL Expires In] box.

   >[!NOTE]
>
>You can also generate a profile authentication token via API. For more information, see [Profiles](https://developers.adobetarget.com/api/#profiles) on the [Adobe Target Developers website](https://developers.adobetarget.com/).

1. Copy the token and include it in the header of the request in the format: "Authorization" : "Bearer "

Click [!UICONTROL Re-generate Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>Resetting this token will cause API calls using the current token to fail. This will require updating any scripts or apps that use this token.

