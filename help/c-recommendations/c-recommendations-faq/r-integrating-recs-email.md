---
description: Information about the ways to integrate email with Recommendations.
keywords: email;ESP;email service provider;rawbox;delivery API;download-only template;email
  template;batch processing;build-time email
seo-description: Information about the ways to integrate email with Recommendations.
seo-title: Integrate Recommendations with email
solution: Target
title: Integrate Recommendations with email
title-outputclass: premium
topic: Recommendations
uuid: ae137d7c-58c5-4601-92fc-2dc5548760fd
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Integrate Recommendations with email{#integrate-recommendations-with-email}

Information about the ways to integrate email with Recommendations.

Your email service provider's capabilities determine which method to use. Your account manager or consultant can help you choose the option that will work best for you.

## Option 1: Use the Delivery API {#section_9F00D271BABA4B7390B461F4C44EC319}

The delivery API is a POST request that works with build-time email. This option is the preferred method for build-time email.

Most email clients do not allow POST requests; therefore, this API is not recommended for open-time use cases. Some email clients, such as Gmail or Outlook, might cache the content or block the image and require the recipient to pro-actively allow the image to render.

You cannot return default content using the delivery API.

The following code is a sample API delivery request:

```
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

Where `clientcode` is your Target client code.

>[!NOTE]
>
>Be sure to provide a unique value for both `sessionId` and one of `tntId` or `thirdPartyId` for each email recipient (for example, for each API call). If you do not provide unique values for these fields, API response might slow or fail due to the large number of events generated within a single profile.

See [Delivery API documentation](https://developers.adobetarget.com/api/#server-side-delivery) for more information.

## Option 2: Use a Rawbox Email Template {#section_C0D48A42BCCE45D6A68852F722C7C352}

A rawbox is similar to an mbox request, but for non-Web environments, such as email service providers (ESPs). Because you don't have [!DNL mbox.js] or [!DNL at.js] to use in rawbox requests, you must create your requests manually. The examples below explain how to work with rawbox requests in email.

This approach allows you to track performance of recommendations in emails, test them in the normal way with a recommendation, and continue tracking on the site.

Set up a [!DNL Recommendations] activity in [!DNL Adobe Target], using the [Form-Based Experience Composer](../../c-experiences/t-form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) option. For the location, select the name of the mbox you've chosen to use in the rawbox request coming from the ESP. Select a design with the look and feel you want for your email. At email build time, the ESP makes a call to the [!DNL Adobe Target] servers for each rawbox in each email being generated. Your ESP must have a way to include the returned HTML in the email when it is sent.

The email system you use should be capable of handling these scenarios:

<table id="table_2C52E771EBA94C999A9C87A6CDE473C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Scenario </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A valid response is received, but no recommendations are present. </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_651BBA215E0F44ADBA0070A253B71375"> 
      <li id="li_056C20D1FB864D0DAA89DD2D9B9B02D0"> <p>In this case, the response will be whatever is set as the <span class="codeph"> mboxDefault </span> parameter value. See explanation below on this parameter. </p> </li> 
      <li id="li_CC3F79E7892B411C822AF3FDBC11DBD5"> <p>The email provider should have a default HTML block of recommendations to use in this case. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> The Target server times out and returns without data. </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_169613D5B5054303BD2055E41F377B63"> 
      <li id="li_40ABA222FA384ADFB4027EB415E00958"> <p> In this case, the <span class="keyword"> Target </span> server will return the following content: </p> <p> <span class="codeph"> //ERROR: application server timeout </span> </p> </li> 
      <li id="li_F58E0C5EF6FF4079BD1AB002FE137363"> <p>The email application should search for that text and be able to handle the error. The email provider has multiple options for handling this case: </p> 
       <ul id="ul_FF19400B34B340FCB0D1910DEAC73F04"> 
        <li id="li_8B2F0B203B684F32AE57231B8C735291"> <p>Try another server call immediately (recommended, perhaps with an attempt counter). </p> </li> 
        <li id="li_5B178AC437BB41D1ACEFF6C2E3394505"> <p>Toss out that particular email and continue to the next one. </p> </li> 
        <li id="li_AC8A1872FE684441A6F82861C723C745"> <p>Queue that particular email and re-run failed emails as a batch at the end of the initial run. </p> </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Sample request URL:**

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

**Required parameters:**

>[!NOTE]
>
>To use [!DNL Recommendations] in email, the rawbox call usually must include either the `entity.id` or `entity.categoryId` or both, depending on the type of recommendation criteria. The sample call above includes both.

<table id="table_4F7443A8A46C4369AC4B8EB76F0292F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col02" class="entry"> Value </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Validation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> client_code </span> </p> </td> 
   <td colname="col02"> <p><i>client_code</i> </p> </td> 
   <td colname="col2"> <p>The client’s code used in Recommendations. Your Adobe consultant can provide this value. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> mbox </span> </p> </td> 
   <td colname="col02"> <p><i>mboxName</i> </p> </td> 
   <td colname="col2"> <p>The mbox name that is used for targeting. </p> </td> 
   <td colname="col4"> <p>Same validation as for all mbox calls. </p> <p>250 character limit. </p> <p>Cannot contains any of the following characters: ', ", %22, %27, &lt;, >, %3C, %3E </p> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> mboxXDomain </span> </p> </td> 
   <td colname="col02"> <p>disabled </p> </td> 
   <td colname="col2"> <p>Prevents the response from setting a cookie in non-web environments. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> entity.id </span> </p> <p>(Required for certain types of criteria: view/view, view/bought, bought/bought) </p> </td> 
   <td colname="col02"> <p><i>entity_id</i> </p> </td> 
   <td colname="col2"> <p>The productId the recommendation is based on, such as an abandoned product in the cart, or a previous purchase. </p> <p>If required by the criteria, the rawbox call must include the <span class="codeph"> entity.id </span>. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> entity.event.detailsOnly </span> </p> </td> 
   <td colname="col02"> <p>true </p> </td> 
   <td colname="col2"> <p>If entity.id is passed, it is highly recommended to also pass this parameter to prevent the request from incrementing the number of tallied page views for an item, so as not to skew product view-based algorithms. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> entity.categoryId </span> </p> <p>(Required for certain types of criteria: most viewed by category and top sellers by category) </p> </td> 
   <td colname="col02"> <p><i>category_id</i> </p> </td> 
   <td colname="col2"> <p>The category the recommendation is based on, such as top sellers in a category. </p> <p>If required by the criteria, the rawbox call must include the <span class="codeph"> entity.categoryId </span>. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> mboxDefault </span> </p> </td> 
   <td colname="col02"> <p><i>https://www.default.com</i> </p> </td> 
   <td colname="col2"> If the <span class="codeph"> mboxNoRedirect </span> parameter is not present, <span class="codeph"> mboxDefault </span> should be an absolute URL that will return default content if no recommendation is available. This can be an image or other static content. <p>If the <span class="codeph"> mboxNoRedirect </span> parameter is present, <span class="codeph"> mboxDefault </span> can be any text indicating there are no recommendations, for example <span class="codeph"> no_content </span>. </p> <p>The email provider will need to handle the case where this value is returned and insert default HTML into the email. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> mboxHost </span> </p> </td> 
   <td colname="col02"> <p><i>mbox_host</i> </p> </td> 
   <td colname="col2"> <p>This is the domain that is added to the default environment (host group) when the call fires. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> mboxPC </span> </p> </td> 
   <td colname="col02"> <p>Empty </p> </td> 
   <td colname="col2"> <p>(Required for recommendations that use a visitor's profile.) </p> <p>If no “thirdPartyId” was provided, a new tntId is generated and returned as part of the response. Otherwise remains empty. </p> <p> <p>Note:  Be sure to provide a unique value of <span class="codeph"> mboxSession </span> and <span class="codeph"> mboxPC </span> for each email recipient (i.e., for each API call). If you do not provide unique values for these fields, API response might slow or fail due to the large number of events generated within a single profile. </p> </p> </td> 
   <td colname="col4"> <p>1 &lt; Length &lt; 128 </p> <p>Cannot contain more than a single “.” (dot). </p> <p>The only dot allowed is for profile location suffix. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Optional parameters**:

<table id="table_EDAF09359DF34308BFB4AA293DC1EB1F"> 
 <thead> 
  <tr> 
   <th class="entry"> Parameter </th> 
   <th colname="col02" class="entry"> Value </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Validation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxPC </span> </p> <p>(Optional) </p> </td> 
   <td colname="col02"> <p><i>mboxPCId</i> </p> </td> 
   <td colname="col2"> <p>Target visitor ID. Use this value when if you want to track a user full-circle back to your site across multiple visits, or when using a user profile parameter. </p> <p>This value needs to be the actual Adobe Target PCID for the user, which would be exported from the website to your CRM. The email provider would retrieve this ID from your CRM or Data warehouse, and use it for the value of this parameter. </p> <p>The <span class="codeph"> mboxPC </span> value is also useful for tracking visitor site behavior across multiple visits for metrics tracking when a recommendation is part of an A/B activity. </p> <p> <p>Note:  Be sure to provide a unique value of <span class="codeph"> mboxSession </span> and <span class="codeph"> mboxPC </span> for each email recipient (i.e., for each API call). If you do not provide unique values for these fields, API response might slow or fail due to the large number of events generated within a single profile. </p> </p> </td> 
   <td colname="col4"> <p>1 &lt; Length &lt; 128 </p> <p>Cannot contain more than a single "." (dot). </p> <p>The only dot allowed is for profile location suffix. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxNoRedirect </span> </p> <p>(Optional) </p> </td> 
   <td colname="col02"> <p>1 </p> </td> 
   <td colname="col2"> <p>By default, the caller is redirected when no deliverable content is found. Use to disable the default behavior. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td> <p> <span class="codeph"> mbox3rdPartyId </span> </p> </td> 
   <td colname="col02"> <p><i>xxx</i> </p> </td> 
   <td colname="col2"> <p>Use this if you have your own custom visitor ID to use for profile targeting. </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

**Potential Target server responses**:

<table id="table_D197310D72E246769330C665F821E284"> 
 <thead> 
  <tr> 
   <th class="entry"> Response </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <span class="codeph"> //ERROR: </span> </td> 
   <td> <p>Generated by load balancer when it can't return content </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> success </span> </td> 
   <td> <p>The <span class="codeph"> mboxNoRedirect </span> parameter is set to 'true' and the server does not return any recommendations (i.e., there is no match for the mbox or the server cache is not initialized). </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> bad request </span> </td> 
   <td> <p>The <span class="codeph"> mbox </span> parameter is missing. </p> <p> 
     <ul id="ul_AD90ED7DB02548E99673D383549A84A7"> 
      <li id="li_E6DC1403122C440F9DB19CC2BA3CC1C8"> <p> Either <span class="codeph"> mboxDefault </span> or the <span class="codeph"> mboxNoRedirect </span> parameter is not specified. </p> </li> 
      <li id="li_FA1B81972DBB42658E6EF079C71A48F5"> <p> <span class="codeph"> mboxTrace </span> request parameter is specified but <span class="codeph"> mboxNoRedirect </span> is not. </p> </li> 
      <li id="li_8D9E8CBE46D14F56A848857A3D79F995"> <p> <span class="codeph"> mboxTarget </span> parameter is not specified when mbox names ends with <span class="codeph"> -clicked </span> suffix. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> Cannot redirect to default content, please specify mboxDefault parameter </span> </td> 
   <td> <p> <span class="codeph"> mboxDefault </span> not specified when no match for the request exists and <span class="codeph"> mboxNoRedirect </span> parameter is not specified. </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> Invalid mbox name:= MBOX_NAME </span> </td> 
   <td> <p>Indicates <span class="codeph"> mbox </span> parameter contains invalid characters. </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> Mbox name [MBOX_NAME] is too long </span> </td> 
   <td> <p>Indicates <span class="codeph"> mbox </span> parameter is longer than 250 characters. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Option 3: Use the Download-Only Template {#section_518C279AF0094BE780F4EA40A832A164}

Set up a recommendation as usual, but choose **download only** in the presentation section instead of a template and mbox combination. Then in the ESP, tell the ESP what recommendation ID you created. The ESP accesses the recommendation data via API. This data shows which items should be recommended for a particular category or key item, such as items in an abandoned cart. The ESP stores this data, connects it with their own look and feel, displays information about each item, and delivers that in the emails.

With this option, the recommendations server cannot directly track the performance of a recommendation or split traffic across multiple algorithm/template combinations. Also, the recommendations are not tied to a visitor profile.

For more information about the download API, see [Legacy APIs > Download](https://marketing.adobe.com/resources/help/en_US/rec/r_Using_the_Recommendations_Download_API.html).
