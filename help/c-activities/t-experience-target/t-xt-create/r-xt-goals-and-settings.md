---
description: The Goals and Settings page is where you enter information about the
  goals of the test.
keywords: activity settings;experience targeting goals and settings;xt goals and settings;experience
  targeting;reporting settings;goal metrics;success metrics;dependent success metrics;advanced
  settings;primary goal;additional metrics;objective;priority;duration;reporting solution;goal;audiences
  for reporting;Which success metric must be reached before incrementing this metric;What
  will happen after a user encounters this goal metric;notes
seo-description: The Goals and Settings page is where you enter information about
  the goals of the test.
seo-title: Goals and Settings
solution: Target
title: Goals and Settings
topic: Standard
uuid: e8cd1881-9b08-4c90-b2fc-ec60fee17697
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Goals and Settings{#goals-and-settings}

The Goals and Settings page is where you enter information about the goals of the test.

* Activity Settings
* Reporting Settings
* Other Metadata

**Activity Settings (3:02)**

This video includes information about activity settings.

* Enter an objective for your activity
* Set the priority level of your activities
* Schedule activity start and end times
* Add audiences for reporting to create report filters
* Enter notes for your activities

>[!VIDEO](https://www.youtube.com/watch?v=6XNEM8tUADo)

The available settings depend on whether you use Target or Analytics as the data source.

![](assets/ab_settings.png)

## Activity Settings {#section_DCBDC354261F420EBD4B43EA34947BAC}

<table id="table_464BE186EE1F463DA99D16FC482A4AFA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Settings </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Objective </td> 
   <td colname="col2"> <p>Type an optional objective. The objective can be any information that helps you and your team members identify the campaign. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Priority </td> 
   <td colname="col2"> <p>Depending on your settings, the UI and options for <span class="wintitle"> Priority </span> vary. You can use the legacy settings of Low, Medium, or High, or you can enable fine-grained priorities from 0 to 999. </p> <p>The priority is used if multiple activities are assigned to the same location with the same audience. If two or more activities are assigned to the location, the activity with the highest priority displays. </p> <p>If this option is not enabled in <span class="wintitle"> Setup </span> (the default), specify a priority: Low, Medium, or High. </p> <p> To enable fine-grained priorities, click <span class="wintitle"> Setup </span>, then toggle the <span class="wintitle"> Enable Fine-Grained Priorities </span> option to the "On" position. </p> <p>If this option is enabled, specify a value between 0 and 999: </p> <p> 
     <ul id="ul_FCA07A04D6F248759429BC46BA57CCE5"> 
      <li id="li_88F440506D22467295C71F2B14470AD7">0 = Low </li> 
      <li id="li_AEC7893759464944A6501FA742A2B0FE">999 = High </li> 
     </ul> </p> <p>For activities created in previous versions of <span class="keyword"> Target Standard/Premium </span>, Low priority is converted to 0, Medium is converted to 5, and High is converted to 10. You can adjust these values as necessary. </p> <p> <p>Note:  Before you can disable this option after using fine-grained priories, all priorities must be set back to 0, 5, and 10. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duration </td> 
   <td colname="col2"> <p>The activity can start when approved, or you can set a specific date and time. Likewise, the activity can either end when it is deactivated or you can set a date and time. The time picker uses a 24-hour clock, with 00:00 being midnight. The time zone is set to the time zone configured in your browser. To use a different time zone, set your browser to another time zone and restart the browser. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Reporting Settings {#section_13119392051044FBA6387D9B3B1C43CF}

<table id="table_178993EC689C4C538F3EC7E3FC205592"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Settings </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reporting Solution </td> 
   <td colname="col2"> <p>Specify whether data is collected from Adobe Target or from Adobe Analytics. See <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html" format="https" scope="external"> Adobe Analytics as the Reporting Source for Target </a> to learn about the differences between the reporting solutions and the advantages of each. </p> <p>When selecting Analytics as the reporting source for Target, you select an Analytics report suite to receive Target activity data. To do this, first choose from any of the Analytics companies your account is tied to, and then select the appropriate report suite for the activity. Only report suites that are provisioned to connect to Adobe Target will be available for selection. If you don't see the report suite(s) you expect, first try logging out and logging back in to the Adobe Experience Cloud to try again. If the report suite is still missing from the list, please contact Customer Care. </p> <p>Analytics for Target requires a tracking server to report results correctly. A default tracking server will appear in the Tracking Server field. If you use more than one tracking server, you should check to ensure you include the correct tracking server in this field. See <a href="../../../c-integrating-target-with-mac/a4t/t-analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823" format="dita" scope="local"> Using an Analytics Tracking Server </a> for more information. </p> <p>If a reporting solution is specified in your account settings, the specified solution is used and this setting is not visible. </p> <p> <p>Note:  You cannot change your reporting source after the activity goes live in order to keep reports consistent. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Goal </td> 
   <td colname="col2"> <p>Select the action taken by a visitor to achieve the goal. For example, choose a Conversion metric, then set the parameters that determine when success is achieved. </p> <p>For more information about setting metrics, see <a href="../../../c-activities/t-test-ab/t-test-create-ab/t-ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB" format="dita" scope="local"> Set Metrics </a>. </p> <p> <p>Note:  If the reporting solution is set to Analytics, the only available goal metric is Conversion. Analytics metrics cannot be selected as a goal. </p> </p> <p>When you select your success metric, a selector displays. Use this selector to choose the specifics for the success metric. </p> <p>If enabled, the Estimated Value of the Conversion field (not available for the Page Score metrics) provides a value for your goal, but not for other metrics. This value enables Target to calculate an estimated lift in revenue. This field is optional; however, incremental revenue for any non-revenue metric cannot be calculated without it. For all revenue metrics (Revenue per Visitor, Average Order Value, Total Sales, and Orders), the estimate uses Revenue per Visitor. The data type is currency. </p> <p> After reaching the activity goal, a visitor continues to see the activity content, unless that visitor qualifies for a higher priority activity. If the visitor reaches the goal again, it is counted as another conversion. Note that this is different than the default behavior in Target Classic, which counts visitors as new if they see the test again. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Additional Metrics </td> 
   <td colname="col2"> <p>Create additional success metrics. </p> <p>This setting is not available if the reporting solution is set to Analytics. In this case, the metrics defined for the Analytics report suite are applied. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Audiences for Reporting </td> 
   <td colname="col2"> <p>By default, reports show results for all qualified visitors. You can add report audiences to show only information about specific audiences. </p> <p>This setting is not available if you choose Analytics as your reporting solution. The audience defined for the Analytics report suite are applied. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Advanced Settings {#section_E2FE441AFB324E498793ABB025ED9974}

Advanced settings are available for Experience Targeting goal metrics.

![](assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>If you use Adobe Analytics as your reporting source, settings are managed by the Analytics server. The advanced settings option will not be available.

<table id="table_5706360D23704F16AA18597D4C8F3438"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Which success metric must be reached before incrementing this metric? </td> 
   <td colname="col2"> <p>Use this option to only count someone as reaching the success metric if they’ve previously reached a different success metric. For example a test conversion might only be valid if the visitor clicks on the offer, or reaches a particular page before converting. </p> <p>You can provided dependency on multiple metrics along with the flexibility to choose whether the metric should be reached or not reached for the count to increase. </p> <p>You must define both (or multiple) success metrics before you can make one dependent on another. </p> <p>The <span class="wintitle"> Add Dependency </span> option allows the success metric to increment if another success metric has been reached or has not been reached. </p> <p>To add a dependency: </p> <p> 
     <ol id="ol_7CE86C31CD5541039A3265E14D0C3630"> 
      <li id="li_3E374D8B28B443FA9FE8AF2B02814A82"> <p>After adding additional metrics, click <span class="uicontrol"> Advanced Settings </span>. </p> </li> 
      <li id="li_F65C369C8F354A6CBD447ED26D9F79E4"> <p>Click the <span class="uicontrol"> Add Dependency </span> option: </p> <p> <img href="assets/add_dependency.png" id="image_D3C6E4862509435E86A1F61B88F342CA" /> </p> </li> 
      <li id="li_9A6F187B4C294A9C8B5C834C76B32767"> <p>Drag and drop the desired metrics from the left pane into the right pane, then click <span class="uicontrol"> Reached </span> to toggle the setting between <span class="uicontrol"> Reached </span> and <span class="uicontrol"> Not Reached </span>. </p> <p> <img href="assets/add_dependency_reached.png" id="image_CA136FD10D754BD1B26C621DF2A4858D" /> </p> </li> 
     </ol> </p> <p>You can edit or remove dependencies after adding them. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> What will happen after a user encounters this goal metric? </td> 
   <td colname="col2"> <p>There are three options for what happens after a visitor reaches the goal metric: </p> 
    <ul id="ul_2347FFB59E804DB382C3440BE684000E"> 
     <li id="li_5A8C13D4D43C436786D9FBE24C701CE1">Select <span class="uicontrol"> Increment Count &amp; Keep User in Activity </span> to specify how the count is incremented. </li> 
     <li id="li_04D4A04310354FB4A7F23023E1FE0DE0">Select <span class="uicontrol"> Increment Count, Release User &amp; Allow Reentry </span> to specify the experience the user sees if they reenter the activity. </li> 
     <li id="li_32FEAFA4C6BC469998C9181792B29BEE">Select <span class="uicontrol"> Increment Count, Release User &amp; Bar from Reentry </span> to specify what the user sees instead of the activity content. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

See [Success Metrics](../../../c-activities/r-success-metrics/r-success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) for more information about advanced settings.

## Other Metadata {#section_2E8917BEFB954480A4206B9E9E917F80}

<table id="table_41D61740D4C246D695CE8B785B1785CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Settings </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Notes </td> 
   <td colname="col2"> <p>Type any information about your activity that is useful to keep on hand for yourself or other team members. The Notes pane is resizable. </p> </td> 
  </tr> 
 </tbody> 
</table>
