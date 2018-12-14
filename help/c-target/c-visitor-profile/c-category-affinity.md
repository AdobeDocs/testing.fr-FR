---
description: The category affinity feature automatically captures the categories a
  user visits and then calculates the user's affinity for the category so it can be
  targeted and segmented on. This helps to ensure that content is targeted to visitors
  who are most likely to act on that information.
keywords: affinity;category affinity
seo-description: The category affinity feature automatically captures the categories
  a user visits and then calculates the user's affinity for the category so it can
  be targeted and segmented on. This helps to ensure that content is targeted to visitors
  who are most likely to act on that information.
seo-title: Category affinity
solution: Target
title: Category affinity
topic: Standard
uuid: b81d9c91-a222-4768-9ac8-359f9ab9ca2d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Category affinity{#category-affinity}

The category affinity feature automatically captures the categories a user visits and then calculates the user's affinity for the category so it can be targeted and segmented on. This helps to ensure that content is targeted to visitors who are most likely to act on that information.

## Category affinity {#concept_75EC1E1123014448B8B92AD16B2D72CC}

The category affinity feature automatically captures the categories a user visits and then calculates the user's affinity for the category so it can be targeted and segmented on. This helps to ensure that content is targeted to visitors who are most likely to act on that information.

## Passing Category Affinity Information into Target {#section_B0C8E46EEBAC4549AD90352A47787D04}

Whenever a user visits your site, profile parameters specific to the visitor are recorded in the [!DNL Target] database. This data is tied to the user's cookie. One particularly useful parameter is `categoryId`, an mbox parameter assigned on a product page. As the visitor continues to browse, or returns for another session, the categories of products a particular user views can be recorded. You can also record category information by passing it as the mbox parameter `user.categoryId` in any mbox (including a nested mbox), as a URL parameter `user.categoryId`, or in Target page parameters with a global mbox. See your account representative for more details.

Separate categories with a comma to create separate categories. For example:

* `categoryId=clothing,shoes,nike,running,shox,nike shox turbo,nike shox turbo VI`
* `entity.categoryId=clothing,shoes,nike,running,shox,nike shox turbo,nike shox turbo VI`

Based on the frequency and recency of visits to your product categories, the category affinity (if any) a user has is recorded. Category affinity can be used to target populations for your activities.

You can use `user.categoryAffinities[]` in a profile script to return an array of the affinities that a visitor has populated.

## Business Case for Category Affinity {#section_D6FF913E88E6486B8FBCE117CA8B253B}

A visitor's activity in one session, such as which category he or she views the most often, can be used for targeting in subsequent visits. Each category page a visitor views during a session is captured, and his or her "favorite" category is calculated based on a recency and frequency model. Then, every time the visitor returns to the home page, the hero image area can be targeted to show content related to that user's favorite category.

## Example of Using Category Affinity {#section_A4AC0CA550924CB4875F4F4047554C18}

Suppose you sell musical instruments online and want to target sales promotions on bass guitars to visitors who have already expressed interest in guitars in the past. Using category affinity, you can create offers that display only to visitors with this category affinity.

## Category Affinity Algorithm {#section_8B86C7FF50294208866ABF16F07D5EB9}

The category affinity algorithm works as follows:

* 10 points for first view
* 5 points for every one after
* At end of session divide all values by 2

For example, viewing categoryA then categoryB in one session results in A: 10, B: 5. When the session ends, you will have A: 5, B: 2.5. If you view the same items in the next session, the values change to A: 15 B: 7.5.

## Use Category Affinity for Targeting {#concept_5750C9E6C97A40F8B062A5C16F2B5FFC}

Information to help you use a [!UICONTROL Category Affinity] audience for targeting in an activity.

<!-- 

target/c_use-category-affinity-for-targeted-group.xml

 -->

This section contains the following information:

* [Create an Audience to Use Category Affinity](../../c-target/c-visitor-profile/c-category-affinity.md#section_A27C600BBA664FE7A74F8FE076B78F40)
* [Use the Category Affinity Audience in an Activity](../../c-target/c-visitor-profile/c-category-affinity.md#section_91526B942D1B4AEBB8FCDF4EBFF931CF)

## Create an Audience to Use Category Affinity {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. From the **[!UICONTROL Audiences]** list, click **[!UICONTROL + Create Audience]**.

   Or

   To copy an existing audience, from the Audiences list, hover over the desired audience, then click the Copy icon. You can then edit the audience to create a similar audience.

1. Type a descriptive audience name.
1. Click **[!UICONTROL + Add Rule]** > **[!UICONTROL Visitor Profile]**.
1. From the **[!UICONTROL Visitor Profile]** drop-down list, select **[!UICONTROL Category Affinity]**.

   ![](assets/affinity.png)

1. Select the desired category:

   * Favorite Category
   * First Category
   * Second Category
   * Third Category
   * Fourth Category
   * Fifth Category

1. Chose the Evaluator:

   * Contains (case insensitive)
   * Does Not Contain (case insensitive)
   * Equals

1. Specify each new value in a separate line (for example, "shoes").
1. Click **[!UICONTROL Save]**.

## Use the Category Affinity Audience in an Activity {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

You can use Category Affinity audiences in any activity. During the three-step guided workflow, on the Target step, choose the desired audience.
