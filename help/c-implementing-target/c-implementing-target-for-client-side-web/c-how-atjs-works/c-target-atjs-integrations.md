---
description: Information about common integrations with Target and their support status
  with at.js.
keywords: at.js integration;supported integrations;unsupported integrations;third
  party integrations
seo-description: Information about common integrations with Target and their support
  status with at.js.
seo-title: at.js integrations
solution: Target
title: at.js integrations
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# at.js integrations{#at-js-integrations}

Information about common integrations with Target and their support status with at.js.

If you have a compelling need for an integration that is not supported or mentioned here, please contact your account representative or consultant.

## Supported Integrations {#section_3B44A970D3FB42D1973701452C868B55}

<table id="table_3C9C2D0A88004D5D9708347B85DE5A7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Integration </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Analytics for Target (A4T) </p> </td> 
   <td colname="col2"> <p>See <a href="../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE" format="dita" scope="local"> Adobe Analytics as the Reporting Source for Adobe Target (A4T)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profiles &amp; Audiences (P&amp;A) </p> </td> 
   <td colname="col2"> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html" format="html" scope="external"> Audiences</a> in the Adobe Experience Cloud and Core Services Help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud ID Service </p> </td> 
   <td colname="col2"> <p>See the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Adobe Experience Cloud ID Service documentation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adobe Launch </p> </td> 
   <td colname="col2"> <p>Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences. </p> <p>See <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25" format="dita" scope="local"> Implementing Target using Adobe Launch</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dynamic Tag Management (DTM) </p> </td> 
   <td colname="col2"> <p>See the <a href="https://marketing.adobe.com/resources/help/en_US/target/ov2/implementing-target-using-dynamic-tag-management.html" format="html" scope="external"> Implementing Target Using Dynamic Tag Management guide</a>. </p> <p> <p>Important: <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25" format="dita" scope="local"> Adobe Launch</a> is the preferred, up-to-date method for implementing Target and the at.js library. For new Target implementations, use Launch. The following guide is for existing clients using a DTM implementation. </p> </p> <p>Consider the following when using a DTM integration: </p> <p> 
     <ul id="ul_8B7BF60E14554C7B863E434180D409C7"> 
      <li id="li_EF8BC216C6A04FAA8E214ADC59CC7724">Library Management: Use the "Custom" hosting option to use at.js. <p>"Automatic" management is not currently supported. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Manager (AEM) Cloud Service </p> </td> 
   <td colname="col2"> <p>The AEM Cloud Service enables the creation of A/B tests and Experience Targeting activities within the AEM workflow. Supports at.js with Adobe Experience Manager 6.2 with FP-11577 (or later) . For more information, see <a href="https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html" format="html" scope="external"> Integrating with Adobe Target</a> and select your AEM version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM Experience Fragments </p> </td> 
   <td colname="col2"> <p>Experience fragments created in AEM in Target activities let you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in Target to test and personalize experiences at scale. </p> <p>AEM brings together all of your content and assets in a central location to fuel your personalization strategy. AEM lets you easily create content for desktops, tablets, and mobile devices in one location without writing code. There’s no need to create pages for every device—AEM automatically adjusts each experience using your content. </p> <p>See <a href="../../../c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8" format="dita" scope="local"> AEM experience fragments</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Unsupported Integrations {#section_8EFCAED418DC42E0B07F95924819EAC2}

<table id="table_4CF1738CF06B43A784EE783D3FAED3C8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Integration </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Legacy Target to SiteCatalyst Integration </p> </td> 
   <td colname="col2"> <p>This was the integration that sent campaign and recipe ids to <span class="keyword"> SiteCatalyst</span> via the page call so you could do reporting in the <span class="keyword"> SiteCatalyst</span> UI. This functionality is replaced by A4T. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Legacy Target to SiteCatalyst Integration </p> </td> 
   <td colname="col2"> <p>This was the integration that made mbox calls named "SiteCatalyst: Event" and "SiteCatalyst: Purchase" so you could build success metrics and user profiles based on evars and props. This functionality is replaced by A4T and P&amp;A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Legacy Audience Manager (AAM) to Target Integration </p> </td> 
   <td colname="col2"> <p>This was the integration that made a front-end API call to retrieve AAM segments and then sent them as mbox parameters on every mbox call on the page. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Third-Party Integrations {#section_EE599839CCAD49DD97640E5EDAD9082E}

<table id="table_8139E0696BAD436588224AEC2AEE0852"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Integration </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Other Tag Managers </p> </td> 
   <td colname="col2"> <p><span class="filepath"> at.js</span> should work with non-Adobe tag management platforms, but be careful using custom integration features that other vendors have developed. Their integrations might be dependent on internal <span class="filepath"> mbox.js</span> functions that no longer exist in <span class="filepath"> at.js</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Third-party data providers (e.g. Demandbase, Bluekai, weather APIs) </p> </td> 
   <td colname="col2"> <p>Many third-party data providers used to supplement Target's user profiling can be integrated using the at.js <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Data Providers</a> feature </p> </td> 
  </tr> 
 </tbody> 
</table>

