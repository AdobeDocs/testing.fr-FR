---
description: Information about the various methods you can use to get data into Target,
  including page parameters, in-page profile attributes, script profile attributes,
  data providers, the bulk profile update API, the single profile update API, and
  Customer Attributes.
keywords: implement;implementing;setting up;setup;page parameter;tomcat;url encoded;in-page
  profile attribute;mbox parameter;in-page profile attributes;script profile attribute;bulk
  profile update API;single file update API;customer attributes;data providers;dataprovider;data
  provider
seo-description: Information about the various methods you can use to get data into
  Target, including page parameters, in-page profile attributes, script profile attributes,
  data providers, the bulk profile update API, the single profile update API, and
  Customer Attributes.
seo-title: Methods to get data into Target
solution: Target
subtopic: Getting Started
title: Methods to get data into Target
topic: Standard
uuid: a6d64e39-6cdc-49fe-afe5-ecf7dcacf97d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Methods to get data into Target{#methods-to-get-data-into-target}

Information about the various methods you can use to get data into Target, including page parameters, in-page profile attributes, script profile attributes, data providers, the bulk profile update API, the single profile update API, and Customer Attributes.

## Page parameters (also called "mbox parameters") {#section_5A297816173C4FE48DC4FE03860CB42B}

<table id="table_AAD9DB05254A4CE196690EB97C303243"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definition/Details </p> </td> 
   <td colname="col2"> <p>Page parameters are name/value pairs passed in directly through page code that are not stored in the visitor's profile for future use. </p> <p>Page parameters are useful to send additional page data to Target that does not need to be stored with the visitor's profile for future targeting use. These values are instead used to describe the page or the action the user took on the specific page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>Page parameters are passed into Target via a server call as a string name/value pair. Parameter names and values are customizable (although there are some "reserved names" for specific uses). </p> <p>Examples: </p> <p>page=productPage </p> <p>categoryId=homeLoans </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example Use Cases </p> </td> 
   <td colname="col2"> <p>Product pages: Send information about the specific product viewed (this is how Recommendations works) </p> <p>Order details: Send order ID, orderTotal, and so forth for order collection </p> <p>Category affinity: Send category-viewed information to Target to build knowledge of the user's affinity to particular site categories </p> <p>3rd-party data: Send information from 3rd-party data sources, such as weather targeting providers, account data (for example, DemandBase), demographic data (for example Experian), and more. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benefits of Method </p> </td> 
   <td colname="col2"> <p>Data gets sent to Target in real-time, and can be used on the same server call the data on which it comes in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caveats </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_48E6B180B9984B1C937524C671DFB8B6"> 
      <li id="li_13DA7ECE7D744815BE6B5CF581B8525A"> <p>Requires page code update (directly or via a tag management system). </p> </li> 
      <li id="li_D419E3CA1FFB4AB3BD1CFCBE94142763"> <p>If the data needs to be used for targeting on a subsequent page/server call, it needs to be translated to a profile script. </p> </li> 
      <li id="li_74DF8228F033420DB5CABA1F6C358309"> <p>Query strings can contain only characters as per the <a href="https://www.ietf.org/rfc/rfc3986.txt" format="txt" scope="external"> Internet Engineering Task Force (IETF) standard </a>. </p> <p>In addition to those mentioned on the IETF site, Target allows the following characters in query stings: </p> <p>&lt; > # % " { } | \ ^ [] ` </p> <p>Everything else must be url-encoded. The standard specifies the following format ( <a href="https://www.ietf.org/rfc/rfc1738.txt" format="txt" scope="external"> https://www.ietf.org/rfc/rfc1738.txt </a>), as illustrated below: </p> <p> <img href="assets/ietf1.png" id="image_6EFD6F1CE7D44F67B60DEF72FE92C909" /> </p> <p>Or, the full list for simplicity: </p> <p> <img href="assets/ietf2.png" id="image_C0FD032BC10D4C7B9B5F8C2829D4D446" /> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Examples </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> targetPageParamsAll </span> (appends the parameters to all mbox calls on the page): </p> 
    <code>
      function targetPageParamsAll() { return "param1=value1&amp;param2=value2&amp;p3=hello%20world"; 
    </code> <p> <span class="codeph"> targetPageParams </span> (appends the parameters to the global mbox on the page): </p> 
    <code>
      function targetPageParams() {  return "param1=value1&amp;param2=value2&amp;p3=hello%20world"; 
    </code> <p>Parameters in mboxCreate code: </p> 
    <code>
      &lt;div class="mboxDefault">  default content to replace by offer &lt;/div> &lt;script>  mboxCreate('mboxName','param1=value1','param2=value2'); &lt;/script> 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Links to Relevant Information </p> </td> 
   <td colname="col2"> <p>Recommendations: <a href="../../../c-recommendations/c-plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC" format="dita" scope="local"> Implementation According to Page Type </a> </p> <p>Order confirmation: <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053" format="dita" scope="local"> Track Conversions </a> </p> <p>Category affinity: <a href="../../../c-target/c-visitor-profile/c-category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC" format="dita" scope="local"> Category Affinity </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## In-page profile attributes (also called "in-mbox profile attributes) {#section_57E1C161AA7B444689B40B6F459302B6}

<table id="table_D49DACF993624F00A76602C3D16E26D2"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definition/Details </p> </td> 
   <td colname="col2"> <p>In-page profile attributes are name/value pairs passed directly through page code that are stored in the visitor's profile for future use. </p> <p>In-page profile attributes allow user-specific data to be stored in Target's profile for later targeting and segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>In-page profile attributes are passed into Target via a server call as a string name/value pair with the prefix "profile." before the Attribute name. </p> <p>Attribute names and values are customizable (although there are some "reserved names" for specific uses). </p> <p>Examples: </p> <p> <span class="codeph"> profile.membershipLevel=silver </span> </p> <p> <span class="codeph"> profile.visitCount=3 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example Use Cases </p> </td> 
   <td colname="col2"> <p>Login information: Share non-PII (Personally Identifiable Information) data to Target based on the user's login. This could be membership status, order history, or more. </p> <p>Store info: Track which store is this user's preferred location. </p> <p>Previous interactions: Track what the user has done on the site previously to inform future personalization. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benefits of Method </p> </td> 
   <td colname="col2"> <p>Data gets sent to Target in real-time, and can be used on the same server call on which the data comes in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caveats </p> </td> 
   <td colname="col2"> <p>Requires page code updates (directly or via a tag management system). </p> <p>Attributes and values are visible in server calls, so a visitor can see the values. If sharing information such as credit ranges or other potentially private information, this might not be the best approach. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Examples </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> targetPageParamsAll </span> (appends the attributes to all mbox calls on the page): </p> 
    <code>
      function targetPageParamsAll() {  return "profile.param1=value1&amp;profile.param2=value2&amp;profile.p3=hello%20world"; } 
    </code> <p> <span class="codeph"> targetPageParams </span> (appends the attributes to the global mbox on the page): </p> 
    <code>
      function targetPageParams() {  return profile.param1=value1&amp;profile.param2=value2&amp;profile.p3=hello%20world"; }
    </code> <p>Attributes in mboxCreate code: </p> 
    <code>
      &lt;div class="mboxDefault"> default content to replace by offer &lt;/div> &lt;script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); &lt;/script> 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Links to Relevant Information </p> </td> 
   <td colname="col2"> <p> <a href="../../../c-target/c-visitor-profile/c-profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201" format="dita" scope="local"> Profile Attributes </a> </p> <p> <a href="../../../c-target/c-audiences/c-target-rules/c-visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E" format="dita" scope="local"> Visitor Profile </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Script profile attributes {#section_3E27B58C841448C38BDDCFE943984F8D}

<table id="table_EE8A6F42E61A48E88D64F89FEE8E3B69"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definition/Details </p> </td> 
   <td colname="col2"> <p>Script profile attributes are name/value pairs defined in the Target solution. The value is determined from executing a JavaScript snippet on Target's server per server call. </p> <p>Users write small code snippets that execute per mbox call, and before a visitor is evaluated for audience and activity membership. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>Script profile attributes are created in the Audiences section of Target. Any attribute name is valid, and the value is the result of a JavaScript function written by the Target user. The attribute name is automatically prefixed by " <span class="codeph"> user. </span>" in Target to distinguish them from in-page profile attributes. </p> <p>The code snippet is written in the Rhino JS language and can reference tokens and other values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example Use Cases </p> </td> 
   <td colname="col2"> <p>Cart Abandonment: When the visitor reaches the shopping cart, set the profile script to 1. When the visitor converts, reset it to 0. If the value =1, then the visitor has an item in the cart. </p> <p>Visit Count: On every new visit, increment the count by 1 to keep track of how often a visitor returns to the site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benefits of Method </p> </td> 
   <td colname="col2"> <p>Requires no page code updates. </p> <p>Executes before audience and activity membership decisions, so these profile script attributes can affect membership on a single server call. </p> <p>Can be very robust. As many as 2,000 instructions can be executed per script. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caveats </p> </td> 
   <td colname="col2"> <p>Requires JavaScript knowledge. </p> <p>The execution order of profile scripts cannot be guaranteed, so they cannot rely on each other. </p> <p>Can be difficult to debug. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Examples </p> </td> 
   <td colname="col2"> <p><b>Code Examples</b> </p> <p>Profile scripts are quite flexible: </p> 
    <code>
      user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; } 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Links to Relevant Information </p> </td> 
   <td colname="col2"> <p> <a href="../../../c-target/c-visitor-profile/c-profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2" format="dita" scope="local"> Profile Script Attributes </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Data Providers {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

<table id="table_6C9979535224484FA50FC596EA3BF133"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definition/Details </p> </td> 
   <td colname="col2"> <p>Data Providers is a capability that allows you to easily pass data from third parties to Target. </p> <p> <p>Note:  Data Providers requires <span class="filepath"> at.js </span> 1.3 or later. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> window.targetGlobalSettings.dataProviders </span> setting is an array of data providers. </p> <p>For more information about the structure for each data provider, see <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Data Providers </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example Use Cases </p> </td> 
   <td colname="col2"> <p>Collect data from a third party, such as a weather service, a DMP, or even your own web service. You can then use this data to build audiences, target content, and enrich the visitor profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benefits of Method </p> </td> 
   <td colname="col2"> <p>This setting lets customers gather data from third-party data providers, such as Demandbase, BlueKai, and custom services, and pass the data to Target as mbox parameters in the global mbox request. </p> <p>It supports the collection of data from multiple providers via async and sync requests. </p> <p>Using this approach makes it easy to manage flicker of default page content, while including independent timeouts for each provider to limit the impact on page performance </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caveats </p> </td> 
   <td colname="col2"> <p>If the data providers added to <span class="codeph"> window.targetGlobalSettings.dataProviders </span> are async, they will be executed in parallel. The Visitor API request will be executed in parallel with functions added to <span class="codeph"> window.targetGlobalSettings.dataProviders </span> to allow a minimum wait time. </p> <p> <span class="codeph"> at.js </span> won't try to cache the data. If the data provider fetches data only once, the data provider should make sure that data is cached and, when the provider function is invoked, serve the cache data for the second invocation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Examples </p> </td> 
   <td colname="col2"> <p>Several examples can be found in <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Data Providers </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Links to Relevant Information </p> </td> 
   <td colname="col2"> <p>Documentation: <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Data Providers </a> </p> <p>Training Videos: </p> <p> 
     <ul id="ul_E85E32034ECC4E7781A7FBF982998918"> 
      <li id="li_3885523E41D94234A11438334D2E8B4F"> <p> <a href="https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html" format="html" scope="external"> Using Data Providers in Adobe Target </a> </p> </li> 
      <li id="li_77786BA65FCA4A188A5F87330272701B"> <p> <a href="https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html" format="html" scope="external"> Implement Data Providers in Adobe Target </a> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bulk profile update API {#section_92AB4820A5624C669D9A1F1B6220D4FA}

<table id="table_4DA330A794C047A7B14B340A4A9A7583"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definition/Details </p> </td> 
   <td colname="col2"> <p>Via API, send a .csv file to Target with visitor profile updates for many visitors. Each visitor profile can be updated with multiple in-page profile attributes in one call. </p> <p>This option is very similar to Customer Attributes with a few differences: </p> <p> 
     <ul id="ul_75EFDFD9534541E3BBB1A99228E5D0A2"> 
      <li id="li_2F36B7D3580D4AB7983A0EEBBEAD43F4"> <p>Customer Attributes use an FTP upload while the Target Bulk Profile Update API uses an HTTP POST API. </p> </li> 
      <li id="li_C1CB5D8CDB0C4F18AC08D3E506FFB38E"> <p>Customer Attributes data can be shared with Analytics. Bulk Profile Update is useable only in Target. </p> </li> 
      <li id="li_7AE2B90224C54ECE88BE807E2011141D"> <p>Customer Attributes support creating a profile for a user Target has not yet seen. The Bulk Profile Update API updates existing Target profiles only. </p> </li> 
      <li id="li_B7DDD5613526421CBA901B10E2DDAC2E"> <p>Customer Attributes require the use of the Experience Cloud ID (ECID). The Bulk Profile Update API requires either the TNT ID or the <span class="codeph"> mbox3rdPartyId </span>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>The .csv file must refer to each visitor via his or her Target PCID or <span class="codeph"> mboxThirdPartyId </span>. The Experience Cloud ID (ECID) is not supported. All profile attributes/values are created and updated via the API. Format details are available in the API documentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example Use Cases </p> </td> 
   <td colname="col2"> <p>Your CRM or other internal system stores valuable data about your visitors that you want to consistently update into Target, without exposing the profile data in your page implementation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benefits of Method </p> </td> 
   <td colname="col2"> <p>No limit on the number of profile attributes. </p> <p>Profile attributes sent via the site can be updated via the API and vice versa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caveats </p> </td> 
   <td colname="col2"> <p>The size of the batch file must be less than 50 MB. In addition, the total number of rows should not exceed 500,000 rows per upload. </p> <p>There is no limit on the number or rows you can upload over a period of 24 hours in subsequent batches. However, the ingestion process might be throttled during business hours to ensure that other processes run efficiently. </p> <p>Consecutive <a href="https://developers.adobetarget.com/api/#updating-profiles" format="http" scope="external"> V2 batch update calls </a> without mbox calls in between for the same thirdPartyIds override the properties updated in the first batch update call. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Examples </p> </td> 
   <td colname="col2"> <p>See <a href="https://developers.adobetarget.com/api/#updating-profiles" format="http" scope="external"> Updating Profiles </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Links to Relevant Information </p> </td> 
   <td colname="col2"> <p> <a href="https://developers.adobetarget.com/api/#updating-profiles" format="http" scope="external"> Updating Profiles </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Single profile update API {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

<table id="table_DEDF4A08D1A7478BA4388F85545FD5DE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definition/Details </p> </td> 
   <td colname="col2"> <p>Almost identical to the Bulk Profile Update API, but one visitor profile is updated at a time, in line in the API call instead of with a .csv file </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>The visitor must be identified via the Target <span class="codeph"> mboxPC </span> value or <span class="codeph"> mboxThirdPartyId </span> value. The Experience Cloud ID (ECID) is not supported. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example Use Cases </p> </td> 
   <td colname="col2"> <p>You want to update Target in real-time when a visitor performs some offline action, such as reaching a call center, a loan is funded, using a loyalty card in store, accessing a kiosk, and so forth. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benefits of Method </p> </td> 
   <td colname="col2"> <p>No limit on the number of profile attributes. </p> <p>Profile attributes sent via the site can be updated via the API and vice versa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caveats </p> </td> 
   <td colname="col2"> <p>Limit of 1,000,000 API calls (1 million) per 24-hour period </p> <p> Updates profiles only. Cannot create a profile for a potential user Target has yet to see. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Examples </p> </td> 
   <td colname="col2"> <p>GET and POST supported. 
     <code>
       https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&amp;profile.attr1=0&amp;profile.attr2=1... 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Links to Relevant Information </p> </td> 
   <td colname="col2"> <p> <a href="https://developers.adobetarget.com/api/#updating-profiles" format="http" scope="external"> Updating Profiles </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Attributes {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

<table id="table_98FDD56F970D4CEA9F722248FA74AD9F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definition/Details </p> </td> 
   <td colname="col2"> <p>Customer attributes let you upload visitor profile data via FTP to the Experience Cloud. Once uploaded, leverage the data in Adobe Analytics and Adobe Target. </p> <p>Target Standard customers can leverage 5 attributes, Target Premium customers can leverage 200 attributes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>A .csv file with Experience Cloud IDs (ECIDs) and attribute name/value pairs is uploaded via FTP or manually in the Experience Cloud UI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Example Use Cases </p> </td> 
   <td colname="col2"> <p>Your CRM or other internal system stores valuable information you want to share with Adobe's Experience Cloud, including Target and Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benefits of Method </p> </td> 
   <td colname="col2"> <p>Uploading customer data creates a profile entry for that visitor in Target, even if Target has yet to see the visitor. </p> <p>Same data is automatically available in Target and Analytics. </p> <p>FTP can be a simpler implementation method than API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caveats </p> </td> 
   <td colname="col2"> <p>Target Standard customers can leverage 5 attributes, Target Premium customers can leverage 200 attributes </p> <p>Can only update values via Customer Attributes, not on page. </p> <p>Requires Experience Cloud ID (ECID) implementation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Examples </p> </td> 
   <td colname="col2"> <p>Details can be found in <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html" format="html" scope="external"> Create a Customer Attribute Source and Upload the Data File </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Links to Relevant Information </p> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html" format="html" scope="external"> Create a Customer Attribute Source and Upload the Data File </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

