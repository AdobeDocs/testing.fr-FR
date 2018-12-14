---
description: These release notes provide information about features, enhancements,
  fixes, and known issues for the latest or upcoming Target releases.
keywords: release notes
seo-description: These release notes provide information about features, enhancements,
  fixes, and known issues for the latest or upcoming Target releases.
seo-title: Target release notes (prerelease)
solution: Target
title: Target release notes (prerelease)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Target release notes (prerelease){#target-release-notes-prerelease}

These release notes provide information about features, enhancements, fixes, and known issues for the latest or upcoming Target releases.

**Last Updated: December 6, 2018**

>[!NOTE]
>
>These release notes contain prerelease information. Release dates, features, and other information are subject to change. To view information about the current release, see [Target Release Notes](r-release-notes.md) in the Target documentation. Depending on the timing of releases, the information on these pages might differ.

<table id="table_1DAD8293D4A447D9932083FB9488EAA2"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Announcements:</b> </p> <p> 
     <ul id="ul_A0205508929340CB89A766AA047E8363"> 
      <li id="li_248ACD8F14F74ECEB34E18DB16CFD1C5"> <p> Starting with the Target 18.4.1 release (April 25, 2018), Adobe Target will take steps to move towards TLS 1.2 encryption and phase out support for TLS 1.0 encryption. Migrating to TLS 1.2 will provide improved security. It is important that you go through the specifics and plan out the changes for a smooth transition. For more information, see [TLS (Transport Layer Security) Encryption Changes](c-implementing-target/c-considerations-before-you-implement-target/c-tls-transport-layer-security-encryption.md)(</a>. </p> </li> 
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
  <!-- <row> <entry colname="col1"> <p>Form-Based Activities </p> </entry> <entry colname="col2"> <p>This release includes a new priority model for activities that use the Form-Based Experience Composer with only a global mbox. Before this release, content from multiple activities was returned to the page and overwrote content from other returned activities. Now, only the top priority activity's content is returned. </p> </entry> </row> --> 
  <tr> 
   <td colname="col1"> <p>at.js 1.6.3 </p> </td> 
   <td colname="col2"> <p>at.js version 1.6.3 is now available. </p> <p> 
     <ul id="ul_2C7CB74B1AAF4B52B6EB382977F7DC28"> 
      <li id="li_07CF8EDB25E24A7AB9B7A0F3402BAEB1"> <p>Selectors are now CSS-escaped if they contain IDs or CSS classes that start with a digit, two hyphens, or a hyphen followed by a digit (for example #-123). (TNT-31061) </p> </li> 
      <li id="li_6504E90D7C534A1BB9A2DE8510CE3B90"> <p>Fixed an issue introduced with at.js 1.6.2 where Visual Experience Composer (VEC) offers from different activities that apply to the same CSS selector did not respect activity priority. (TNT-31052) </p> </li> 
      <li id="li_D347CA513F1240E4BF79D757287AB30C"> <p>Fixed an issue with timing out a promise in environments where there was no native support for promises. (TNT-30974) </p> </li> 
      <li id="li_17F41A84CCFF41D7993E35DE10F87066"> <p>Issues are now correctly captured and reported via the content-rendering failed event. Previously, JavaScript might have been reported to have run successfully, even if that wasn't the case. (TNT-30599) </p> </li> 
     </ul> </p> <p>For more information, see <a href="../c-implementing-target/c-implementing-target-for-client-side-web/r-target-atjs-versions.md" format="dita" scope="local"> at.js Version Details</a>. </p> </td> 
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
  <!-- <row> <entry colname="col1"> <p>Form-Based Activities </p> </entry> <entry colname="col2"> <p>This release includes a new priority model for activities that use the Form-Based Experience Composer with only a global mbox. Before this release, content from multiple activities was returned to the page and overwrote content from other returned activities. Now, only the top priority activity's content is returned. </p> </entry> </row> --> 
  <tr> 
   <td colname="col1" class="premium"> <p>Personalization Insights reports </p> </td> 
   <td colname="col2"> <p>Two specialized reports are available to users of <span class="wintitle"> Automated Personalization (AP)</span> and <span class="wintitle"> Auto-Target (AT)</span> activities: </p> <p> 
     <ul id="ul_C338AC34C57C49E1A8DFA471167EC40A"> 
      <li id="li_2329BFC8CC524EBBA99C2F8EDC745B90"> <p><b><span class="wintitle"> Automated Segments</span>:</b> Different visitors respond differently to the offers/experiences in your AP/AT activity. This report shows how different automated segments defined by Target's personalization models responded to the offers/experiences in the activity. </p> </li> 
      <li id="li_48556C9BAD48476DA00DD666F5265E2B"> <p><b><span class="wintitle"> Important Attributes</span>:</b> In different activities, different attributes are more, or less, important to how the model decides to personalize. This report shows the top attributes that influenced the model and their relative importance. </p> </li> 
     </ul> </p> <p>See <a href="../c-reports/c-personalization-insights-reports/c-personalization-insights-reports.md" format="dita" scope="local"> Personalization Insights reports</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Product Documentation for Target Capabilities {#section_F03C61D438814538967B2BF901130BE4}

Use the following links to view product documentation for Target capabilities:

* [Adobe Target Learn &amp; Support](https://helpx.adobe.com/support/target.html)
* [Recommendations Classic help](https://marketing.adobe.com/resources/help/en_US/rec/)
* [Search&Promote help](https://marketing.adobe.com/resources/help/en_US/snp/)

## Prerelease Information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

To receive advance notifications about upcoming product enhancements, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
