---
description: Use an AdBox to deliver images in an off-site implementation.
keywords: Implementation;mbox.js non javascript;mbox;adbox
seo-description: Use an AdBox to deliver images in an off-site implementation.
seo-title: Create an Adbox for an image
solution: Target
subtopic: Getting Started
title: Create an Adbox for an image
topic: Standard
uuid: 6b1763f7-08de-4bde-9e20-e79b92b02f20
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Create an Adbox for an image{#create-an-adbox-for-an-image}

Use an AdBox to deliver images in an off-site implementation.

An AdBox is like an mbox, but it is controlled by a URL rather than JavaScript. AdBoxes are created with a special AdBox URL that loads an "ad" mbox (or AdBox) into your Adobe account. Use this AdBox in place of the mbox in your activities. Use the AdBox URL instead of a direct image reference in email or other non-JavaScript implementations.

For help selecting the right setup see [Non-JavaScript-Based Implementations](../../c-implementing-target/c-non-javascript-based-implementation/c-non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. Create the AdBox URL:

   `https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/image?mbox=emailHeroImage123_320x200&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif`

<table id="table_DD29523C6FB54061B40AD2B07AE8EDAB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Where </th> 
   <th colname="col2" class="entry"> Is </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>myClientCode </p> </td> 
   <td colname="col2"> <p>Your company's client code. </p> <p><b>at.js:</b> Your client code is available at the top of the Setup > Implementation > Edit at.js Settings page of the Target interface. </p> <p><b>mbox.js:</b> Your client code is available at the top of the Setup > Implementation > Edit Mbox.js Settings page. </p> <p>Your company's client code is all lower case and has no special characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>image </p> </td> 
   <td colname="col2"> <p>The call type. In this case it is an image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>emailHeroImage123_320x200 </p> </td> 
   <td colname="col2"> <p>The name of the AdBox. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif </p> </td> 
   <td colname="col2"> <p>The mbox's default content. This must be an image. </p> <p class="- topic/p ">This must be URL encoded and must be an absolute reference. </p> <p class="- topic/p ">Tip:<span class="+ topic/ph sw-d/filepath filepath"> https://www.w3schools.com/tags/ref_urlencode.asp</span> quickly encodes your URLs. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Create [Redirect Offers](../../c-experiences/c-manage-content/t-offer-redirect.md#task_33C80CD722564303B687948261484F94) for each alternative image.

   >[!NOTE] {class="- topic/note "}
>
>AdBoxes must be loaded with a Redirect Offer or the default content offer. Other offers types will not work. Because the AdBox is a URL, it can only display the URLs it receives, so only the Redirect Offer works.

1. Create the activity.

   See [Non-JavaScript-Based Implementations](../../c-implementing-target/c-non-javascript-based-implementation/c-non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) for the right set up to meet your goals.
1. Complete QA on the activity.

   As best practice, create a dummy page and verify that all experiences, default content, and reports act as expected on all browser types, for all of your environments. 1. Launch the activity.
