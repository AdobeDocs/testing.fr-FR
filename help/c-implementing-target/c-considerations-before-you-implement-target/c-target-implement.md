---
description: Implement Target by referencing the Target libraries (at.js or mbox.js)
  on your web pages.
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox
seo-description: Implement Target by referencing the Target libraries (at.js or mbox.js)
  on your web pages.
seo-title: Understand the Target JavaScript libraries
title: Understand the Target JavaScript libraries
topic: Target
uuid: c8a254c9-afc9-4a55-be01-788c11bef7cc
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Understand the Target JavaScript libraries{#understand-the-target-javascript-libraries}

Implement Target by referencing the Target libraries (at.js or mbox.js) on your web pages.

>[!NOTE]
>
>The `mbox.js` library is no longer being developed. All customers should migrate from `mbox.js` to `at.js`. For more information, see [Migrate to at.js from mbox.js](../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/t-target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Differences Between the Two Libraries {#section_40117C78C2F84FECAC4F1BA40CC4F171}

The following table explains the differences between the two libraries:

<table id="table_1C35E3E57F604FB986066B039017E4AD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Library Reference </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="filepath"> at.js</span> </td> 
   <td colname="col2"> <p> <span class="filepath"> at.js</span> replaces <span class="filepath"> mbox.js</span> for <span class="keyword"> Target</span> implementations. </p> <p>Among other benefits, <span class="filepath"> at.js</span> improves page-load times for web implementations, improves security, prevents <span class="filepath"> document.write</span> warnings in Google Chrome, and provides better implementation options for single-page applications. </p> <p>For more information, see <a href="../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/c-target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17" format="dita" scope="local"> at.js Implementation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="filepath"> mbox.js</span> </td> 
   <td colname="col2"> <p> Prior to Target 16.3.1 (March 2016), <span class="keyword"> Target</span> required a call to <span class="filepath"> mbox.js</span> to create the global mbox required for <span class="keyword"> Adobe Target </span>to deliver <span class="keyword"> Target</span> activities, track clicks, and track most success metrics. This file contains the libraries needed for all of your activities. You do not need to maintain different activity-specific versions of the file. </p> <p> If you already have wrapping mboxes on your pages from an older style of <span class="keyword"> Target </span> implementation, these mboxes can still be used in the new interface. The updated <span class="filepath"> mbox.js</span> file is still required, but these mboxes can be selected for activities and edited using the <span class="wintitle"> Visual Experience Composer</span>. </p> <p><span class="keyword"> Target Standard and Premium</span> update and supplement <span class="filepath"> mbox.js</span> with a reference to a <span class="filepath"> target.js</span> file. The <span class="filepath"> target.js</span> file is hosted by Adobe. The <span class="filepath"> Target.js</span> file makes it possible to edit content on any page using the <span class="wintitle"> Visual Experience Composer</span>, even if the page does not contain predefined mboxes. You must reference this file on every page on your site. </p> <p> Although <span class="filepath"> at.js</span> replaces <span class="filepath"> mbox.js</span>, <span class="filepath"> mbox.js</span> will continue to be supported. </p> <p>For more information, see <a href="../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/t-mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420" format="dita" scope="local"> mbox.js Implementation</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impact of at.js and mbox.js on Page-Load Time {#section_16630CD0FF0A498EB596A51381366A5A}

Many customers and consultants want to know the impact of [!DNL at.js] and [!DNL mbox.js] on page-load time, especially in the context of new vs returning users. Unfortunately, it's hard to measure and give concrete numbers regarding how [!DNL at.js] or [!DNL mbox.js] influence page-load time due to each customer's implementation.

However, if the Visitor API is present on the page, we can better understand how [!DNL at.js] and [!DNL mbox.js] influence page-load time.

>[!NOTE]
>
>The Visitor API and [!DNL at.js] or [!DNL mbox.js] have an impact on page-load time only when you are using the global mbox (because of the body-hiding technique). Regional mboxes are not impacted by Visitor API integration.

The following table describes the sequence of actions for new and returning visitors:

<table id="table_DFC2E802C56F4089B1018B2569184E8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Library Reference </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>New Visitors </p> </td> 
   <td colname="col2"> <p> 
     <ol id="ol_68066FE03B404D07AFA5598D39FD742D"> 
      <li id="li_66E61E8B17CF4364A19A25EDC337A8E1"> <p>The Visitor API is loaded, parsed, and executed. </p> </li> 
      <li id="li_44EEA42946504B318FF82F8BFF5D65F4"> <p><span class="filepath"> at.js</span> / <span class="filepath"> mbox.js</span> is loaded, parsed, and executed. </p> </li> 
      <li id="li_F063C1ADDBED4451A2054E18706B6FE6"> <p> If global mbox auto-create is enabled, the Target JavaScript library: </p> 
       <ul id="ul_720E6DFB7F6743029DC77456B4909237"> 
        <li id="li_FA4F2BF98703456683098BB5BDC55FFF"> <p>Instantiates the Visitor object. </p> </li> 
        <li id="li_CAE5248725D14A789520BEEAD1C15FF9"> <p>The Target library tries to retrieve Experience Cloud Visitor ID data. </p> </li> 
        <li id="li_F022B2A075014BA29A2D45300466048E"> <p>Because this is a new visitor, the Visitor API fires a cross-domain request to <span class="filepath"> demdex.net</span>. </p> </li> 
        <li id="li_335B4EAE3E364A28861E04F4FE245A51"> <p>After Experience Cloud Visitor ID data is retrieved, a request to Target is fired. </p> </li> 
       </ul> </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Returning Visitors </p> </td> 
   <td colname="col2"> <p> 
     <ol id="ol_EC696FABA7204E5389482206496953CB"> 
      <li id="li_AA3C98F64542460B8C3EA092849E2D30"> <p>The Visitor API is loaded, parsed, and executed. </p> </li> 
      <li id="li_BD4D65ED4E9A4FACA14FFB800212174D"> <p><span class="filepath"> at.js</span> / <span class="filepath"> mbox.js</span> is loaded, parsed, and executed. </p> </li> 
      <li id="li_BE8E11A07A60489FA8E002127DD1C71A"> <p> If global mbox auto-create is enabled, the Target JavaScript library: </p> 
       <ul id="ul_136ED98B2D3842649B4A11813D700741"> 
        <li id="li_AE62483E3F5640C481D971DB351CC7BB"> <p>Instantiates the Visitor object. </p> </li> 
        <li id="li_076F00DF192F4C9FB2AACAB8F603D2C3"> <p>The Target library tries to retrieve Experience Cloud Visitor ID data. </p> </li> 
        <li id="li_5370E81BFC3F479D9F995C981BB68D9A"> <p>The Visitor API retrieves data from cookies. </p> </li> 
        <li id="li_A089C9E19C874F7FAA1A7314CC2099C9"> <p>After Experience Cloud Visitor ID data is retrieved, a request to Target is fired. </p> </li> 
       </ul> </li> 
     </ol> </p> </td> 
  </tr> 
 </tbody> 
</table>

For new visitors, when the Visitor API is present, Target has to go over the wire multiple times to make sure that Target requests contain Experience Cloud Visitor ID data. For returning visitors, Target goes over the wire only to Target to retrieve the personalized content.
