---
description: learn about new features and fixes in the adobe marketing cloud.
keywords: release notes
seo-description: learn about new features and fixes in the adobe marketing cloud.
seo-title: release notes - may 2015
title: release notes - may 2015
index: y
internal: n
snippet: y
translate: y
matt: lawrence
translation-type: tm+mt
source-git-commit: 7269a39b5a2c1b42b6f669be5c8b36d8b71f1973
Translated: 'false'

---

# Lots of columns

<!-- <table border="1">
<tr>
<td>1</td>
<tdcolspan="2">2 and 3</td>
<td>4</td>
</tr>
<tr>
<tdrowspan="3">5, 9 and 13</td>
<td>6</td>
<td>7</td>
<td>8</td>
</tr>
<tr>
<td>10</td>
<td>11</td>
<td>
<ol>
<li> one </li>
<li> two </li>
</ol>
</td>
</tr>
<tr>
<tdcolspan="3">14, 15 and 16</td>
</tr>
</table> -->

## Sign in and manage your profile settings

>[!NOTE]
>
>You must encode any URL before passing it to the `destURL` parameter. (Encoder sites like [URL Decoder / Encoder](https://meyerweb.com/eric/tools/dencoder/) are available.)

| Parameter | Description | Example | Required / Optional |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|------------------------------------|
| tenantId | Name of the tenant the user should log into. | aem62tenant | Optional |
| destURL | The complete URL to the place where the user should be taken to. | https://sc.omniture.com/x/1_7xxzf | Optional |
| solutionname | Name of the MAC Solution that is the owner of destURL parameter. It is used to verify that the user has access to the solution which is the owner of the URL.  It is the responsibility of the solutions to make sure that the solutionname is in Sync with the destURL parameter.  For example : If the URL contains solutionname as social and the destURL provided is an analytics url, then the user would be redirected to the url even if he doesn't have access to analytics. MAC does NOT verify weather the owner of the destURL is in sync with the solution name. | analytics | Required if destURL param is used. |

| Product Name & Help Link | Analysis Workspace | Reports & Analytics | Ad Hoc Analysis | Report Builder | Data Warehouse | Data Workbench |
|------------------------|------------------|-------------------|---------------|--------------|--------------|--------------|
| Access Method | Browser solution for building robust,custom analysis projects, and democratizing insights. | Browser solution for digital analysis. | Java based tool for advanced digital analysis. | Excel add-in that lets you build customized requests from R&A data, and visualize using Microsoft Excel. | Browser solution that generates reports in .csv format. Can generate Tableau format files. | Multi-channel analytics tool for advanced analysis, such as custom attribution modeling, predictive analytics, and 360 customer analysis. |
| Report Breakdowns | Unlimited | Up to 2 correlations | Unlimited | Up to 2 correlations | Performs fully expanded, unlimited breakdowns, break down by segment. | Unlimited |
| Segment Comparisons | Unlimited | Up to 2 segments | Unlimited | Unlimited (data request stacking) | 1 segment. Supports multiple (stacked) segments. | Unlimited |
| Row Output Limit | 400 | 200 | 50,000 | 50,000 | Unlimited | Customizable |
| Unique Value Limits (within eVar/ prop reports) | 500K-2MM | 500K-2MM | 500K-2MM | 500K-2MM | Unlimited | Customizable |
| Funnel/Pathing | Yes Fallout Flow | Yes | Yes | Yes | No | Yes |
| Advanced Customer Journey Analysis | Planned | No | Yes | No | No | Yes |
| Cohort Analysis | Yes | No | No | No | No | Yes |
| Advanced Attribution | Limited currently - first/last/linear | Limited - first/last/linear | Limited - first/last/linear | Limited - first/last/linear | Limited - first/last/linear | Yes |
Learn about new features and fixes in the Adobe Marketing Cloud.

>[!NOTE]
>
>To receive release notes one week prior to the monthly product update, subscribe to the[Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html). Release information in the Priority Product Update comes one week in advance of the release date and is subject to change. Please check back at release time for updates.

<!-- <p>This file is the template for the monthly RNs. To update all links, open this file in notepad++, search for <span class="filepath"> 05212015 </span> and replace all occurrences with the current file name (usually release date). When adding content, edit only the tables and Fixes ULs. Do not overwrite Concepts, Sections, or the topic maps ULs. </p> -->
May 2015

## Core Services

| Hello | There |
|---|---|
| a | b |

| Feature | Description |
| --- | --- |
| Something goes here... | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions.  Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. |

| Feature | Description | Description2 | Description 3 |
| --- | --- | --- | --- |
| Something goes here... | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. ![Warning](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. <br>![Warning](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) <br> Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. ![Warning](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. |

<table>
<tr>
<td>
hello
</td>
<td>
there
</td>
</tr>
<tr>
<td>
</td>
<td>
This<br>is<br>a<br>test
</td>
</tr>
</table>

### Marketing Cloud Interface 15.5.1 {#marketing_cloud_interface}

New features and fixes in the [!DNL  Adobe Marketing Cloud] interface.

Release date: **May 13, 2015**

<table id="table_14E7B35E06C84A258A21D09691B58354"> 
 <thead> 
  <tr> 
   <th colname="col1" > Feature </th> 
   <th colname="col2" > Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Something goes here...</p> </td> 
   <td colname="col2"> <p>The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. Notable changes include: </p> 
    <ul id="ul_5BEBAB86B9234A239C4E2DAF8826D8E3"> 
     <li id="li_7FA9F64CE69144B8A8A92746BF40E5A1">The <span class="term"> Audience Library </span> and <span class="term"> Customer Attributes </span> menu selections are now located under <span class="term"> Audiences </span>. </li> 
     <li id="li_95D62A43AE6243DBB2A65EDB830D05C4">The <span class="term"> Exchange </span> menu selection was moved from the Help drop-down menu to the left navigation rail. </li> 
     <li id="li_0443FD50C78446CD8AA27A4F272CAD31"> <span class="term"> Solutions </span> has been removed. You can launch all solutions from the bottom half of the navigation rail. </li> 
    </ul> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names" format="https" scope="external"> About Core Services and Solutions </a> for descriptions of the selections in the lefthand navigation menu. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* Fixed an issue preventing customer attributes from syncing for some customers.
* Fixed an issue preventing [Adobe Target Product Documentation](https://marketing.adobe.com/resources/help/ja_JP/target/a4t/) page from displaying in Japanese.
* Fixed an issue preventing the use of Japanese text in comments between the [!DNL  Creative Cloud] and the [!DNL  Marketing Cloud].

See [Marketing Cloud Product Documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/) for product help.


### Adobe Mobile Services {#mobile}

New features and fixes in the [!DNL  Adobe Mobile Services] interface.

<table id="table_03055471A9624B40B122C0E2CD295AA9"> 
 <thead> 
  <tr> 
   <th colname="col1" > Feature </th> 
   <th colname="col2" > Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Acquisition links </p> </td> 
   <td colname="col2"> <p> Added a desktop browser regional override for acquisition links. This setting lets you select the region-specific app store that you want an acquisition link to direct to when a user clicks the link from a desktop browser. </p> <p> This feature can be set only by those users with administrative privileges to create Acquisition Links (Mobile App Admins). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reports </p> </td> 
   <td colname="col2"> <p>PDF/CSV export for <span class="wintitle"> Ranked </span>, <span class="wintitle"> Trended </span>, <span class="wintitle"> Retention </span>, <span class="wintitle"> Funnel </span>, <span class="wintitle"> Geo Location </span>, and <span class="wintitle"> Sunburst </span> reports. (Public Beta) </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* Resolved issue for some IMS users redirecting from [!DNL  marketing.adobe.com] not seeing any apps in [!DNL  mobilemarketing.adobe.com].
* Added custom calendar support in Retention for 4-5-4 and 4-4-5 (custom and retail).
New features and fixes in the [!DNL  Adobe Mobile Services] SDKs.

<table id="table_1A8173DB38E8426D96BB7C57BF8FD2D5"> 
 <thead> 
  <tr> 
   <th colname="col1" > Update </th> 
   <th colname="col2" > Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>iOS SDK Version 4.5 </p> </td> 
   <td colname="col2"> <p>Starting in iOS SDK version 4.5, a new iOS extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other iOS extension apps. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external"> iOS Extension Implementation </a> in the <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/" format="https" scope="external"> iOS SDK 4.x for Marketing Cloud Solutions </a> guide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Android SDK Version 4.5 </p> </td> 
   <td colname="col2"> <p>Starting in Android SDK version 4.5, a new Android extension lets you collect data from your Android Wearable app. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external"> Android Wearable Implementation </a> in the <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/" format="https" scope="external"> Android SDK 4.x for Marketing Solutions </a> guide. </p> </td> 
  </tr> 
 </tbody> 
</table>


>[!IMPORTANT]
>
>Adobe strongly recommends that you do not create your own wrappers for our SDKs and track wearables using older versions. Doing so will likely cause issues with your data.

See [Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/) for product documentation. To see the release notes for previous releases, expand *Previous Release Notes* in the left pane.

## Analytics

### New Features/Changes in Analytics {#features_analytics}


<table id="table_91D1FD20C4C1411292252364328677AF"> 
 <thead> 
  <tr> 
   <th colname="col1" > Component </th> 
   <th colname="col2" > Feature Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Data Warehouse </td> 
   <td colname="col2"> Added "Marketing Channel Last Touch Instances" metric for Data Warehouse reporting. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Sources modification coming in June 2015 </td> 
   <td colname="col2"> <p>Reports &amp; Analytics has not supported data sources of type “Traffic Data Source" since the introduction of SiteCatalyst 15. The data sources user interface still allows you to create a Traffic Data Source, but this kind of data source can only be applied to date ranges prior to the date when your company migrated from SiteCatalyst 14 to SiteCatalyst 15. Next month (June 2015), Adobe plans to remove Traffic Data Sources as an option. In June, we will also introduce new capabilities in Reports &amp; Analytics that will allow you to create simple traffic metrics without the need for Traffic Data Sources. </p> </td> 
  </tr> 
 </tbody> 
</table>


### Reports &amp; Analytics {#fixes_reports_analytics}

**Fixes**

* Fixed an issue with [!DNL  Target] campaign reports not showing up in Reports &amp; Analytics.
* Fixed an issue with special characters in [!DNL  Target] campaign names preventing their reporting in Reports &amp; Analytics.
   * An *` Access Denied`* error displaying when creating breakdowns in [!UICONTROL  Marketing Channel] reports, and in calculated metrics on a [!UICONTROL  Campaigns] report.
   * An interface reset in which the report changed to a different one when applying changes to a segment.
* Fixed an issue with [!UICONTROL  Bots] reports in dashboards not showing correct data.
* Fixed an issue with the Edit (pencil) icon when editing segments Internet Explorer 11. This issue forced you to click the Edit icon twice to load the [!UICONTROL  Segment Manager].
* Fixed an issue where an incorrect metric name and currency unit were displayed in a [!UICONTROL  Contribution Analysis] report.


### Data Warehouse {#fixes_data_warehouse}


<table id="table_A01098A1EE3A4F1084AB13DD1A0DF1B3"> 
 <thead> 
  <tr> 
   <th colname="col1" > Feature </th> 
   <th colname="col2" > Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Report API 1.4 </p> </td> 
   <td colname="col2"> <p>Data warehouse supports the Analytics Reporting API 1.4. </p> <p>See <a href="https://marketing.adobe.com/developer/documentation/data-warehouse/r-report-2" format="https" scope="external"> Report.Queue </a> in the Data Warehouse API documentation on the Developer Connection. </p> </td> 
  </tr> 
 </tbody> 
</table>

### AppMeasurement and Mobile SDKs {#appmeasurement_sdk}

**Marketing Cloud Visitor ID Service**

**1.4**

As of version 1.4, the preferred method of setting configuration is passing in a config object in as the second parameter to the *` Visitor.getInstance`* function.

Example Config Initialization:


```
var visitor = Visitor.getInstance("016D5C175213CCA80A490D05@AdobeOrg",{ 
    "loadTimeout":1000, 
    "trackingServer":"myco.sc.omtrdc.net", 
    "idSyncContainerID":80 
});
```


>[!NOTE]
>
>The ID sync functionality releasing on May 21 only works for JavaScript. There is no Flash support at this time.

See [Visitor ID Service Implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) for information about this change.

** [!DNL  AppMeasurement] for JavaScript**

**1.4.5**

* Inclusion of Marketing Cloud Visitor ID Service API 1.4.
* Updated Audience Manager module to use DIL version 6.0.
**JavaScript H code (Legacy) **

** H.27.5 Update**

* Inclusion of Marketing Cloud Visitor ID Service API 1.4.

**Flash **

**3.9.2 Update**

* Inclusion of Marketing Cloud Visitor ID Service API 1.4.

**[!DNL  AppMeasurement] for Other Platforms**

See [AppMeasurement Release History](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/index.html) the following for a release history of [!DNL  AppMeasurement] on the following platforms:

* JavaScript
* iOS
* Android
* Flash-Flex
* OSX
* Windows Phone, XBOX, Silverlight, and .NET
* BlackBerry
* Java
* PHP
* Symbian

## Social

The Social 15.5.1.0 release (05/21/2015) includes the following changes:


| Feature | Description |
|--- |--- |
| Facebook dark posts | Create posts on Facebook that do not display on your Timeline but can be accessed with direct links. This option lets content creators create posts to be promoted as sponsored (paid) ads. |
| New reserved events in  Adobe Analytics | Currently there are metrics we receive from social networks that cannot be reported on in  Adobe Analytics . New reserved events let you create custom reports in  Analytics  to view social data alongside web data. |
| Adobe Social  Mobile App | The  Adobe Social  Mobile app for iOS will be available in the Apple App Store in June 2015. |

For training videos on these new features, see [What's New for May 2015](https://bit.ly/1JSO2k5).

**Enhancements**

<table id="table_191B769A5A8A405C87A34245BE6B1127"> 
 <thead> 
  <tr> 
   <th colname="col1" > Feature </th> 
   <th colname="col2" > Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Video publishing </p> </td> 
   <td colname="col2"> <p>Select a still frame from anywhere in the video to upload and use as that video's thumbnail image in the post. Previously, <span class="keyword"> Social </span> selected the opening frame to be used as the thumbnail image. 
     <!--AS-32358 and AS-32536--></p> 
    <!--<p>See the <wintitle>Upload a Video</wintitle> section in <xref href="t_pub_cnt_cal_create.xml#concept_6DD750347952474C942F537A6E13087A" format="dita" scope="local">Create or Edit a Post in Content Calendar</xref> and <xref href="c_pub_publisher.xml#concept_CDA6B3AC4D3E47FDB474B83CF6B4B71E" format="dita" scope="local">Publisher Page</xref>. </p>--> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Twitter geo-targeting </p> </td> 
   <td colname="col2"> <p>On March 1, 2015, Adobe Social discontinued support for geo-targeting of tweets. After working with Twitter, geo-targeting is available again. </p> 
    <!--<p>See the <wintitle>Specify Targets</wintitle> section in <xref href="t_pub_cnt_cal_create.xml#concept_6DD750347952474C942F537A6E13087A" format="dita" scope="local">Create or Edit a Post in Content Calendar</xref> and <xref href="c_pub_publisher.xml#concept_CDA6B3AC4D3E47FDB474B83CF6B4B71E" format="dita" scope="local">Publisher Page</xref>. </p>--> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Approving posts </p> </td> 
   <td colname="col2"> <p>Publishing approvers can now approve a post from its preview. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Twitter direct message images </p> </td> 
   <td colname="col2"> <p>Improved the method <span class="keyword"> Social </span> uses to fetch and display images in Twitter direct messages in moderation feeds. 
     <!--AS-30675--></p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Social tags </p> </td> 
   <td colname="col2"> <p>You can now create a tag group or tag with the same name as a previously deleted tag group or tag. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

This [!DNL  Social] release focuses on improved performance, scalability, usability, and reliability. More than 140 back-end fixes and enhancements address these areas. The fixes highlighted below describe resolutions for the more important customer-reported issues.

* Fixed an issue that caused incorrect data to display for Facebook pages in the [!UICONTROL  Competitor Analytics] report.
* Fixed an issue that caused discrepancies in the number of reported Twitter followers.
* Fixed an issue that prevented tracking parameters from appending to posts created using the [!UICONTROL  Publish Anywhere] feature.
* Fixed an issue that sometimes caused posts to fail with a timeout error.
* Fixed an issue with shortened links where links to pages within a website redirected to the company's homepage.
* Fixed an issue that caused some invalid content (posts, comments, and replies) to appear in moderation feeds. Code enhancements will help our collection system more effectively block Invalid content that does not match the page.

## Target

Refer to the [Adobe Target Release Notes](https://marketing.adobe.com/resources/help/en_US/target/rn/) for the latest release information about the following products:

* Target Standard and Premium
* Target Classic
* Recommendations Classic

## Audience Manager

| Feature | Description |
|---|---|
| [Audience Marketplace](https://marketing.adobe.com/resources/help/en_US/aam/c_audience_marketplace.html) | [!DNL  Audience Marketplace] provides specialized features that lets data buyers and data providers execute data deals in a self-service manner with minimum effort. Talk to your [!DNL  Audience Manager] consultant to get started. They can activate [!DNL  Audience Marketplace] for you. |

**Fixes, Enhancements, and Deprecations**

* [Create Groups](https://marketing.adobe.com/resources/help/en_US/aam/t_create_groups.html): Simplified steps and directions for creating groups and assigning permissions.
* [Understanding Wild Card Permissions](https://marketing.adobe.com/resources/help/en_US/aam/c_wildcard_permissions.html): Use [!DNL  Wild Card Permissions] to give group members access to new data sources automatically. With standard permissions, you must manually assign new data sources to a group.

**Known Issues**

In the VisitorAPI / AppMeasurement Audience Manager Module integrations, there will be two destination publishing iFrame requests made in IE6-9: [!DNL  //fast.<subdomain>.demdex.net/dest5.html] and [!DNL  //fast.<subdomain>.demdex.net/dest4.html]. The correct behavior, as seen in other browsers, is to only load [!DNL  //fast.<subdomain>.demdex.net/dest5.html].

## Key Documentation Updates

<table id="table_3C13024F4D754E2C98D7B8434A3497EF"> 
 <thead> 
  <tr> 
   <th colname="col1" > Item </th> 
   <th colname="col2" > Description </th> 
   <th colname="col3" > Date Published </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=adobe_managed_cert_pgm" format="https" scope="external"> Adobe Managed Certificate Program </a> </p> </td> 
   <td colname="col2"> <p>Added <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=adobe_managed_cert_pgm" format="https" scope="external"> Adobe Managed Certificate Program </a> to the revamped <span class="term"> First-Party Cookies </span> product documentation. </p> <p>The managed certificate program lets you implement a new first-party SSL certificate for first-party cookies at no additional cost. </p> </td> 
   <td colname="col3"> <p>May 22, 2015 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Revamped the Adobe Mobile product documentation. </p> </td> 
   <td colname="col3"> <p>May 22, 2015 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/index.html?f=core_services" format="https" scope="external"> Enabling Your Solutions for Core Services </a> </p> </td> 
   <td colname="col2"> <p>A high-level round-up what you need to do to modernize your solution implementations for core services. </p> </td> 
   <td colname="col3"> <p>March 19, 2015 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/index.html?f=attributes" format="https" scope="external"> Customer Attributes </a> </p> </td> 
   <td colname="col2"> <p>If you capture enterprise customer data in a customer relationship management (CRM) database, you can upload that data into the Marketing Cloud. </p> </td> 
   <td colname="col3"> <p>March 19, 2015 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics Spring Release  </td> 
   <td colname="col2"> <p>See the section in Analytics for a round-up of new documentation for the Spring 2015 Analytics release. </p> </td> 
   <td colname="col3"> <p>March 19, 2015 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Analytics <a href="https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_set.html" format="https" scope="external"> Classification Rules </a> - overwrite existing values </p> </td> 
   <td colname="col2"> <p>In <span class="uicontrol"> Admin Tools </span> > <span class="uicontrol"> Classification Rule Builder </span> > <span class="term"> &amp;lt;rule set name&amp;gt; </span>, two new options enable you to select an overwrite mode: </p> 
    <ul id="ul_14E61CC9E94B431090539CB47A9B83D6"> 
     <li id="li_F77AEF4B136540E5A6E1040215999E85"> <b>Rules overwrite any existing values:</b> (Default setting) Always overwrite existing classification keys, including classifications uploaded via the importer (SAINT). </li> 
     <li id="li_0E82075DFBF04D1D8D686A5B95FCFB3E"> <b>Rules overwrite only unset values:</b> Only fill in blank (unset) cells. Existing classifications will not be changed. </li> 
    </ul> <p>Previously, if a key was already classified in any column or cell, the rule would not run on that key, and the row in the table was skipped. </p> </td> 
   <td colname="col3"> <p>February 19, 2015 </p> </td> 
  </tr> 
 </tbody> 
</table>
