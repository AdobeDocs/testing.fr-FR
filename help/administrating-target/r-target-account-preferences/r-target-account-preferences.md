---
description: Set your account preferences to configure Target Standard or Target Premium
  to work correctly with your account.
keywords: account preferences;preferences;site details;custom mbox name;Experience
  Cloud solution used for reporting;Show estimated lift in revenue;css selectors;use
  element classes;Default Visual Experience Composer URL;Enable Enhanced Experience
  Composer;Generate Experience Snapshots;mobile viewport configuration;Industry Vertical;Filter
  Incompatible Criteria
seo-description: Set your account preferences to configure Target Standard or Target
  Premium to work correctly with your account.
seo-title: Preferences
solution: Target
subtopic: Getting Started
title: Preferences
topic: Standard
uuid: ed3904c8-533b-4b9c-a3a1-079c61b1bf2a
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Preferences{#preferences}

Set your account preferences to configure Target Standard or Target Premium to work correctly with your account.

**Account Preferences (7:33)**

This video includes information about account preferences.

* Describe the account settings available in Target Standard

>[!VIDEO](https://www.youtube.com/watch?v=MJXhgxlP-KI)

To set your account preferences, click **[!UICONTROL Setup]** > **[!UICONTROL Preferences]**, configure your preferences as desired, then click **[!UICONTROL Submit]**.

The following illustration shows the available settings on the [!UICONTROL Account Preferences] page.

![](assets/preferences.png)

Note that some of these preferences are available only if you have [!DNL Target Premium].

## Site Details {#section_04A3340FC29B46978DB77058259F4EE0}

Select the optional custom mbox name you are using to deliver Target activities. This global mbox must be empty, meaning it has no default content. Save this setting only after the updated [!DNL mbox.js] file is installed on your site.

>[!CAUTION]
>
>Configuring this setting incorrectly might result in an outage for existing activities.

## Results and Reporting {#section_47C887AABD704A96BCD1C00BEABF4BCE}

Set options that determine what data is used for your results and reports.

<table id="table_BEB1A223B87A4B87B713EA131D57BA48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud solution used for reporting </p> </td> 
   <td colname="col2"> <p>Select the reporting source for your activities, either <span class="keyword"> Target</span> or <span class="keyword"> Adobe Analytics</span>. You can also choose to select your reporting source per activity. </p> <p>Consider the following information as you choose your reporting source: </p> <p> 
     <ul id="ul_3A0F882B1297463A84428AD2585C2E17"> 
      <li id="li_9E8C841875074E0DAF6B70B5CF84A871"> <p>Auto-Allocate, Auto-Target, and Automated Personalization (AP) activity creation, activation, and deactivation are allowed irrespective of the reporting source selected. These activity types are not supported when you choose <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html" format="html" scope="external"> Adobe Analytics as the reporting source for Adobe Target (A4T)</a>. Even if you specify Analytics as your reporting source, Target is used as the reporting source for these activity types. </p> </li> 
      <li id="li_91EF8D3CE35B480D9AF9FCC425AE7E26"> <p>If the reporting source is set to <span class="wintitle"> Analytics</span> here, you are not allowed to activate an activity that uses Target as the reporting source (the reporting source is specified as Target per activity). You must change the reporting source to <span class="wintitle"> Analytics</span> in your activity or change the reporting engine to <span class="wintitle"> Select Per Activity</span> in <span class="wintitle"> Setup</span> > <span class="wintitle"> Preferences</span>. </p> </li> 
      <li id="li_048C31E452CD4B23AD61E36851FAEC23"> <p>If the reporting source is set to <span class="wintitle"> Target</span> here, you are not allowed to activate an activity that uses <span class="wintitle"> Analytics</span> as the reporting source. You must change the reporting source to <span class="wintitle"> Target</span> in your activity or change the reporting source to <span class="wintitle"> Select Per Activity</span> in <span class="wintitle"> Setup</span> > <span class="wintitle"> Preferences</span>. </p> </li> 
      <li id="li_C7A5359084C74781B729A07FC6AC6CF5"> <p>If the reporting source is set to <span class="wintitle"> Select Per Activity</span> here, you can create, activate, and deactivate activities that are supported by the selected reporting source. For a matrix of supported activities, see <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html" format="html" scope="external"> Adobe Analytics as the reporting source for Adobe Target (A4T)</a>. </p> </li> 
      <li id="li_F7BC2B9547EA49608AB54A42847C27C2"> <p>When you switch from A/B Manual to Auto-Allocate or Auto-Target, all metrics and reporting audiences are lost if the reporting source of the A/B Manual activity is not supported in Auto-Allocate or Auto-Target activities. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show estimated lift in revenue </p> </td> 
   <td colname="col2"> <p>You can also choose to show the estimated lift in revenue if you enter a monetary value for your goal. Target can estimate the revenue lift you would attain if all users view the winning experience. The estimated lift feature is disabled by default. </p> <p>Only Experience Cloud Admin users can enable or disable this feature. If estimated lift is disabled, the corresponding fields do not appear in the interface. Disabling the feature does not result in a loss of data, including the data used for your estimates. The estimates are based on data that is collected whether or not the feature is enabled. </p> <p>For detailed information, see <a href="https://marketing.adobe.com/resources/help/en_US/target/target/c_estimating_lift_in_revenue.html" format="https" scope="external"> Estimating Lift in Revenue</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CSS Selectors {#section_8155EDBF449E4198863235F94D1EA872}

Specify how Target generates CSS selectors.

These options help Target understand your site's structure to generate better CSS selectors for content delivery. By default, Target generates selectors based on element IDs on the page. If your site uses few IDs, or duplicates IDs on the same page, then using classes might be a better option.

You can choose one or both of the following options:

<table id="table_36A0F371B60E4FDC9F4559EE735FB32E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Use element IDs </p> </td> 
   <td colname="col2"> <p>Deselect this option if the same ID is used for multiple elements or if element ID might change on page load. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use element classes </p> </td> 
   <td colname="col2"> <p> By default, Target only uses element IDs. However, if your page is designed to use classes to identify elements, such as a page built with <span class="keyword"> Adobe Experience Manager</span>, you should also select <b>Use element classes</b>. </p> <p> <p>Note:  Although everything has been done to assure accuracy, be aware that using classes can result in errors. If you do not select either option, accuracy is also affected. The order of accuracy is IDs > classes > neither option. Always be sure to test your page to make sure the selectors are correct. </p> </p> <p>You can override this setting per activity (click the Settings gear icon, then select <span class="uicontrol"> CSS Selectors</span>). This is especially useful if you have multiple sites that are configured differently. </p> <p> <p>Note:  Overriding the setting per activity is not available in Automated Personalization and Multivariate Testing activities. </p> </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/target/target/c_vec_selectors.html" format="https" scope="external"> Element Selectors Used in the Visual Experience Composer</a> for additional information about selectors. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Visual Experience Composer {#section_CD9BDD372CF54E678F88E8BA95757A5A}

<table id="table_A27A5C9B0A23409DB85A2B145872B785"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Default Visual Experience Composer URL </p> </td> 
   <td colname="col2"> <p>Set the default URL used by the <span class="wintitle"> Visual Experience Composer</span>. This is the default page, such as your home page, used whenever you set up an experience for each new activity. If you do not set a default URL, you must enter a URL for each activity when you create it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enable Enhanced Experience Composer </p> </td> 
   <td colname="col2"> <p>Allows editing on iFrame-busting sites and sites with mixed content. Some sites may not be compatible with the enhanced version. Uncheck this option to revert to the original Experience Composer. Activity delivery on sites is not affected by this choice. </p> <p>For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/target/target/r_troubleshoot_composer.html" format="https" scope="external"> Troubleshooting the Visual Experience Composer</a>. </p> <p> <p>Note: You can also enable the <span class="wintitle"> Enhanced Experience Composer</span> at the activity level. For more information, see <a href="../../c-experiences/c-experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D" format="dita" scope="local"> Experiences</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generate Experience Snapshots </p> </td> 
   <td colname="col2"> <p>Enabling experience snapshots generates thumbnails for your experiences in the activity workflow diagram. Disabling snapshots might result in faster performance for some users. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mobile Viewport Configuration {#section_42176D062BCE4A28ADBB784CC4BEF84D}

You can add devices to use when previewing experiences. Each device has an associated audience.

<table id="table_C0C00E2BB1654B9AA38D71FE2A873262"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p class="premium">Add New </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Add New</span>, specify a descriptive name for the mobile viewport, specify the width and height, select the desired operating system, then click Save. </p> <p>For information about how to add a mobile viewport, see <a href="../../c-experiences/c-visual-experience-composer/c-mobile-viewports.md#task_B4B161499DC0470584ED922A4D20FCAB" format="dita" scope="local"> Mobile Viewport Configuration</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

