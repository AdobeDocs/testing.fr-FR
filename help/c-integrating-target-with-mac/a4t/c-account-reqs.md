---
description: User account requirements to create an Adobe Analytics-based activity
  in Adobe Target (A4T).
keywords: Analytics as reporting source;a4t;A4T
seo-description: User account requirements to create an Adobe Analytics-based activity
  in Adobe Target (A4T).
seo-title: User permission requirements
solution: Target,Analytics
title: User permission requirements
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# User permission requirements{#user-permission-requirements}

User account requirements to create an Adobe Analytics-based activity in Adobe Target (A4T).

Before a report suite can be selected when defining an Analytics activity, you need both an Analytics user account and a Target user account. Your user accounts must be configured as described in the following sections:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

See [Join the Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/link_accounts.html) for more information.

* **Linked Accounts**. Your Analytics and Target user accounts must be linked to your Adobe ID. To verify, open **[!UICONTROL Account Settings]** > **[!UICONTROL Organization & Product Access]**.

   ![](assets/linking.png)

* **Experience Cloud group membership**. You must be a member of one or more Experience Cloud groups that have access to Analytics and Target. Verify that **[!UICONTROL Analytics]** and **[!UICONTROL Target]** appear in the **[!UICONTROL Marketing Apps]** section of the left navigation:

   ![](assets/analytics-target-access.png)

   Also verify that when you click on Analytics you see your full Analytics account. If you only see a welcome page with no access to your data, relink your account.

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

* **Analytics report suite access:** Before creating or viewing reports for an Analytics-powered activity, you must be a member of the **[!UICONTROL All Report Access]** group, or member of a group that has access to at least one report in the report suite that you want to use. If you are unable to view reports, make sure you are a member of one of these groups.

   See [Groups](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) for more information.

* **Web Services Access Group:** You must belong to the Web Services Access group in Adobe Analytics to be able to use Analytics as the reporting source for Target.

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

No additional privileges are required.
