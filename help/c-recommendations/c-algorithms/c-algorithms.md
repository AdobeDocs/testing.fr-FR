---
description: Criteria are rules that determine which products to recommend based on
  a predetermined set of visitor behaviors.
keywords: recommendations;recommendations activity;criteria
seo-description: Criteria are rules that determine which products to recommend based
  on a predetermined set of visitor behaviors.
seo-title: Criteria
solution: Target
title: Criteria
title-outputclass: premium
topic: Premium
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# ![PREMIUM](/help/assets/premium.png) Criteria{#criteria}

Criteria are rules that determine which products to recommend based on a predetermined set of visitor behaviors.

## Criteria {#concept_4BD01DC437F543C0A13621C93A302750}

Criteria are rules that determine which products to recommend based on a predetermined set of visitor behaviors.

Criteria determine which action will result in which recommendation. You can test multiple recommendation types against each other by adding multiple criteria.

## Industry Vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

You select an industry vertical based on the goals of your recommendations activity:

<table id="table_B99C2269E3EA4D5AA710C03A6BBBB008"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Industry Vertical </th> 
   <th colname="col2" class="entry"> Goal </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Retail/Ecommerce </p> </td> 
   <td colname="col2"> <p>Conversion resulting in purchase </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lead Generation/B2B/Financial Services </p> </td> 
   <td colname="col2"> <p>Conversion with no purchase </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Media/Publishing </p> </td> 
   <td colname="col2"> <p>Engagement </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recommendation Key {#section_885B3BB1B43048A88A8926F6B76FC482}

The recommendation key you select determines the criteria type. There are several criteria types, which are represented as criteria cards when you set up a [!DNL Recommendations] activity.

<table id="table_C82741028256468E9FE0B789A4C22F33"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Criteria Type </th> 
   <th colname="col2" class="entry"> Keys </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Current Page Activity </p> </td> 
   <td colname="col2"> <p>Recommend items based on what users do on the current page. For example, visitors who view a particular article might want to see other articles from the same category. </p> <p> 
     <ul id="ul_84C06C98520B4CF98FF296D051EA360D"> 
      <li id="li_1D0F6D833598441385EE674ABE27EC9C"> <p>Current Item </p> </li> 
      <li id="li_28971A6C56F5470982BF2ECB0FF0140F"> <p>Current Category </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom </p> </td> 
   <td colname="col2"> <p>Recommend items based on custom attributes. </p> <p> 
     <ul id="ul_E34FB629F7984A0C9637FB7E3A5DCC0F"> 
      <li id="li_2824DCFCA5D74DFAACF22057872C0420"> <p>Custom Attribute </p> </li> 
     </ul> </p> <p>When you base recommendations on custom attributes, you must select the custom attribute and then select the recommendation type. </p> <p>You can perform real-time filtering on top of your own custom criteria output. For example, you can limit your recommended items to only those from a visitor's favorite category or brand. This gives you the power to combine off-line calculations with real-time filtering. </p> <p>This functionality means that you can use Target to add personalization on top of your offline calculated recommendations or custom-curated lists. This combines the power of your data scientists and research with Adobe's tried-and-true delivery, run-time filtering, A/B testing, targeting, reporting, integrations, and more. </p> <p>With the addition of inclusion rules on Custom criteria, this turns otherwise static recommendations into dynamic recommendations based a visitor's interests. </p> <p> 
     <ul id="ul_BDD55AB34F4A43C691D2399C16AA3D6C"> 
      <li id="li_133C33E0D02E4861A4C855BD8A492E69"> <p>Custom criteria are configurable, like other criteria in recommendations. </p> </li> 
      <li id="li_AC201F0917BF465C985E8947635F762E"> <p>You can use <a href="../../c-recommendations/c-products/c-collections.md#concept_671BEFFB997D4F1282665BF3CAC00AC5" format="dita" scope="local"> collections</a>, <a href="../../c-recommendations/c-products/c-feeds.md#task_DD6D2F889E234F8C82B1604A3B315D81" format="dita" scope="local"> exclusions</a>, and <a href="../../c-recommendations/c-algorithms/c-use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F" format="dita" scope="local"> inclusions</a> (including the special rules for Price and Inventory) in the same way as any other criteria. </p> </li> 
     </ul> </p> <p>Possible use-cases include: </p> <p> 
     <ul id="ul_E353950A09DB4CFD91FF7F580D77A6A5"> 
      <li id="li_2348C2FFEFD44084AF639A59B0452CFC"> <p>You want to recommend movies from a custom-curated list, but <i>only</i> if the visitor hasn't already watched them. </p> </li> 
      <li id="li_8152A997C37C4116B506698CA0A3E5BE"> <p>You want to run an offline algorithm and use the results to power your recommendations, but you need to ensure that out-of-stock items are never recommended. </p> </li> 
      <li id="li_F2078FF5468A477EABDD7A25E7A68EE7"> <p>You want to include only items that are from this visitor's favorite category. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Past Behavior </p> </td> 
   <td colname="col2"> <p>Recommend items based on how visitors have responded to an item in the past. For example, people who have purchased a particular brand have been more likely to purchase another item from that brand. </p> <p> 
     <ul id="ul_2ED7631E9E7149EDA36D7A0F93BCF1C4"> 
      <li id="li_B3EB50778A2E4F55A61D95E3834BEE91"> <p>Last Purchased Item </p> </li> 
      <li id="li_CD2D62C14F71463E8D4BED64F1CF7846"> <p>Last Viewed Item </p> </li> 
      <li id="li_4D06DB888F0A43DD961172CAB82F6ACF"> <p>Most Viewed Item </p> </li> 
      <li id="li_5AA64DC791694E628177B622EA5344F9"> <p>Favorite Category </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Popularity </p> </td> 
   <td colname="col2"> <p>Recommend the most popular items, such as the most popular videos in a related category or the products that have been viewed most often on your site. </p> <p> 
     <ul id="ul_97F9B3D46473459CAD91046FE6F0966B"> 
      <li id="li_1AB63F10D22F43FDBADE6853F432227E"> <p>Popularity </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recently Viewed Items </p> </td> 
   <td colname="col2"> <p>Recommend the items a visitor has viewed most recently, such as the items a visitor looked at the last time he or she visited your site, or the articles that are trending most highly right now. </p> <p>The Recently Viewed Items algorithm returns results specific to a visitor’s activity within an <a href="../../administrating-target/c-hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E" format="dita" scope="local"> environment</a>. If two sites belong to different environments and a visitor switches between the two sites, the algorithm will return only recently viewed items from the appropriate site. </p> <p>This criteria type is not limited by collections. </p> <p> 
     <ul id="ul_9017DDFB12AA4826BF139D5D24610574"> 
      <li id="li_B0A11E8C999C402EA7333481E9F04C1C"> <p>Recently Viewed Items </p> </li> 
     </ul> </p> <p> <p>Note:  You cannot use the Recently Viewed Items criteria for backup recommendations. </p> </p> <p>Recently Viewed Items/Media can be filtered so that only items with a particular attribute are displayed. </p> <p> 
     <ul id="ul_A2D260F01CA047EEA72EF56BD0EE88FA"> 
      <li id="li_DB107DD357B741CCB2B7A4FDAD16F9D6"> <p>Recently Viewed criteria are configurable, like other criteria in recommendations. </p> </li> 
      <li id="li_85452C03F0924D4C8D854509F1293021"> <p>You can use <a href="../../c-recommendations/c-products/c-collections.md#concept_671BEFFB997D4F1282665BF3CAC00AC5" format="dita" scope="local"> collections</a>, <a href="../../c-recommendations/c-products/c-feeds.md#task_DD6D2F889E234F8C82B1604A3B315D81" format="dita" scope="local"> exclusions</a>, and <a href="../../c-recommendations/c-algorithms/c-use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F" format="dita" scope="local"> inclusions</a> (including the special rules for Price and Inventory) in the same way as any other criteria. </p> </li> 
     </ul> </p> <p>Possible use-cases include: </p> <p> 
     <ul id="ul_664648DD336643AEAE57FD931BBC742C"> 
      <li id="li_70FFEEB8514345A0B6DBFA1A47C071DA"> <p> A multi-national company with multiple businesses might have a visitor view items across multiple digital properties. In this case, you can limit the recently viewed items to display only for the respective property where it was viewed. This prevents Recently Viewed items from displaying on another digital property's site. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Criteria/Algorithms {#section_DC4E38A00B9744959F05F8E10A0087A1}

[!DNL Target Recommendations] uses sophisticated algorithms to determine when a visitor's actions qualify for the criteria set in your activity. The recommendation key determines the recommendations logic options that are available.

<table id="table_23DE3F3FFE374F4F812684BD6259930A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Criteria </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Items/Media with Similar Attributes </p> </td> 
   <td colname="col2"> <p> Recommends items or media similar to items or media based on current page activity or past visitor behavior. </p> <p> <p>Note: If you select <span class="uicontrol"> Items</span>/<span class="uicontrol"> Media with Similar Attributes</span>, you will have the option to set <a href="../../c-recommendations/c-algorithms/t-create-new-algorithm.md#concept_5402DAFA279C4E46A9A449526889A0CB" format="dita" scope="local"> content similarity rules</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> People Who Viewed This, Viewed That </p> </td> 
   <td colname="col2"> <p class="- topic/p "> Recommends items that are most often viewed in the same session that the specified item is viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> People Who Viewed This, Bought That </p> </td> 
   <td colname="col2"> <p class="- topic/p "> Recommends items that are most often purchased in the same session that the specified item is viewed. This criteria returns other products people purchased after viewing this one, the specified product is not included in the results set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> People Who Bought This, Bought That </p> </td> 
   <td colname="col2"> <p class="- topic/p "> Recommends items that are most often purchased by customers at the same time as the specified item. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site Affinity </p> </td> 
   <td colname="col2"> <p>Recommends items based on the certainty of a relationship between items. You can configure this criteria to determine how much data is required before a recommendation is presented using the <span class="wintitle"> Inclusion Rules</span> slider. For example, if you select <span class="wintitle"> very strong</span>, the products with the strongest certainty of a match are recommended. </p> <p>For example, if you set a very strong affinity and your design includes five items, three of which meet the strength of connection threshold, the two items that do not meet the minimum strength requirements are not displayed in your recommendations and are replaced by your defined backup items. The items with the strongest affinity display first. </p> <p> Some customers with diverse product collections and diverse site behaviors might get the best results if they set a weak site affinity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> Top Sellers </p> </td> 
   <td colname="col2"> <p class="- topic/p "> The items that are included in the most completed orders. Multiple units of the same item in a single order are counted as one order. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> Most Viewed </p> </td> 
   <td colname="col2"> <p class="- topic/p "> The items or media that are viewed most often. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Recently Viewed Items/Media </p> </td> 
   <td colname="col2"> <p> Items that have been viewed recently by the visitor. When using this criteria, you should update the <span class="keyword"> Target</span> design to handle cases where blank recommendations would show when there are not enough previously viewed items to display. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE] {class="- topic/note "}
>
>If you are running a recommendation and change its criteria, you will lose your reporting data.

You can also use additional known information about a visitor to enhance your recommendations.

All one-day criteria run twice daily. All one-week and longer criteria run once daily. Site Affinity criteria run once daily. Backup criteria run twice daily.

## Viewing Criteria Information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

You can view criteria details on a pop-up card by hovering over a card and by clicking the Information icon on a criteria card without opening the criteria.

![](assets/criteria_hover.png)

Click the **[!UICONTROL Algorithm Info]** tab to view general information about the selected criteria, including its Name, Descriptions, Industry Vertical, Page Type(s), Recommendation Key, Recommendation Logic, and Algorithm ID.

![](assets/criteria_info.png)

Click the **[!UICONTROL Algorithm Usage]** tab to view a list of activities that reference the selected criteria. The card lists active and inactive activities. Click the Live Activities or Inactivities drop-down lists to view the entire list of activities that reference that criteria. You can click the activity link to open the activity for editing.

![](assets/criteria_usage.png)

## Determining When Criteria Results are Ready to Display {#section_03F328C07F234692B6D996DF745584B3}

From the activity diagram, Criteria cards now indicate when results are ready to display. Knowing if results are ready to display helps you determine if your activity is ready to activate to push it live. Knowing if results are ready to display also helps you know if there are any issues with the criteria.

>[!NOTE]
>
>For a discussion about load times, see "Expected Criteria Processing Time" in [Creating Criteria](../../c-recommendations/c-algorithms/t-create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

The following illustration shows the activity diagram on a Recommendations activity's Overview page. You can also see the activity diagram with criteria status results from step 2 during the activity-creation workflow.

![](assets/criteria_status.png)

Status results include the following: Results Ready, Results Not Ready, and Feed Failure, as illustrated in the following diagram:

![](assets/criteria_status_multi.png)

