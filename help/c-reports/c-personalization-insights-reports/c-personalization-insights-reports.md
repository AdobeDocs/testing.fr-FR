---
description: Two specialized reports are available to users of Automated Personalization
  (AP) and Auto-Target (AT) activities  the Automated Segments and Important Attributes
  reports.
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto
  target;auto target report;auto-target report;personalization;insights;automated
  segments;faq;frequently asked questions;important attributes
seo-description: Two specialized reports are available to users of Automated Personalization
  (AP) and Auto-Target (AT) activities  the Automated Segments and Important Attributes
  reports.
seo-title: Personalization Insights reports
solution: Target
title: Personalization Insights reports
title-outputclass: premium
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Personalization Insights reports{#personalization-insights-reports}

Two specialized reports are available to users of Automated Personalization (AP) and Auto-Target (AT) activities: the Automated Segments and Important Attributes reports.

>[!NOTE]
>
>* P and AT activities are available as part of the [!DNL Target Premium] solution. They are not included with [!DNL Target Standard] without a [!DNL Target Premium] license.
>* Personalization Insights reports are available only for AP and AT activities that use a conversion optimization goal. Activities where the optimization goal was changed to conversion from revenue after the activity was already live are also not supported.
>* Personalization Insights reports are supported in the [default environment](../../administrating-target/c-hosts.md) only.


## Personalization Insights Reporting Overview {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

The goal of the [!UICONTROL Personalization Insights] reports is to provide more information on how the Target personalization models behind your AP and AT activities personalize visitor traffic. The [Random Forest algorithm](../../c-activities/t-automated-personalization/c-algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA) is the basis for Target's personalization models.

Because the goal of the [!UICONTROL Personalization Insights] reports is to understand how Target's personalization models decided to send which visitor to what piece(s) of content, the [!UICONTROL Personalization Insights] reports reflect only a sub-segment of all the traffic served by your AP or AT activity. Specifically, the two reports are reflective of all traffic that used the personalization model. In other words, [!UICONTROL Personalization Insights] reports do not consider control traffic or traffic that is served by the overall winner model.

There are two reports available in:

<table id="table_713AAD1ED0A5460580ACA7EBB7986C2A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Report </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Automated Segments </span> </p> </td> 
   <td colname="col2"> <p>Different visitors respond differently to the offers/experiences in your AP/AT activity. This report shows how different automated segments defined by Target's personalization models responded to the offers/experiences in the activity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Important Attributes </span> </p> </td> 
   <td colname="col2"> <p>In different activities, different attributes are more, or less, important to how the model decides to personalize. This report shows the top attributes that influenced the model and their relative importance. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Interpreting Attributes in Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

There are two types of attributes represented in [!UICONTROL Personalization Insights] reports that are used in your AP or Auto Target models:

* **Attributes automatically collected by Target:** Target uses a base data set to build its personalization algorithms in AP and AT activities that are reflected in Personalization Insights. See [Data Collection for Target's Personalization Algorithms](../../c-activities/t-automated-personalization/r-ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058) for data types, example attributes, and their [!UICONTROL Personalization Insights] naming convention. Note that although these attributes are considered, an individual activity’s models might not use all of these attributes in the final model.
* **Attributes passed to Target:** See [Uploading Data for the Target Personalization Algorithms](../../c-activities/t-automated-personalization/c-uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

Target provides many ways for you to pass in additional data to Target to enrich the base data set used to build its personalization algorithms in AP and AT activities:

<table id="table_8DAFC42AA43D4AB8A5CE4CF562A5B614"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Type </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Data Type Naming Convention </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Profile Attributes, including profile scripts, Profile Update API, and in-page profile attributes </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_293A93F5B98646BDB9D93C251A4E4915"> 
      <li id="li_E023C6C1AA4C4F5FB1725CDEDE0B0C98"> <p>Any information you've decided to include in Target's user profile. </p> </li> 
      <li id="li_978DEF1A5E0F4BCFB995E6D3D41AA140"> <p>This information could come from profile scripts, information uploaded using the Profile Update API, or in-mbox profile parameters prefixed with "profile." </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Custom - Profile - [parameter name] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Parameters (also called “mbox parameters”) </p> </td> 
   <td colname="col2"> <p>Name/value pairs passed in directly through page code that are not stored in the visitor's profile for future use. </p> </td> 
   <td colname="col3"> <p>Custom - Mbox Parameter - [parameter name] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer Attributes </p> </td> 
   <td colname="col2"> <p>Customer attributes let you upload visitor profile data via FTP to the Experience Cloud. Once uploaded, leverage the data in Adobe Analytics and Adobe Target. </p> </td> 
   <td colname="col3"> <p>Custom - Customer Attributes - [parameter name] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Shared Audiences (Adobe Audience Manager or Adobe Analytics) </p> </td> 
   <td colname="col2"> <p>Audiences created through Adobe Audience Manager or Adobe Analytics and shared with Target. </p> </td> 
   <td colname="col3"> <p>Custom - Experience Cloud Segment - [segment name] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>In-Activity Reporting Audiences/ Segments </p> </td> 
   <td colname="col2"> <p>Audiences defined in your AP or Auto Target activity during setup in “Goals &amp; Metrics.” </p> </td> 
   <td colname="col3"> <p>Custom - Reporting Segment - [segment name] </p> </td> 
  </tr> 
 </tbody> 
</table>

