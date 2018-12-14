---
description: Information to help you use transition from the Target legacy APIs to
  the new APIs on Adobe I/O.
keywords: api;adobe i/o
seo-description: Information to help you use transition from the Target legacy APIs
  to the new APIs on Adobe I/O.
seo-title: Transition from Target legacy APIs to Adobe I/O
solution: Target
title: Transition from Target legacy APIs to Adobe I/O
topic: Standard
uuid: f8a0ab54-5840-4430-b9be-19e689b1c09a
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Transition from Target legacy APIs to Adobe I/O{#transition-from-target-legacy-apis-to-adobe-i-o}

Information to help you use transition from the Target legacy APIs to the new APIs on Adobe I/O.

With the decommissioning of Adobe Target Classic, the APIs that are connected to your Target Classic account have also been made unavailable. This document will help you transition your legacy API-based integrations to the Target APIs powered by Adobe I/O.

For more information about the Target API documentation, see [Target APIs and NodeJS SDK](../../c-implementing-target/c-api-and-sdk-overview/c-api-and-sdk-overview.md#concept_5718EC1FF2ED4436935D0BCCD7AA29A6).

## Terminology {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

<table id="table_3228619660E54F029F4834236BEFE19B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Term </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Legacy API </p> </td> 
   <td colname="col2"> <p>APIs that are linked to your Target Classic account. These API calls are based on a username and password-based authentication and use the hostname <span class="filepath"> testandtarget.omniture.com</span>. If your API calls contain a user name and password in the request URL, you must transition to Adobe I/O APIs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adobe I/O </p> </td> 
   <td colname="col2"> <p><b>Adobe I/O:</b> Adobe I/O is the new gateway for Target APIs. These APIs are connected to your Target Standard/Premium account. The Target APIs on Adobe I/O use a JWT-based authentication, which is the industry standard for secure enterprise APIs. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Timeline {#section_A478EBF637554A2DB5A31661955121ED}

The legacy APIs will be decommissioned when you Target Classic is decommissioned:

<table id="table_BE395755732E4DC1915A72EE72D57CA8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Date </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>October 17, 2017 </p> </td> 
   <td colname="col2"> <p>All API methods that perform a write operation (<span class="codeph"> saveCampaign</span>, <span class="codeph"> copyCampaign</span>, <span class="codeph"> saveHTMLOfferContent</span>, and <span class="codeph"> setCampaignState</span>) were decommissioned. </p> <p>This is the same date when all Target Classic user accounts were set to read-only status. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>November 14, 2017 </p> </td> 
   <td colname="col2"> <p>The remaining APIs were decommissioned. </p> <p>This is the date when the Target Classic user interface was decommissioned </p> </td> 
  </tr> 
 </tbody> 
</table>

Recommendations Classic APIs won’t be impacted by this time line.

## Equivalent Methods {#section_DDB42CCC172545B09CB728D794CC466B}

The following table lists the equivalent new Target API methods for the legacy API methods. The new APIs return JSON when compared to the XML response provided by the legacy APIs.

The new API methods are linked to the corresponding section in the API documentation site. An example is provided for each API method. You can also use the Admin Postman Collection that contains sample API calls for all the new Adobe API methods on Adobe I/O.

<table id="table_C7A209501D99423DB13D513F54427277"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Grouping </th> 
   <th colname="col2" class="entry"> Legacy API Method </th> 
   <th colname="col3" class="entry"> New API Method </th> 
   <th colname="col4" class="entry"> Notes </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Campaign/Activity </p> </td> 
   <td colname="col2"> <p>Campaign Create </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#create-ab-activity" format="http" scope="external"> Create AB Activity</a> </p> <p><a href="https://developers.adobetarget.com/api/#create-xt-activity" format="http" scope="external"> Create XT Activity</a> </p> </td> 
   <td colname="col4"> <p>The new APIs provide separate create methods for AB and XT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Campaign Update </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#update-ab-activity" format="http" scope="external"> Update AB Activity</a> </p> <p><a href="https://developers.adobetarget.com/api/#update-xt-activity" format="http" scope="external"> Update XT Activity</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Copy Campaign </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
   <td colname="col4"> <p>Use the Activity Create APIs </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Campaign List </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#list-activities" format="http" scope="external"> List Activities</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Campaign State </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#update-activity-state" format="http" scope="external"> Update Activity State</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Campaign View </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#get-ab-activity-by-id" format="http" scope="external"> Get AB Activity by ID</a> </p> <p><a href="https://developers.adobetarget.com/api/#get-xt-activity-by-id" format="http" scope="external"> Get XT Activity by ID</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Third-Party Campaign ID </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
   <td colname="col4"> <p>If you are using a thirdpartyID, the relevant Activity methods can be used </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Offers </p> </td> 
   <td colname="col2"> <p>Offer Create </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#create-offer" format="http" scope="external"> Create Offer</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Offer Get </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#get-offer-by-id" format="http" scope="external"> Get Offer by ID</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Offer List </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#list-offers" format="http" scope="external"> List Offers</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Folder List </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
   <td colname="col4"> <p>Folders aren’t supported in Target Standard/Premium </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reporting </p> </td> 
   <td colname="col2"> <p>Campaign Performance Report </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#get-ab-performance-report" format="http" scope="external"> Get AB Performance Report</a> </p> <p><a href="https://developers.adobetarget.com/api/#get-xt-performance-report" format="http" scope="external"> Get XT Performance Report</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Audit Report </p> </td> 
   <td colname="col3"><a href="https://developers.adobetarget.com/api/#get-audit-report" format="http" scope="external"> Get Audit Report </a> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>1-1 Content Report </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#get-ap-activity-performance-report" format="http" scope="external"> Get AP Performance Report</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account Settings </p> </td> 
   <td colname="col2"> <p>Get Host Groups </p> </td> 
   <td colname="col3"> <p><a href="https://developers.adobetarget.com/api/#list-environments" format="http" scope="external"> List Environments</a> </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

## Exceptions {#section_09CF9A0E289149279783B4801D1B6D4C}

If you require an exception, please contact your Customer Success Manager.

## Help {#section_591F850E2B7A4342B1C233693425415C}

Please contact Adobe Target Client Care (tt-support@adobe.com) if you have any questions or need help transitioning to the new Target APIs on Adobe I/O.
