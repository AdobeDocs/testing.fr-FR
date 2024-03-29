---
description: Create activity-only audiences from within the three-step guided workflow
  when creating an activity. These ad hoc audiences can be used in other places within
  the same activity, but are not stored in the Audiences Library for use in other
  activities.
keywords: audience;audience rules;create audience;creating audience;activity only;activity-only;adhoc
seo-description: Create activity-only audiences from within the three-step guided
  workflow when creating an activity. These ad hoc audiences can be used in other
  places within the same activity, but are not stored in the Audiences Library for
  use in other activities.
seo-title: Create an activity-only audience
solution: Target
title: Create an activity-only audience
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Create an activity-only audience{#create-an-activity-only-audience}

Create activity-only audiences from within the three-step guided workflow when creating an activity. These ad hoc audiences can be used in other places within the same activity, but are not stored in the Audiences Library for use in other activities.

Activity-only audiences provide the following benefits:

* You can use activity-only audiences to create an audience that you want to use only once and you do not want to store it in the Audience Library. This prevents the Audience Library from being cluttered with audiences that you never want to use again.
* Activity-only audiences are not visible in the Audience Library. Because of this, they are shielded from unwanted changes by others in your organization.

**To create an activity-only audience:**

1. While creating an activity, in the **[!UICONTROL Audience]** box, click the **[!UICONTROL Edit]** icon (three vertical ellipses), then click **[!UICONTROL Replace Audience]**.

   ![](assets/replace_audiience.png)

1. On the Choose Audience page, click **[!UICONTROL Activity Only Audience]**.

   ![](assets/activity-only-aud.png)

1. Click **[!UICONTROL Create Audience]**.
1. Type a descriptive audience name.
1. Click **[!UICONTROL + Add Rule]**.

   Rules make it possible to limit your audience to a subset of you site visitors.

1. Select a rule type.

   Each rule type has its own parameters. See [Categories for Audiences](../c-target/c-audiences/c-target-rules/c-target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) for more information on configuring each type of audience rule.

1. Define the rule parameters.
1. Click **[!UICONTROL Save]**.

Keep the following information in mind as you work with activity-only audiences:

* You can create activity-only audiences in the Visual Experience Composer (VEC) or in the Form-Based Experience Composer. This functionality replaces refinement rules in previous versions of Target.
* You can create an activity to store in the Audience Library for reuse in other activities or you create an activity-only audience. After saving the audience, you cannot change the audience type.
* Refinements for existing activities are migrated to activity-only audiences.
* Activity-only audiences have a status of Used or Unused. Unused activity-only audiences display until the activity is saved. If left unused and you try to save the activity, a warning message displays informing you that unused activity-only audiences will be deleted.
* You can view audience definition details on a pop-up card accessed from the audience picker without opening the audience.
* You can [combine multiple audiences](../c-target/c-combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) to create activity-only audiences.

