---
description: Audiences determine who will see content and experiences in a targeted
  activity.
keywords: audience;audience rules;create audience;creating audience;targeting audience;reporting
  audience;report audience;segment;custom profile parameters;audience definition;audiences
  list
seo-description: Audiences determine who will see content and experiences in a targeted
  activity.
seo-title: Create audiences
solution: Target
title: Create audiences
topic: Advanced,Standard,Classic
uuid: 994eed40-11ca-460e-827c-75a4db8a942d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Create audiences{#create-audiences}

Audiences determine who will see content and experiences in a targeted activity.

Audiences are used anywhere targeting is available. When targeting an activity, you can either select a reusable audience from the [!UICONTROL Audiences] list, create an activity-specific audience and target it, or [combine multiple audiences](../../c-target/c-combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) to create an ad hoc audience.

You can also use audience data collected by [!DNL Analytics] for real-time targeting and personalization in [!DNL Adobe Target] and other [!DNL Experience Cloud] solutions. See [Audiences in the Experience Cloud Product Documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html).

**Using Audiences (6:22)**

This video includes information about using audiences.

* Explain the term "audience"
* Explain the two ways audiences are used for optimization
* Find audiences in the Audiences List
* Target an activity to an audience
* Use audiences for passive reporting in an activity

>[!VIDEO](https://www.youtube.com/watch?v=TAMBpW9vpOI)

[!DNL Target] defines two types of audiences:

* **Targeting Audiences: **Used to deliver different content to different types of visitors.
* **Reporting Audiences: **Used to determine how different types of visitors respond to the same content so you can analyze your test results.

   In [!DNL Target], you can configure reporting audiences only if you use [!DNL Target] as your reporting source. If you use [ [!DNL Adobe Analytics] as your reporting source (A4T)](../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE), you must configure your reporting audiences within [!DNL Analytics].

To access the [!UICONTROL Audiences] list, click **[!UICONTROL Audiences]** in the top menu bar:

![](assets/audiences_list.png)

The [!UICONTROL Audiences] list contains all of the audiences that you can use in your activities. Use the [!UICONTROL Audiences] list to create, edit, delete, copy, or combine audiences. The list also shows the source where the audience was created ( [!DNL Target], [!DNL Target Classic], [!DNL Adobe Audience Manager (AAM),] [!DNL Experience Cloud], and so forth). Predefined audiences, such as "New Visitors" and "Returning Visitors," cannot be renamed.

When working with audiences that were originally created in AAM, Target alerts you if you reference an audience in Target activities that have later been deleted in AAM.

* If an audience was deleted in AAM, a warning icon in both the [!UICONTROL Audience] list and the audience picker displays. A tool-tip in the UI also indicates that the audience was deleted in AAM.
* If you attempt to combine multiple audiences with a deleted audience, or if you attempt to save an activity that references a deleted audience, a warning message displays.

You can also target custom profile parameters and `user.` parameters. When adding an audience, click **[!UICONTROL Visitor Profile]**, then under [!UICONTROL Custom User Parameters] or [!UICONTROL Custom Profile Parameters] in the [!UICONTROL Visitor Profile] drop-down list, choose the parameter you use want to use to target your activity. If the desired parameter does not appear, the parameter has not been fired by an mbox. Other custom mbox parameters are available in the [!UICONTROL Custom Parameters] drop-down list.

Use the search box to search your [!UICONTROL Audiences] list. You can search for any part of an audience name, or you can enclose a specific string in quotes.

You can sort the [!UICONTROL Audiences] list by audience name or by the date when it was last modified. To sort by name or date, click the column header, then select to display audiences in ascending or descending order.

## Viewing Audience Definitions {#section_11B9C4A777E14D36BA1E925021945780}

You can view audience definition details on a pop-up card in various places in the Target UI without opening the audience. This functionality applies to audiences created in Target Standard/Premium and audiences imported from Target Classic or created via API.

For example, the following audience definition card is accessed by hovering over an audience on the Audience List, then clicking the View icon:

![](assets/audience_definition_list.png)

The following audience definition card is accessed by clicking the View icon on an activity's Overview page:

![](assets/audience_definition.png)

Click the [!UICONTROL Audience Usage] tab to see other activities that reference that audience, if applicable. This way you can avoid accidental impact to other activities while editing audiences. Information includes Live Activities, Inactive Activities, Archived Activities, And Syncing Activities. This feature is available for all audiences (Library audiences and [activity-only audiences](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

If an audience is combined with another audience and the combined audience is used to create an activity, the usage information for both audiences will list that newly created activity.

![](assets/audience_definition_list_usage.png)

The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM). Notice that Target does not show detailed audience definition information because that information is not present in Target.

![](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

<table id="table_BEE4E80E557B4BC9B703A5B80BF59F0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Audience Type </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mobile audience </p> </td> 
   <td colname="col2"> <p>Marketing Name, Vendor, and Model. </p> <p>The <span class="codeph"> matches|does not match</span> operator displays instead of <span class="codeph"> equals|does not equal</span>. </p> <p><img href="assets/imported_mobile_audience.png" id="image_D858836141D34047ABEBCE9FBE302826" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitor-behavior audience </p> </td> 
   <td colname="col2"> <p>user.categoryAffinity: <span class="codeph"> categoryAffinity</span> with <span class="codeph"> FAVORITE</span> parameter. </p> <p><img href="assets/imported_category_affinity.png" id="image_117DA80E582F45ACB03B244798A24264" /> </p> <p>Monitoring: <span class="codeph"> Monitoring service equals true</span>. </p> <p>No Monitoring Service: <span class="codeph"> Monitoring service equals false</span>. </p> <p><img href="assets/imported_monitoring.png" id="image_D63245B224C14837B5DDA33247394CB5" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audiences using the NOT operator </p> </td> 
   <td colname="col2"> <p>Single Rule: Target displays the audience in the format <span class="codeph"> [All Visitor AND [NOT [rule]</span>. Single NOT rule displays with AND with AllVisitor audience. </p> <p><img href="assets/imported_not_audience.png" id="image_E1D8B2BF23C64213984A58CFEF7951F4" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium.
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.

