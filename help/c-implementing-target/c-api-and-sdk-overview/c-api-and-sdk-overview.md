---
description: Information about Target Server Side delivery APIs, Recommendations APIs,
  and the NodeJS SDK.
keywords: server side;server-side;api;sdk;nodejs;node js;recommendations api
seo-description: Information about Target Server Side delivery APIs, Recommendations
  APIs, and the NodeJS SDK.
seo-title: Server Side  implement Target
solution: Target
title: Server Side  implement Target
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Server Side: implement Target{#server-side-implement-target}

Information about Target Server Side delivery APIs, Recommendations APIs, and the NodeJS SDK.

## Delivery APIs, NodeJS SDK, and Recommendations APIs Documentation {#section_D1D3A35EA6704594A2F7A0DC28DDEFCA}

The following table lists the various APIs and the NodeJS SDK and provides additional information:

<table id="table_A8DCB8FB8CBF4AA49FB562B9A3EB0E81"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type / Link </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="https://developers.adobetarget.com/api/#server-side-delivery" format="http" scope="external"> Server Side Delivery APIs</a> </p> <p>/res/v1/mbox </p> </td> 
   <td colname="col2"> <p>Adobe Target lets your application make mbox calls from any browser, mobile device, or even another server. The Server Side delivery API is specifically designed to integrate Adobe Target with any server-side platform that makes HTTP/HTTPS calls. </p> <p>You can use the API to integrate your custom application with Target. This is especially valuable for organizations that want to deliver targeting to a non-browser based IoT device, such as a connected TV, kiosk, or in-store digital screen. </p> <p>This endpoint can return offers for ordinary mboxes only. You can also fetch content for a single mbox only. </p> <p>This API implements existing mbox features in a RESTful manner. </p> <p>This API does not process cookies or redirect calls. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://developers.adobetarget.com/api/#server-side-batch-delivery" format="http" scope="external"> Server Side Batch Delivery APIs</a> </p> <p>/rest/v2/batchmbox </p> </td> 
   <td colname="col2"> <p>The Batch Delivery API lets your application request content for multiple mboxes in a single call. It also has a prefetch mode that enables clients like mobile apps, servers, and so forth to fetch content for multiple mboxes in one request, cache it locally, and later notify Target when the user visits those mboxes. </p> <p>This endpoint can return offers for ordinary mboxes only. Because you can fetch content for multiple mboxes, for performance, it makes more sense to use batch the mbox API. It lets you avoid executing multiple HTTP requests, which can be expensive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.npmjs.com/package/@adobe/target-node-client" format="https" scope="external"> NodeJS SDK</a> </p> </td> 
   <td colname="col2"> <p>In terms of SDKs, currently we have just one SDK, the NodeJS SDK. </p> <p>The NodeJS SDK is a thin wrapper around the NodeJS core HTTP/HTTPS module. Behind the scenes, the NodeJS SDK APIs use the same Server Side Delivery APIs. </p> <p>Here is the mapping: </p> <p> 
     <ul id="ul_9B959ED6F1AF4E0BA04084D74CAAE0B7"> 
      <li id="li_870A31104EAE4EE381608E813DB75BA7"> <p>MarketingCloudClient.getOffer() *- invokes */res/v1/mbox endpoint </p> </li> 
      <li id="li_51B95B848C5F4A438B0EAE9B7D0293E5"> <p>MarketingCloudClient.getOffers() *- invokes */res/v2/batchmbox endpoint </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.io/apis/experiencecloud/target/docs/getting-started.html" format="html" scope="external"> Target Recommendations APIs</a> </p> </td> 
   <td colname="col2"> <p>The Recommendations APIs enable you to programmatically interact with Target's recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the user interface. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Target Classic APIs </p> </td> 
   <td colname="col2"> <p>The Target Classic UI and APIs have been decommissioned. For information about switching to Target’s modern APIs, see <a href="../../c-implementing-target/c-api-and-sdk-overview/c-target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2" format="dita" scope="local"> Transitioning from Target Legacy APIs to Adobe I/O</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Differences Between Server Side Delivery APIs and the NodeJS SDK {#section_10336B7934F54CE98E35907A4748A4A4}

Many customers are confused about the differences between the Server Side delivery APIs and the NodeJS SDK. This is especially true when it comes to performance.

The following FAQs should help you decide which to use:

**When should you use "raw" Server Side APIs versus the NodeJS SDK?**

Ideally if you are using NodeJS as your backend technology, NodeJS SDK is a natural choice. The SDK handles a lot of details, such as cookies, headers, payload, and so forth. This lets you focus on the core of your application.

**Should I gain any performance improvements by using the NodeJS SDK?**

Unfortunately, we don't have any performance numbers. However, in general, the NodeJS SDK should good performance, thanks to the NodeJS event-driven architecture. Be aware that most of the time is spent on the Target backend. The NodeJS SDK does very little processing. The SDK is basically responsible for packaging a Target request and parsing a Target response.
