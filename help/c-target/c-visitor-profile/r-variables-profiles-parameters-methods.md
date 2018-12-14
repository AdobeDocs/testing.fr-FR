---
description: This page lists profiles, variables, and parameters that are useful in
  profile scripts.
keywords: variables;profiles;parameters;built in profiles;methods;url variables;geo
  profiles;third party profiles;mbox variables;campaign variables;customer attributes
seo-description: This page lists profiles, variables, and parameters that are useful
  in profile scripts.
seo-title: Profile and variable glossary
solution: Target
title: Profile and variable glossary
topic: Standard
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Profile and variable glossary{#profile-and-variable-glossary}

This page lists profiles, variables, and parameters that are useful in profile scripts.

## Built-In Profiles {#section_2B694370003C4F8E8E29E0B2F6E52045}

<table id="table_8F26DFF396244388A98F3CD0E776FF44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Profile </th> 
   <th colname="col2" class="entry"> Notes </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.activeActivities </span> </p> <p> <span class="codeph"> user.activeCampaigns </span> </p> </td> 
   <td colname="col2"> <p>Return the campaign ID for all campaigns/activities that the user is in, even if he or she has not interacted with the campaign/activity in the current session. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.pcId </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.sessionId </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.categoryAffinity </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.categoryAffinities </span> </p> </td> 
   <td colname="col2"> <p> Return an array of the affinities that a visitor has populated </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.isFirstSession </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.isNewSession </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.daysSinceLastVisit </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.browser </span> </p> </td> 
   <td colname="col2"> <p>The user agent </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header </span> </p> </td> 
   <td colname="col2"> <p>All <span class="codeph"> user.header </span> profiles are built-in from mbox request header data </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('x-cluster-client-ip') </span> </p> </td> 
   <td colname="col2"> <p>The public-facing IP address of the network connection that the visitor is on. </p> <p>You can get this in several ways, for example <span class="filepath"> whatismyip.com </span>. The IP address is not the NAT address (internal address), starting with 10., 192.168., or 172. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('host') </span> </p> </td> 
   <td colname="col2"> <p>Website hostname </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('cookie') </span> </p> </td> 
   <td colname="col2"> <p>Visitor cookie data </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('user-agent') </span> </p> </td> 
   <td colname="col2"> <p>Visitor browser user-agent </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('accept-language') </span> </p> </td> 
   <td colname="col2"> <p>Visitor language </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('accept-encoding') </span> </p> </td> 
   <td colname="col2"> <p>Visitor character encoding </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('accept') </span> </p> </td> 
   <td colname="col2"> <p>Visitor language and character encoding </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('connection') </span> </p> </td> 
   <td colname="col2"> <p>Server connection. For example: <span class="codeph"> keep-live </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.header('referer') </span> </p> </td> 
   <td colname="col2"> <p>Website URL of visitor current page. Does not work for Internet Explorer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.getLocal('param_name','value'); </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.setLocal('param_name','value'); </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.get('param_name') </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> user.parameter </span> </p> </td> 
   <td colname="col2"> <p> Persistent profile attributes created from profile scripts. Also references “system” profiles like geolocation, visit count, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> profile.get('param_name') </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> profile.param('param_name'); </span> </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> profile.parameter('parameter_name'); </span> </p> </td> 
   <td colname="col2"> <p>Mbox parameters that are made persistent due to their <span class="codeph"> profile. </span> prefix. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> profile.browserTime </span> </p> </td> 
   <td colname="col2"> <p>The visitor's local browser time. For system time, create a new date object in the profile script </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> profile.averageDaysBetweenVisits </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> profile.sessionCount </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> parameter= </span> </p> </td> 
   <td colname="col2"> <p>Generic term for additional values passed with an mbox, usually as name/value pairs. Not persistent unless made so with <span class="codeph"> profile.parameter </span> or <span class="codeph"> user.parameter </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## URL Variables {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## Geo and Mobile Carrier Profiles {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## Mbox Variables {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

<table id="table_1AC13D7874F942349086851980DD5606"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Notes </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.name </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.param('param_name') </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parameters automatically passed with every request: </p> <p> 
     <ul id="ul_67A44986D47745E886A9F0FEDD65832B"> 
      <li id="li_CCBFA7DB2C5F4B0988C59B7B7DB68F5F"> <span class="codeph"> mbox.param('browserHeight') </span> </li> 
      <li id="li_594E67B2FDB1448AA6D3FF769DE3D857"> <span class="codeph"> mbox.param('browserTimeOffset') </span> </li> 
      <li id="li_A935E111B83A42CC8E159B1D3562ABB7"> <span class="codeph"> mbox.param('browserWidth') </span> </li> 
      <li id="li_E48FA9B53D384A69B314426C04A84AAA"> <span class="codeph"> mbox.param('colorDepth') </span> </li> 
      <li id="li_FE70A416B6BC46FAAB7CC7A360C38399"> <span class="codeph"> mbox.param('mboxXDomain') </span> </li> 
      <li id="li_8CEB7C8B2F7B455DA5DF175EAB14BC9F"> <span class="codeph"> mbox.param('mboxTime') </span> </li> 
      <li id="li_2C43D1FFEA3D43A8A60360C131ED4C66"> <span class="codeph"> mbox.param('screenHeight') </span> </li> 
      <li id="li_9F3C670289A34187BCBAEE2327C1FB54"> <span class="codeph"> mbox.param('screenWidth') </span> </li> 
     </ul> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parameters passed with order mboxes: </p> <p> 
     <ul id="ul_51D2BF83365F45F0BA72B9D874B025B6"> 
      <li id="li_1EB644FDDD044AEF9F6A2BED55762090"> <span class="codeph"> mbox.param('orderId') </span> </li> 
      <li id="li_2EC9F67E2E214DDA9F90AE09FA99F7BE"> <span class="codeph"> mbox.param('orderTotal') </span> </li> 
      <li id="li_468EC01B4EF745ACA4FDFE58A297071A"> <span class="codeph"> mbox.param('productPurchasedId') </span> </li> 
     </ul> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox3rdPartyId </span> </p> </td> 
   <td colname="col2"> <p>An mbox parameter to sync a customer ID to Target's mboxPCID. A customer ID is an ID your company uses to track visitors, such as a CRM ID, membership ID, or something similar. This ID can then be used to add information via the Profile APIs and <a href="../../c-target/c-visitor-profile/c-working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8" format="dita" scope="local"> Customer Attributes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxPageValue </span> </p> </td> 
   <td colname="col2"> <p>In each mbox call the page is assigned a value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxDebug </span> </p> </td> 
   <td colname="col2"> <p>Only used for debug info. Added to the page url where the <span class="filepath"> mbox.js </span> looks for it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxOverride.browserIp </span> </p> </td> 
   <td colname="col2"> <p>Sets a different geo than the actual location so you can test how something would look in another location. </p> <p> <p>Note:  Using mboxOverride parameters should be used only while testing the activity and not in production. The use of any <span class="codeph"> mboxOverride </span> parameters can cause reporting discrepancies when using <a href="../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE" format="dita" scope="local"> Analytics for Target </a> (A4T). You should use <a href="../../c-activities/c-activity-qa/c-activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40" format="dita" scope="local"> Activity QA mode </a> while testing to ensure that your activity works as expected before pushing the activity into your live environment. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Attributes {#section_62B4821EB6564FF4A14159A837AD4EDB}

Customer attributes can be referenced in profile scripts, formatted as ` crs.get('< *`Datasource Name`*>.< *`Attribute name`*>')`.

These attributes are also available as tokens in profile scripts and directly in offers without first requiring a profile script. The token should be in the form: ` $crs. *`datasourceName`*. *`attributeName`*`.
