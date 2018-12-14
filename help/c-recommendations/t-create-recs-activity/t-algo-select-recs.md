---
description: Select the criteria to use in your Recommendations activity.
keywords: recommendations;recommendations activity;criteria
seo-description: Select the criteria to use in your Recommendations activity.
seo-title: Select criteria
solution: Target
title: Select criteria
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Select criteria{#select-criteria}

Select the criteria to use in your Recommendations activity.

You can test multiple recommendation types against each other by adding more than one criteria.

If you select multiple criteria, traffic is split evenly between the selected criteria. For example, if you have selected two criteria and your activity is designed to display default content to 20% of activity entrants, then 40% of activity entrants will see the recommendations controlled by each criteria. There is no option to change the percentages for each criteria.

* To search for an existing criteria (for example, if many criteria cards display), type in the search field until the desired criteria appears, then select the criteria and click **[!UICONTROL Done]**.

   Some criteria are supplied with [!DNL Recommendations]. You and your team can also create your own custom criteria.

* To create a new criteria, click **[!UICONTROL Create New]**, then fill in the information for the new criteria. For information about creating new criteria, see [Create a New Criteria](../../c-recommendations/c-algorithms/t-create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

1. [Create a new recommendation](../../c-recommendations/t-create-recs-activity/t-create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), or find the recommendation whose criteria you want to set and click **[!UICONTROL Edit]**.
1. Select an industry type and a page type.

* **Industry Type: **The industry type is used to help categorize [!DNL Recommendations] criteria. To change your default industry vertical, click **[!UICONTROL Settings]** and select your desired default **[!UICONTROL Industry Vertical]** setting.
* **Page Type: **The page type helps you categorize your recommendations. There are also built-in criteria that can be chosen for each page type.
* **Compatible: **Show only those criteria where the selected page passes the required data. Not every criteria will run correctly on every page. The page or mbox needs to pass in `entity.id` or [!DNL entity.categoryId] for the current item/current category recommendations to be compatible. In general, it is best to show only compatible criteria. However, if you want incompatible criteria to be available for the activity, clear the **[!UICONTROL Compatible]** check box. This option can be disabled or enabled in your [!DNL Target] [!UICONTROL Preferences].

1. Click **[!UICONTROL Add]**.
