---
description: These release notes provide information about features, enhancements,
  fixes, and known issues for each Target Standard and Target Premium release.
keywords: Release notes;prerelease
seo-description: These release notes provide information about features, enhancements,
  fixes, and known issues for each Target Standard and Target Premium release.
seo-title: Target release notes (current)
solution: Target
title: Target release notes (current)
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Target release notes (current){#target-release-notes-current}

These release notes provide information about features, enhancements, fixes, and known issues for each Target Standard and Target Premium release.

<table id="table_1DAD8293D4A447D9932083FB9488EAA2"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Announcements:</b> </p> <p> 
     <ul id="ul_A0205508929340CB89A766AA047E8363"> 
      <li id="li_27A12387D508414BA5DFCD743432E735"> <p>Participate in the new <a href="../cmp-resources-and-contact-information.md#concept_11902FAC95C64479AABE020557A7EEE4" format="dita" scope="local"> Target Basics Webinar Series</a>. Sign up now for the next session. </p> </li> 
      <li id="li_262EDDD313B5423DA77D002B8AF747C6"> <p> Starting with the Target 18.4.1 release (April 25, 2018), Adobe Target will take steps to move towards TLS 1.2 encryption and phase out support for TLS 1.0 encryption by February 2019. Migrating to TLS 1.2 will provide improved security. It is important that you go through the specifics and plan out the changes for a smooth transition. For more information, see <a href="../c-implementing-target/c-considerations-before-you-implement-target/c-tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451" format="dita" scope="local"> TLS (Transport Layer Security) Encryption Changes</a>. </p> </li> 
      <li id="li_CC766ADAE921431486E513373EBFF5AC"> <p><a href="../cmp-resources-and-contact-information.md#concept_7600A06142034A3FA325EF7FA898DDE8" format="dita" scope="local"> Subscribe to the Adobe Target Insider Newsletter!</a> The Adobe Target Insider is a monthly newsletter for members of the Adobe Target community. Learn about product updates and future plans, personalization and optimization tips and tricks, customer successes, upcoming events, information-filled white papers, popular blog posts, and more. </p> </li> 
      <li id="li_B0250D0AA36A4787A6738378699720B4"> <p> For information about Target Delivery APIs, Recommendations APIs, and NodeJS, see <a href="../c-implementing-target/c-api-and-sdk-overview/c-api-and-sdk-overview.md#concept_5718EC1FF2ED4436935D0BCCD7AA29A6" format="dita" scope="local"> Target APIs and NodeJS SDK</a>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Platform (November 15, 2018) {#section_484A56774E004282B98FFFF851E4E670}

<table id="table_7320E43397D2471FA313A9D6FC21E55F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature / Enhancement </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>at.js 1.6.3 </p> </td> 
   <td colname="col2"> <p>at.js version 1.6.3 is now available. </p> <p> 
     <ul id="ul_2C7CB74B1AAF4B52B6EB382977F7DC28"> 
      <li id="li_07CF8EDB25E24A7AB9B7A0F3402BAEB1"> <p>Selectors are now CSS-escaped if they contain IDs or CSS classes that start with a digit, two hyphens, or a hyphen followed by a digit (for example #-123). (TNT-31061) </p> </li> 
      <li id="li_6504E90D7C534A1BB9A2DE8510CE3B90"> <p>Fixed an issue introduced with at.js 1.6.2 where Visual Experience Composer (VEC) offers from different activities that apply to the same CSS selector did not respect activity priority. (TNT-31052) </p> </li> 
      <li id="li_D347CA513F1240E4BF79D757287AB30C"> <p>Fixed an issue with timing out a promise in environments where there was no native support for promises. (TNT-30974) </p> </li> 
      <li id="li_17F41A84CCFF41D7993E35DE10F87066"> <p>Issues are now correctly captured and reported via the content-rendering failed event. Previously, JavaScript might have been reported to have run successfully, even if that wasn't the case. (TNT-30599) </p> </li> 
     </ul> </p> <p>For more information, see <a href="../c-implementing-target/c-implementing-target-for-client-side-web/r-target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A" format="dita" scope="local"> at.js Version Details</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Target Standard/Premium 18.11.1 (November 12, 2018) {#section_6BBA8B1EE9D241C28E12856A375E97F6}

The [!DNL Target] Standard/Premium release on November 12 includes back-end enhancements, fixes, and changes. The [!UICONTROL Personalization Insights] reports will be available November 14.

<table id="table_EF529199D1C741F7BDBC9C41A37B7D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature / Enhancement </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" class="premium"> <p>Personalization Insights reports </p> <p> <p>Note:  Available November 14, 2018. </p> </p> </td> 
   <td colname="col2"> <p>Two specialized reports are available to users of <span class="wintitle"> Automated Personalization (AP)</span> and <span class="wintitle"> Auto-Target (AT)</span> activities: </p> <p> 
     <ul id="ul_C338AC34C57C49E1A8DFA471167EC40A"> 
      <li id="li_2329BFC8CC524EBBA99C2F8EDC745B90"> <p><b><span class="wintitle"> Automated Segments</span>:</b> Different visitors respond differently to the offers/experiences in your AP/AT activity. This report shows how different automated segments defined by Target's personalization models responded to the offers/experiences in the activity. </p> </li> 
      <li id="li_48556C9BAD48476DA00DD666F5265E2B"> <p><b><span class="wintitle"> Important Attributes</span>:</b> In different activities, different attributes are more, or less, important to how the model decides to personalize. This report shows the top attributes that influenced the model and their relative importance. </p> </li> 
     </ul> </p> <p>See <a href="../c-reports/c-personalization-insights-reports/c-personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767" format="dita" scope="local"> Personalization Insights reports</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Release Notes for Other Adobe Target Capabilities {#section_9EB425262A1947D18953F98CF3D4EE71}

Use the following links to view release notes for Target capabilities other than Target Standard and Target Premium:

* [Recommendations Classic release notes](https://marketing.adobe.com/resources/help/en_US/rec/r_whatsnew-recs.html)
* [Search&Promote release notes](https://marketing.adobe.com/resources/help/en_US/snp/c_searchpromote_release_notes.html)

## Documentation Changes, Past Release Notes, and Experience Cloud Release Notes {#section_1BC5F5208DA548E9B4344A0836E4B943}

In addition to the notes for each release, the following resources provide additional information:

<table id="table_9729DAEA57B44D8D9751785BAA43A729"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Resource </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="../r-release-notes/r-doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C" format="dita" scope="local"> Documentation Changes</a> </p> </td> 
   <td colname="col2"> <p>View detailed information about updates to this guide that might not be included in these release notes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../r-release-notes/release-notes-for-previous-releases.md#topic_607D0324907E472EA3682033A27B5F07" format="dita" scope="local"> Release notes for previous releases</a> </p> </td> 
   <td colname="col2"> <p>View information about new features and enhancements in previous releases of <span class="keyword"> Target Standard</span> and <span class="keyword"> Target Premium</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://wwwimages.adobe.com/content/dam/acom/en/marketing-cloud/testing-targeting/54658.en.target.capabilities.whats-new-fall-2016.pdf" format="pdf" scope="external"> What’s New in Adobe Target 2016</a> (PDF) </p> </td> 
   <td colname="col2"> <p>Display a graphical review of features released in 2016. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/whatsnew/" format="https" scope="external"> Experience Cloud Release Notes</a> </p> </td> 
   <td colname="col2"> <p>View the latest release notes for the<span class="keyword"> Adobe Experience Cloud</span> solutions. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prerelease Information {#section_5D588F0415A2435B851A4D0113ACA3A0}

<table id="table_51A9CF02F1A34B6497DB81657E4893FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Enhancement </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Priority Product Update list </p> </td> 
   <td colname="col2"> <p>To receive advance notifications about upcoming product enhancements, sign up for the Adobe Priority Product Update: </p> <p> <a href="https://www.adobe.com/subscription/priority-product-update.html" format="html" scope="external"> https://www.adobe.com/subscription/priority-product-update.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Current and upcoming release notes </p> </td> 
   <td colname="col2"> <p>For information about the current month's Target releases, including prerelease information, see the <a href="https://marketing.adobe.com/resources/help/en_US/target/rn/" format="https" scope="external"> Target Release Notes - Prerelease</a> page. </p> </td> 
  </tr> 
 </tbody> 
</table>
