---
description: The Automated Personalization activity workflow varies from the workflow
  of the other activity types.
keywords: automated personalization;Audiences;ensemble;random forest;residual variance;error
  variance;lifetime value
seo-description: The Automated Personalization activity workflow varies from the workflow
  of the other activity types.
seo-title: Create an Automated Personalization activity
solution: Target
title: Create an Automated Personalization activity
title-outputclass: premium
topic: Advanced
uuid: 7d301dc3-6076-4e05-8abc-4978075a881e
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Create an Automated Personalization activity{#create-an-automated-personalization-activity}

The Automated Personalization activity workflow varies from the workflow of the other activity types.

1. From the Target Standard Activities list, click **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**.

   ![](assets/ap_create.png)

1. Specify the desired channel: Web.

   You can also choose Mobile App, Email, or Other/API.

1. To use the Visual Experience Composer (VEC), click **[!UICONTROL Visual (Default)]**.

   If you prefer to use the Form-Based Experience Composer, select **[!UICONTROL Form]**.

   For more information about both composers, see [Experiences](../../c-experiences/c-experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).
1. Verify or enter the activity URL, then click **[!UICONTROL Next]**.

   >[!NOTE]
>
>[!DNL Target] does not differentiate between URL protocols ( [!DNL https] and [!DNL http]). As a result, [!DNL `http://www.adobe.com`] and [!DNL `https://wwww.adobe.com`] both match.

   The page with the specified URL opens in the Visual Experience Composer.

   ![](assets/ap_url.png)

   For troubleshooting information about the VEC, should you have problems, see [Troubleshooting the Visual Experience Composer](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/r-troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).
1. To name the activity, click the Name field and type your activity name.

   ![](assets/ab_newname.png)

   The following characters are not allowed in an activity name:

   <table id="table_F5E365667FDC48AD8B4461E40CD669B8"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Character </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>/ </p> </td> 
      <td colname="col2"> <p>Forward slash </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>? </p> </td> 
      <td colname="col2"> <p>Question mark </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p># </p> </td> 
      <td colname="col2"> <p>Number sign </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>: </p> </td> 
      <td colname="col2"> <p>Colon </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>= </p> </td> 
      <td colname="col2"> <p>Equals to </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>+ </p> </td> 
      <td colname="col2"> <p>Plus </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>- </p> </td> 
      <td colname="col2"> <p>Minus </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>@ </p> </td> 
      <td colname="col2"> <p>At sign </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Modify page elements as explained in [Experiences](../../c-experiences/c-experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), then click **[!UICONTROL Next]**.

   You can select multiple images at once from the asset manager. This enables you to quickly view the page with each of the images configured for the activity. You can also easily edit text elements in your offers. When you edit an element, bars appear on that element to indicate you have changed it.

1. Click **[!UICONTROL Manage Content]** to configure the available combinations.

   A dialogue box appears with three options at the top of the screen: Experiences, Offers, and Exclusion Groups.

   ![](assets/ap_content.png)

   >[!NOTE]
>
>Although you can create up to 30,000 experiences in an AP activity, the activity performs best when fewer than 5,000 experiences are used.

   The [!UICONTROL Experiences] list shows each piece of content selected for the activity and the location it is assigned to. You can exclude specific experiences by hovering over the desired experience and then clicking the exclude icon, or you can batch exclude/include experiences by selecting the checkbox for the relevant experiences and then click the Exclude icon in the top right corner of the dialogue box.

   ![](assets/ap_content_batch_exclude.png)

   You can filter this list view to see only excluded or only included activities by clicking the **Status** drop-down list..
1. Click **[!UICONTROL Offers]** to select pieces of content and assign them to [reporting groups](../../c-reports/c-offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C).

   Use the [!UICONTROL Location] list to filter offers by location. Use the [!UICONTROL Report Group] list to filter offers by reporting groups. You can also use the [!UICONTROL Report Group] list to filter for [!UICONTROL Unassigned Offers] so you can assign a reporting group to an offer that is not currently assigned to any reporting group.

   You can add specific experiences to a reporting group by hovering over the desired offer and then clicking the folder icon, or you can batch include experiences in a reporting group by selecting the checkbox for the relevant experiences and then click the Reporting Group folder icon button in the top right corner of the dialogue box.

   ![](assets/report_group.png)

   It is important to understand that reporting groups impact how Target builds its models. As a result, we recommend that you use reporting groups only if you plan to replace or add new offers while the activity is live. If a new offer is introduced into a live activity, putting the new offer into a group with existing similar offers allow the machine to use the data already collected for the other offers in its group to learn about the new offer. You should never put all offers into a single reporting group.

   For information about targeting an offer to specific audiences, see [Target AP Offers](../../c-activities/t-automated-personalization/t-ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).
1. (Conditional) Click **[!UICONTROL Offers]** to select pieces of content and assign them to reporting groups or only allow certain visitors to see certain offers with targeting.

   For more information, see [Offer Reporting Groups in Automated Personalization](../../c-reports/c-offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C).

   For information about targeting an offer to specific audiences, see [Target Automated Personalization Offers](../../c-activities/t-automated-personalization/t-ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combinations of elements that you want to exclude from the activity.

   ![Step Result](assets/exclusion_groups.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group and click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.
1. Click **[!UICONTROL Next]** when you have finished setting up the content of your activity.
1. The **Targeting** step will look familiar if you have used other Target activity types. Here you can select an audience and specify the percentage of visitors who will see the control experience by clicking the **[!UICONTROL Custom Allocation]** drop-down list, then click **Next**.

   The [!UICONTROL Custom Allocation] drop-down list lets you choose from the following options:

   ![](assets/split-ap.png)

   * **Evaluate Personalization Algorithm (50/50):** If your goal is to test the algorithm, use a 50/50 percent split of visitors between the control and the targeted algorithm. This split gives the most accurate estimate of the lift.
   * **Maximizing Personalization Traffic (90/10):** If your goal is to create an “always on” activity, put 10% of the visitors into the control to ensure there is enough data for the algorithms to continue learning over time. Note the tradeoff here is that in exchange for personalizing a larger proportion of your traffic, you will have less precision in what the exact lift is.
   * **Custom Allocation** Manually split the percentage as desired.
   The control experience provides a comparison to determine how much lift is provided by the automated test.

   Automated Personalization always measures performance against a control group. Best practice is to place at least 10% of entrants into the control group. If your goal is to test if the personalization algorithm on the data it is given performs better than no personalization (i.e. the randomly served control), then a 50/50 percent traffic split between the control and the personalization algorithm would be the fastest and most accurate way to achieve this goal. If you want to maximize the amount of traffic that is personalized and you are less concerned with understanding the exact lift your activity is generating, then a 10/90 percent traffic split between the control and the personalization algorithm would be the fastest and most accurate way to achieve this goal.

   >[!NOTE]
>
>In Automated Personalization activities, entry criteria (URL targeting, template rules, and audience target) are evaluated for each request. In previous versions, entry criteria were evaluated once per session.

1. Click **[!UICONTROL Continue]** to display the **[!UICONTROL Goals & Settings]** page.
1. Configure the activity with the following settings, then click **[!UICONTROL Save & Close]**.

   <table id="table_136C5D05E9A544C6977050EC50B9F49B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Setting </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Name </td> 
      <td colname="col2"> <p>Name the activity. Give the activity a name that is descriptive enough that team members can recognize it in the Activities list. </p> <p>The following characters are not allowed in an activity name: </p> <p> 
      <ul id="ul_5710602E3CF24EAD9C2C6BF10B83841F"> 
         <li id="li_1E06CC79069F4A3C825FAEB5C32F6C9F"> / </li> 
         <li id="li_0C716E01A8C74BE7BF540D21A249E692">? </li> 
         <li id="li_924D064F365C45B8B0F8AC15A23ABE3D"># </li> 
         <li id="li_E9F2F644FC5C4E9B91101745590DD6D8">: </li> 
         <li id="li_8EBFDC2985E445D49B9627F8DB32DF5A">= </li> 
         <li id="li_2BDACF8A11DC4023AF6586FD7AFC305E">+ </li> 
         <li id="li_7431D6F4017349BEA91D352F6836F28F">- </li> 
         <li id="li_9A475E8CBC8F4AB997D3662F405D3790">@ </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Objective </td> 
      <td colname="col2"> (Optional) Type the objective of the test. The objective helps you remember the purpose of the activity. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Priority </td> 
      <td colname="col2"> <p>Depending on your settings, the UI and options for <span class="wintitle"> Priority</span> vary. You can use the legacy settings of Low, Medium, or High, or you can enable fine-grained priorities from 0 to 999. </p> <p>The priority is used if multiple activities are assigned to the same location with the same audience. If two or more activities are assigned to the location, the activity with the highest priority displays. </p> <p>If this option is not enabled in <span class="wintitle"> Setup</span> (the default), specify a priority: Low, Medium, or High. </p> <p> To enable fine-grained priorities, click <span class="wintitle"> Setup</span>, then toggle the <span class="wintitle"> Enable Fine-Grained Priorities</span> option to the "On" position. </p> <p>If this option is enabled, specify a value between 0 and 999: </p> <p> 
      <ul id="ul_FCA07A04D6F248759429BC46BA57CCE5"> 
         <li id="li_88F440506D22467295C71F2B14470AD7"> <p>0 = Low </p> </li> 
         <li id="li_AEC7893759464944A6501FA742A2B0FE"> <p>999 = High </p> </li> 
      </ul> </p> <p>For activities created in previous versions of <span class="keyword"> Target Standard/Premium</span>, Low priority is converted to 0, Medium is converted to 5, and High is converted to 10. You can adjust these values as necessary. </p> <p> <p>Note:  Before you can disable this option after using fine-grained priories, all priorities must be set back to 0, 5, and 10. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Duration </td> 
      <td colname="col2"> Set the start and end dates for the activity. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Optimization Goal </td> 
      <td colname="col2"> <p>Specify the optimization goal, which consists of two parameters: </p> <p> 
      <ul id="ul_F6238CFA3890414DAADB6896E17653B8"> 
         <li id="li_5366B2CCA42041F38C2B3888BEE3F7E8">What you want to measure with the activity </li> 
         <li id="li_A77B6CFF0A7E46EB9675CA5B4D22CAF3">The action taken by an activity entrant that shows that the goal has been achieved. </li> 
      </ul> </p> <p>You can choose to name the optimization goal by selecting the three dots to the right of My Primary Goal. Automated Personalization activities can measure conversion, RPV, and AOV. Conversion can be achieved by viewing a page or viewing an mbox. Clicks can also be tracked. </p> <p>The primary goal also becomes the modeling metric, used by the modeling system to calculate the success of the experience. </p> <p>Visitors can be kept in the activity for tracking purposes after reaching the modeling goal. For example, often an Automated Personalization activity is used to improve click-rates, and that is set as the modeling goal. However, it's important to see how increased click-rates lead to final conversion, so tracking through the final conversion is essential. </p> <p>You can provide dependency on multiple metrics along with the flexibility to choose whether the metric should be reached or not reached for the count to increase. </p> <p>You must define both (or multiple) success metrics before you can make one dependent on another. </p> <p>The <span class="wintitle"> Add Dependency</span> option allows the success metric to increment if another success metric has been reached or has not been reached. </p> <p>To add a dependency: </p> <p> 
      <ol id="ol_7CE86C31CD5541039A3265E14D0C3630"> 
         <li id="li_3E374D8B28B443FA9FE8AF2B02814A82"> <p>After adding additional metrics, click <span class="uicontrol"> Advanced Settings</span> under the three-dot menu to the right of Additional Goal. </p> </li> 
         <li id="li_F65C369C8F354A6CBD447ED26D9F79E4"> <p>Click the <span class="uicontrol"> Add Dependency</span> option. </p> <p><img id="image_F941ADB2FDC441C2B72FCDBD393FD8A0" href="assets/add_dependency.png" /> </p> </li> 
         <li id="li_9A6F187B4C294A9C8B5C834C76B32767"> <p>Drag and drop the desired metrics from the left pane into the right pane, then click <span class="uicontrol"> Reached</span> to toggle the setting between <span class="uicontrol"> Reached</span> and <span class="uicontrol"> Not Reached</span>. </p> <p><img href="assets/add_dependency_reached.png" id="image_CA136FD10D754BD1B26C621DF2A4858D" /> </p> </li> 
      </ol> </p> <p>You can edit or remove dependencies after adding them. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Conversion Metric </td> 
      <td colname="col2"> <p> The conversion metric for Automated Personalization activities is always the same as the optimization goal. There is no input required in this section. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Additional Metrics </td> 
      <td colname="col2"> <p>Add any additional reporting metrics you want to use. You can add conversion or revenue metrics. </p> <p> <p>Note:  The Engagement metric is not supported as an additional metric as well. The UI might let you select the Engagement metric, but data will not display accurately in reports. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Audiences for Reporting </td> 
      <td colname="col2"> <p>Add audiences to enable filtering by audiences in reports. By default, the report shows results for all qualified visitors. Add audiences to filter results for more specific subsets of visitors. </p> <p> <p>Note:  Unlike other activity types, Automated Personalization cannot use Adobe Analytics as its reporting source. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Notes </td> 
      <td colname="col2"> Type any information about your activity that is useful to keep on hand for yourself or other team members. The Notes pane is re-sizable. </td> 
   </tr> 
   </tbody> 
   </table>

   Note that when you name or rename a metric, the following characters are not allowed:

   <table id="table_71C27F648627451F95D533EDB4C31392"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Character </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>/ </p> </td> 
      <td colname="col2"> <p>Forward slash </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>? </p> </td> 
      <td colname="col2"> <p>Question mark </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p># </p> </td> 
      <td colname="col2"> <p>Number sign </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>: </p> </td> 
      <td colname="col2"> <p>Colon </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>= </p> </td> 
      <td colname="col2"> <p>Equals to </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>+ </p> </td> 
      <td colname="col2"> <p>Plus </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>- </p> </td> 
      <td colname="col2"> <p>Minus </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>@ </p> </td> 
      <td colname="col2"> <p>At sign </p> </td> 
   </tr> 
   </tbody> 
   </table>

After you click **[!UICONTROL Create]**, the Activity Summary appears. Click **Preview Experiences** to preview how your experiences will look when delivered. A pop-up appears that you can use to view and share links to your AP experiences on your site to get a "true preview" of the experiences outside of Target's Visual Experience Composer. You must share the links from the message to share the preview. Clicking a link and then copying the URL directly from the page won't work because the URL contains a parameter that only displays the page correctly when you access the page from the link in the message.

For information about reporting, see [Automated Personalization Reports](../../c-reports/c-reports-ap.md#concept_C02BAFC922114A44846998FD956E345A).
