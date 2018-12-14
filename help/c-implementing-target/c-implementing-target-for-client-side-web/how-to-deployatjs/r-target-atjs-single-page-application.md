---
description: There are many options for implementing Target in single-page applications
  with at.js.
keywords: single page application implementation;implement single page application;spa;ngroute;ui
  router;Component;directive;custom event;hashchange
seo-description: There are many options for implementing Target in single-page applications
  with at.js.
seo-title: Single Page Application implementation
solution: Target
title: Single Page Application implementation
topic: standard
uuid: 5887ec53-e5b1-40f9-b469-33685f5c6cd6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Single Page Application implementation{#single-page-application-implementation}

There are many options for implementing Target in single-page applications with at.js.

Use a combination of the following techniques for the best capabilities. We strongly recommend that you implement [!DNL Target] using [!DNL Adobe Launch], a free Core Service offering that can be used to quickly adapt your [!DNL Target] implementation as needed. For more information, see [Implementing Target using Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25).

<table id="table_A228B59A06454E9E80732400BD8242D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Implementation </th> 
   <th colname="col2" class="entry"> Framework </th> 
   <!-- <entry colname="col3">Pros </entry> <entry colname="col4">Cons </entry> --> 
   <th colname="col5" class="entry"> DTM-Implementable? </th> 
   <th colname="col6" class="entry"> Recommended mbox Name </th> 
   <th colname="col7" class="entry"> Demo/Documentation </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ngRoute </p> </td> 
   <td colname="col2"> <p>Angular </p> </td> 
   <!-- <entry colname="col3"> <p> <ul id="ul_FB3B7021365B4536876A9ACC8495EA29"> <li id="li_21EE6E9161184724BBED3FD10411EF43"> Earliest possible firing of an mbox on the route change </li> <li id="li_2A456D69B54241C99F2AA2513046215A">Excellent flicker handling. Enforces sequencing of the mbox response and DOM updates, offering excellent capabilities for flicker-control when used with DOM-manipulation type offers. </li> </ul> </p> </entry> <entry colname="col4"> Might fire before you have updated your data layer </entry> --> 
   <td colname="col5"> <p>Yes </p> </td> 
   <td colname="col6"> <p>target-global-mbox </p> </td> 
   <td colname="col7"> <p><a href="https://adobe-marketing-cloud.github.io/target-atjs-extensions/examples/angular/route_change_demo.html" scope="external" format="html"> Demo</a> </p> <p> <a href="https://github.com/Adobe-Marketing-Cloud/target-spa-extensions/wiki/Angular-ngRoute" scope="external" format="http"> Documentation</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ui-router </p> </td> 
   <td colname="col2"> <p>Angular </p> </td> 
   <!-- <entry colname="col3"> <p> <ul id="ul_09E8114B138748ED9AC7971A87FFBF6C"> <li id="li_6DC9942B0E16473E88CC62F80ADFE236"> Earliest possible firing of an mbox on the route change </li> <li id="li_CAB6CCFE15104687800325F6C13C0685"> Excellent flicker handling. Enforces sequencing of the mbox response and DOM updates, offering excellent capabilities for flicker-control when used with DOM-manipulation type offers. </li> </ul> </p> </entry> <entry colname="col4">Might fire before you have updated your data layer </entry> --> 
   <td colname="col5"> <p>Yes </p> </td> 
   <td colname="col6"> <p>target-global-mbox </p> </td> 
   <td colname="col7"> <p><a href="https://adobe-marketing-cloud.github.io/target-atjs-extensions/examples/angular/state_change_demo.html" scope="external" format="html"> Demo</a> </p> <p><a href="https://github.com/Adobe-Marketing-Cloud/target-spa-extensions/wiki/Angular-UIRouter" scope="external" format="http"> Documentation</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Directive </p> </td> 
   <td colname="col2"> <p>Angular </p> </td> 
   <!-- <entry colname="col3"> Excellent flicker handling </entry> <entry colname="col4"> Requires use of the form-based composer </entry> --> 
   <td colname="col5"> <p>Yes </p> </td> 
   <td colname="col6"> <p>Custom per content </p> </td> 
   <td colname="col7"> <p><a href="https://adobe-marketing-cloud.github.io/target-atjs-extensions/examples/angular/directive_example.html#/view1" scope="external" format="html"> Demo</a> </p> <p><a href="https://github.com/Adobe-Marketing-Cloud/target-spa-extensions/wiki/Angular-Directive" scope="external" format="http"> Documentation</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Component </p> </td> 
   <td colname="col2"> <p>React </p> </td> 
   <td colname="col5"> <p>No </p> </td> 
   <td colname="col6"> <p>Custom per content </p> </td> 
   <td colname="col7"> <p><a href="https://adobe-marketing-cloud.github.io/target-atjs-extensions/examples/react/react_component_demo.html" scope="external" format="html"> Demo</a> </p> <p><a href="https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions/wiki/React-Component" scope="external" format="https"> Documentation</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom event </p> </td> 
   <td colname="col2"> <p>All </p> </td> 
   <!-- <entry colname="col3"> <p> <ul id="ul_6761725AEDB1433F81432A87419B1FDC"> <li id="li_A99AB34FAE294E309F6457BC22962677"> Richest possible information for targeting and segmenting available passed with the mbox call </li> <li id="li_07AA645BEA7641498DA1C25438C87A74"> Works great with adding new content </li> </ul> </p> </entry> <entry colname="col4"> No guarantee of flicker-handling. No sequencing of DOM updates with mbox calls, which might result in flicker of default content. </entry> --> 
   <td colname="col5"> <p>Yes </p> </td> 
   <td colname="col6"> <p>target-global-mbox </p> </td> 
   <td colname="col7"> <p>
     <!--Demo/--><a href="https://github.com/Adobe-Marketing-Cloud/target-spa-extensions/wiki/Custom-Event" scope="external" format="http"> Documentation</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hashchange </p> </td> 
   <td colname="col2"> <p>All </p> </td> 
   <!-- <entry colname="col3"> <p> <ul id="ul_D27476145B8841FEB4B020FDE87CE1D1"> <li id="li_A721ECBEA3E9435386C5CC240D47F249"> Easiest to implement </li> <li id="li_FAD0033B8F134252B34C173CC005A299">Works great with adding new content </li> </ul> </p> </entry> <entry colname="col4"> No guarantee of flicker-handling. No sequencing of DOM updates with mbox calls, which might result in flicker of default content. </entry> --> 
   <td colname="col5"> <p>Yes </p> </td> 
   <td colname="col6"> <p>target-global-mbox </p> </td> 
   <td colname="col7"> <p><a href="https://adobe-marketing-cloud.github.io/target-atjs-extensions/examples/angular/hash_change_event.html" scope="external" format="html"> Demo</a> </p> <p><a href="https://github.com/Adobe-Marketing-Cloud/target-spa-extensions/wiki/Hash-Change" scope="external" format="http"> Documentation</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>If you previously used [ `mboxUpdate()`](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_61B2B9F351344CF5B0915D5AFD21C5FE) or TNT.createGlobalMbox() to fire the global mbox on view changes within your app, you need to migrate to using a [combination of `getOffer()` and `applyOffer()`](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_BBE83F513B5B4E03BBC3F50D90864245) for this purpose.

>[!NOTE]
>
>If you are using the Analytics for Target (A4T) implementation, ensure that you complete Step 8 in [Analytics for Target Implementation](../../../c-integrating-target-with-mac/a4t/c-a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A).

