---
description: Target visitors who meet specific profile parameters.
keywords: visitor profile;target visitor profile
seo-description: Target visitors who meet specific profile parameters.
seo-title: Visitor Profile
solution: Target
title: Visitor Profile
topic: Premium
uuid: 462c80f4-bd5f-4dce-b02b-21b2c33c5bf6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Visitor Profile{#visitor-profile}

Target visitors who meet specific profile parameters.

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Name the audience.
1. Click **[!UICONTROL Add Rule]** > **[!UICONTROL Visitor Profile]**.

   ![](assets/target_visitor_profile.png)

1. Click **[!UICONTROL Select]**, then select one of the following options:

   Visitor profile parameters are passed via the mbox (profile). You can target either new or returning visitors, or include all users.

   * New Visitor
   * Returning Visitor
   * In Other Tests
   * Not In Other Tests
   * First Page of Session
   * Not First Page of Session
   * Category Affinity
   A visitor profile is created in the local edge memory for each mbox call with new `mboxPC`. After 30 minutes of inactivity, the profile is saved to the Target database and is accessible from other edges.

   When a site visitor logs in mid-session and gets a `3rdpartyId`, all previously-loaded profile attributes tied to the `3rdPartyId` are immediately available.

   You can target custom profile parameters and `user.` parameters. Choose the parameter you use want to use to target your activity. If the desired parameter does not appear, the parameter has not been fired by an mbox.

1. (Optional) Click **[!UICONTROL Add Rule]** and set up additional rules for the audience.
1. Click **[!UICONTROL Save]**.

**Creating Audiences (9:58)**

This video includes information about using audience categories.

* Create audiences
* Define audience categories

>[!VIDEO](https://www.youtube.com/watch?v=wV9lVTSOxMk)
