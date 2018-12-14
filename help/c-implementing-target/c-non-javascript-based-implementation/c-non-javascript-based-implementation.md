---
description: Information about implementing Target in non-JavaScript scenarios, such
  as using an AdBox or Redirector.
keywords: Implementation;mbox.js non javascript;adbox;redirector;mbox
seo-description: Information about implementing Target in non-JavaScript scenarios,
  such as using an AdBox or Redirector.
seo-title: Email  implement Target
solution: Target
subtopic: Getting Started
title: Email  implement Target
topic: Standard
uuid: 07abc419-0253-47c6-80b8-0bd0734d2c9d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Email: implement Target{#email-implement-target}

Information about implementing Target in non-JavaScript scenarios, such as using an AdBox or Redirector.

You can track visits to ads and other offsite content. You can also identify the same user on and off your site and deliver a consistent experience throughout their web experience. Using a single URL, the AdBox allows testing without JavaScript or [!DNL at.js] or [!DNL mbox.js].

An AdBox is useful for sites that do not have [!DNL at.js] or [!DNL mbox.js], such as affiliates. If your activity needs dynamic creative (for example, you need to show a product in the ad that was abandoned in the cart), you cannot use an AdBox.

AdBox ads and Redirector can be used with any kind of activity. The following table compares Adbox and Redirector, and when to use each:

<table id="table_0FCE44A165574C609FF7F94A7DDF8926"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Purpose </th> 
   <th colname="col3" class="entry"> When To Use </th> 
   <th colname="col4" class="entry"> URL Structure </th> 
   <th colname="col5" class="entry"> Offer Type </th> 
   <th colname="col6" class="entry"> Offer Content </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AdBox </p> </td> 
   <td colname="col2"> <p>Returns different images to the ad </p> </td> 
   <td colname="col3"> <p>To change the content of an ad </p> </td> 
   <td colname="col4"> <p> <span class="codeph"> clientcode​.tt.​omtrdc​.net/​m2​/​clientcode/ubox/​image?</span> </p> </td> 
   <td colname="col5"> <p>redirect offer </p> </td> 
   <td colname="col6"> <p>URL for an image </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Redirector </p> </td> 
   <td colname="col2"> <p>Redirects a visitor to a different web page </p> </td> 
   <td colname="col3"> <p>To change the landing page of an ad </p> </td> 
   <td colname="col4"> <p> <span class="codeph">  clientcode​.tt.omtrdc.net/​m2/clientcode​/ubox/page? </span> </p> </td> 
   <td colname="col5"> <p>redirect offer </p> </td> 
   <td colname="col6"> <p>URL for a page </p> </td> 
  </tr> 
 </tbody> 
</table>

## Constraints {#section_38F559DCF1324271926608BCD4AB1227}

* There is no client-side timeout as with standard mboxes. If Target is completely down, visitors to the ad will not see content, not even default.
* 3rd-party cookies are used to track the visits. If the PCIds are different, by default the visitor's 3rd party is merged with any existing 1st-party profiles.
* To use 1st-party cookies on the AdBox itself, you will need to pass the mBox session in the URL. Talk to your account representative to do this.
* To use 1st-party cookies to track ad clicks, pass the mbox session in the URL. Talk to your account representative to do this.
* To use more than one AdBox on the same page, you must pass the Mbox session in the URL. Talk to your account representative to do this. You might have one AdBox and one Redirector link on the same page (because the Redirector is actually on a second page).

