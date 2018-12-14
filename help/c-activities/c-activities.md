---
description: Activities let you test page designs and target content to specific audiences.
keywords: activities list;activities;activity;activity types;edit activity;activity
  actions;activity attribute;activity list filter;activity limitations
seo-description: Activities let you test page designs and target content to specific
  audiences.
seo-title: Activities
solution: Target
title: Activities
topic: Standard
uuid: 89dca5b4-c23d-4dfa-8f13-f1b05c7ab22c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Activities{#activities}

Activities let you test page designs and target content to specific audiences.

## Training Videos {#section_BE80D13A2E81460C885F902010E1AD87}

The Activity Types video (9:03) explains the activity types available in [!DNL Target Standard/Premium].

* Describe the types of activities included in [!DNL Adobe Target]
* Select the appropriate activity type to achieve your goals
* Describe the three-step guided workflow that applies to all activity types

>[!VIDEO](https://www.youtube.com/watch?v=vtHg1pPFJp8)

The Managing Activities video (5:55) explains how to use the Activities list to manage activities.

* Define the term *activity*
* Find activities in the Activities list
* Edit, deactivate, copy, and delete activities

>[!VIDEO](https://www.youtube.com/watch?v=tBSHwZaFhag)

## Activities List {#section_DE8E2DB30D534962A931EF8BB48240F5}

The [!UICONTROL Activities] list provides an overview of all activities.

The Activities list displays the following information:

<table id="table_4DB3713F5206493FBD57D30D8BD11E85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Type </td> 
   <td colname="col2"> <p>The activity type, such as A/B or MVT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> <p>The name of the activity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Objective </td> 
   <td colname="col2"> <p>The objective appears in lighter text next to the name. If the objective is too long for your screen width, it is truncated. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL </td> 
   <td colname="col2"> <p>The URL appears in lighter text below the name. </p> <p>The URL for the activity identifies where the activity is displayed. This helps you quickly identify an activity, and determine whether a particular page already has a test running on it. </p> <p>If a test runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity. </p> <p>You can search based on URL. Use the drop-down list next to search box and select <span class="wintitle"> Search UR</span>L. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Status </td> 
   <td colname="col2"> <p>The status of the activity can be one of the following: </p> <p> 
     <ul id="ul_D31DFDD0E0AD41F097236C9202DDE384"> 
      <li id="li_664243F4A20F4B0E9B033792211F43F6"> <p><b>Live:</b> The activity is currently running. </p> </li> 
      <li id="li_A4DF01C567C34F7EBC6FC150CAA44349"> <p><b>Draft:</b> The activity setup has started but the activity is not yet ready to run. </p> </li> 
      <li id="li_A7D52E4F2108488083B6F8F202387607"> <p><b>Scheduled:</b> The activity is ready to be activated when the specified start date and time arrives. </p> </li> 
      <li id="li_EDA16612A2174A7DA5EF5B26259BF88B"> <p><b>Inactive:</b> The activity has been paused or deactivated. </p> </li> 
      <li id="li_AA0ACF08202447CEA78C9B3C38325AB0"> <p><b>Syncing:</b> The activity has been saved and is being synced to the Target delivery network. </p> </li> 
      <li id="li_10D935F6E27D4CE4AA9D050AF4BF198F"> <p><b>Ended:</b> The specified end date and time of activity has reached and the activity is no longer being served. </p> </li> 
      <li id="li_114739D0482F4860B82FB1F419862851"> <p><b>Archived:</b> The activity has been archived. You can activate an archived activity to use it again. </p> </li> 
     </ul> </p> <p> <p>Note:  When you perform certain actions, such as activating an activity outside of the UI using API methods, the update can take up to ten minutes to propagate to the UI. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Source </td> 
   <td colname="col2"> <p>Shows where the activity was created: </p> <p> 
     <ul class="simplelist"> 
      <li> Adobe Target </li> 
      <li> Adobe Target Classic </li> 
      <li> Adobe Experience Manager (AEM) </li> 
      <li> Adobe Mobile Services (AMS) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estimated Lift in Revenue </td> 
   <td colname="col2"> <p>Shows the predicted increase in revenue if 100% of the audience sees the winning experience. </p> <p>Calculated using the following formula: </p> <p> (&lt;winning experience> - &lt;control experience>)*&lt;total number of visitors> </p> <p>This number is rounded to one decimal place, maximum, if the condensed form has only a single digit before the decimal. For example: $1.6M, $60K, $900, $8.5K, $205K </p> <p>This column shows "---" for activities that do not have enough data to call a winner show or do not have a cost estimate. </p> <p>See <a href="../administrating-target/r-target-account-preferences/c-estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE" format="dita" scope="local"> Estimating Lift in Revenue</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Last Updated </td> 
   <td colname="col2"> <p>The date when the activity was last updated, and by whom. </p> </td> 
  </tr> 
 </tbody> 
</table>

Mouse over an activity to see the available actions. Possible actions include:

<table id="table_B68BB1AD61394C749822FF4938E404E7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Action </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Edit </p> </td> 
   <td colname="col2"> <p>Change the activity. Any activity can be edited. </p> <p>For more information about the various ways you can edit activities, see <a href="../c-activities/c-edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0" format="dita" scope="local"> Edit an Activity</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deactivate </p> </td> 
   <td colname="col2"> <p>Stop a live or scheduled activity. A deactivated campaign can be reactivated or archived. </p> <p>If you deactivate or archive an activity and then later reactivate it, a visitor will continue being a part of that activity after the reactivation if they were in it before it was deactivated or archived. Any conversion metrics recorded during the time between the two events won't be attributed to that activity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activate </p> </td> 
   <td colname="col2"> <p>Start an inactive or ready activity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archive </p> </td> 
   <td colname="col2"> <p> Send the activity to the archive. By default, archived activities no longer appear in the Activities list. Change the filter for the activities list to include archived activities to see them. You can activate an archived activity to use it again. </p> <p>If you deactivate or archive an activity and then later reactivate it, a visitor will continue being a part of that activity after the reactivation if they were in it before it was deactivated or archived. Any conversion metrics recorded during the time between the two events won't be attributed to that activity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copy </p> </td> 
   <td colname="col2"> <p>Copy an activity. Any activity can be copied. Copying an activity creates a new activity with the same name, appended with "Copy." For example, a test called "Browser Offers" is copied to "Browser Offers Copy." </p> <p> Visual offers are copied with the activity. You can safely edit the offers in the copy without impacting the original activity. The only exception is saved offers and images in the Content/Assets folder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Delete </p> </td> 
   <td colname="col2"> <p>Delete a draft or ready activity. Deleted activities cannot be recovered. </p> </td> 
  </tr> 
 </tbody> 
</table>

Note the following details about the Activity list:

* Archived and ended activities do not appear in the [!UICONTROL Activities] list. To view these activities, filter them using the advanced filter settings on left rail.
* As soon as an activity originally created in [!DNL Target Classic] is deactivated or deleted, it is deleted from [!DNL Target Standard/Premium]. Deleted activities originally created in [!DNL Target Classic] are not sent to the [!UICONTROL Archive] folder in [!DNL Target Standard/Premium]. The archived folder functionality applies only to activities created in [!DNL Target Standard/Premium].
* All activity types other than [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate], and [!UICONTROL Auto-Target] give you the choice to use either [!DNL Target] or [!DNL Adobe Analytics] as the data source. [!UICONTROL AP], [!UICONTROL Auto-Allocate], and [!UICONTROL Auto-Target] *always* use [!DNL Target] data.
* Activities are available to several channels:

   * Web and mobile sites
   * Internet-connected screens and devices, including kiosks and ATMs
   * Email and other acquisition channels or partner sites
   * Mobile apps
   * Anywhere else you can deliver tagged content

## Sorting and Filtering the Activities List {#section_41DAD479FFF740E2BB67BF4825955670}

By default, the list is sorted by the date the activity was last modified, with the most recent on top. However, there are several filtering options to help you customize the list to show the activities you want to see.

**Search**

Use the search field to search for activities that match your search criteria.

![](assets/activities_search.png)

The search field includes a drop-down menu to help you narrow your search by specifying one of the following search filters: [!UICONTROL Activity Name] and [!UICONTROL URL].

**Activity List Filters**

You can determine which activities appear in your Activities list by selecting list filters.

![](assets/activities_filters.png)

You can filter by the following options. In each category, if nothing is selected, the default is All.

<table id="table_7C6A39CDD9E84084BE59C92BE17E4254"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filter Category </th> 
   <th colname="col2" class="entry"> Filter </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Type </p> </td> 
   <td colname="col2"> <p>A/B Test: A/B Test Manual, Auto-Allocate, and Auto-Target. </p> <p>Automated Personalization </p> <p>Experience Targeting </p> <p>Multivariate test </p> <p>Recommendations </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Live </p> <p>Draft </p> <p>Scheduled </p> <p>Inactive </p> <p>Syncing </p> <p>Ended </p> <p>Archived </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reporting Source </p> </td> 
   <td colname="col2"> <p>Target </p> <p>Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Composer </p> </td> 
   <td colname="col2"> <p>Visual </p> <p>Form-Based </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrics Type </p> </td> 
   <td colname="col2"> <p>Conversion </p> <p>Revenue </p> <p>Engagement </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activity Source </p> </td> 
   <td colname="col2"> <p>Adobe Target </p> <p>Adobe Target Classic </p> <p>Adobe Experience Manager </p> <p>Adobe Mobile Services </p> </td> 
  </tr> 
 </tbody> 
</table>

**Sort by Activity Attribute**

Click one of the following headings to toggle whether the activities are listed in ascending or descending order according to the selected heading.

* Activity Name
* Activity Type

## Tips and Tricks {#section_F77F30A246A14B538D9363B7F3639F97}

Get the most out of Adobe Target by learning more about various features and see why you should give them a try. The Tips and Tricks feature provides links to videos, use-cases, blogs, documentation, and much more.

The Tips and Tricks feature displays periodically on the Activities list page. After you read or dismiss a tip, it does not display again until the next tip is available. You can optionally disable all tips from displaying by clicking the Help icon > [!UICONTROL Disable Tip of the Day].

![](assets/tip-disable.png)

## Limitations {#section_049D4684403A4E07B998067EB8E9BE56}

Each Target activity has the following content limitations:

<table id="table_2BC0CCAEA2E24A298298E8456BE92642"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Limit </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Unique selectors </p> </td> 
   <td colname="col2"> <p>300 </p> <p>if a selector is repeated in a different experience, it is counted once. However, if it is repeated in the same experience, it is counted again. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Offers in each experience </p> </td> 
   <td colname="col2"> <p>350 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Click track selectors in metrics </p> </td> 
   <td colname="col2"> <p>50 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mboxes in metrics </p> </td> 
   <td colname="col2"> <p>50 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audiences and locations </p> </td> 
   <td colname="col2"> <p>50 </p> <p>Audiences and locations (mbox) combination should not be more than 50. </p> </td> 
  </tr> 
 </tbody> 
</table>

If you exceed any of these limits, the activity cannot be saved.

Increasing the numbers of these items in your activity also increases the length of time it takes to synchronize the activity across Target.

For additional limits of the Visual Experience Composer, see [Visual Experience Composer Limitations](../c-experiences/c-visual-experience-composer/c-experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attributes Imported into Target for Activities Updated Outside of Target {#section_802B0D174E6A44E1A96F404CA81AAE44}

If activities created in [!DNL Target] are updated from outside of [!DNL Target] (for example, via Adobe I/O), the following activity attributes are imported back into [!DNL Target]:

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

This import job will run when the activities page is opened, with a maximum delay of ten minutes. (KB-1526)
