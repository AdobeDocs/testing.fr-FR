---
description: Use a Redirector similarly to how you use an mbox in your tests.
keywords: Implementation;mbox.js non javascript;redirector;costs per click;revenue
  per click
seo-description: Use a Redirector similarly to how you use an mbox in your tests.
seo-title: Work with redirectors
solution: Target
subtopic: Getting Started
title: Work with redirectors
topic: Standard
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Work with redirectors{#work-with-redirectors}

Use a Redirector similarly to how you use an mbox in your tests.

## Work with redirectors {#concept_D5EF059F4DC94C67A8B684C9F9910EE4}

Use a Redirector similarly to how you use an mbox in your tests.

Redirectors are created with a special Redirector URL that loads a Redirector mbox (Redirector) into your account. Use this Redirector similarly to how you use an mbox in your tests. Submit the Redirector URL to your Ad Network as the ad's destination link.

Use the Redirector to do the following:

* Track clicks from your display ads to your site
* Create a single centralized report to track clicks to display ads on multiple ad networks
* Vary display ad destinations

   For example the same banner lands on your home page, category page and product page.

* Find which landing page leads to the most conversions

For help deciding the right setup see [Non-JavaScript-Based Implementations](../../c-implementing-target/c-non-javascript-based-implementation/c-non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Create a Redirector {#task_76608B0F73FC45C4A9F125B894DCF821}

Before you can use a redirector, you must create it.

<!-- 

ov2/t_creating-a-redirector.xml

 -->

1. Determine the ad's destination variations, including the default destination.
1. Create the Redirector URL.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

<table id="table_DD29523C6FB54061B40AD2B07AE8EDAB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Where </th> 
   <th colname="col2" class="entry"> Is </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>yourclientcode </p> </td> 
   <td colname="col2"> <p>Your company's client code. </p> <p><b>at.js: </b>Your client code is available at the top of the Setup > Implementation > Edit at.js Settings page of the Target interface. </p> <p><b>mbox.js: </b>Your client code is available at the top of the Setup > Implementation > Edit Mbox.js Settings page. </p> <p>Your company's client code is all lower case and has no special characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>redirectorlink_456 </p> </td> 
   <td colname="col2"> <p>The name of the Redirector mbox that appears in your account to use in campaigns and tests. </p> <p class="- topic/p ">Redirectors function differently from other mboxes, but appear just as any other mbox in your account. Name the redirector so it is easily distinguished them from the standard type mboxes in your account. </p> <p class="- topic/p ">As best practice, begin the mbox name with<span class="+ topic/ph pr-d/codeph codeph"> 'redirectorlink'</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm </p> </td> 
   <td colname="col2"> <p>The default destination. </p> <p class="- topic/p ">This must be URL encoded and must be an absolute reference. </p> <p class="- topic/p ">Tip:<span class="+ topic/ph sw-d/filepath filepath"> https://www.w3schools.com/tags/ref_urlencode.asp</span> quickly encodes your URLs. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Validate the Redirector.
   1. Insert the Redirector URL into a browser and refresh.
   1. Log in to your account, refresh your mbox list and verify the new Redirector is listed as an mbox.
1. If you will test different destinations for one ad, create [Redirect Offers](../../c-experiences/c-visual-experience-composer/t-redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) for each version.
1. Create the campaign.

   See [Non-JavaScript-Based Implementations](../../c-implementing-target/c-non-javascript-based-implementation/c-non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) for the right setup to meet your goals.
1. Complete QA on the campaign.

   Create a dummy page with an `<a href>` containing the Redirector URL. Example:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Verify that all experiences, default content, and reports act as expected on all browser types, for all of your environments.

   >[!NOTE] {class="- topic/note "}
>
>
>
>
>* Redirectors are not supported by Offer Preview or Browse for mbox. Preview experiences directly in a browser.
>* `mboxDebug` does not work with Redirectors .


1. Submit the full Redirector URL to your Display Ad Network as the ad destination.

## Use a Redirector to Pass Costs per Click and Revenue Per Click {#concept_3078EF48E9C44B34992D62AAB9628853}

Information about using a redirector to pas costs per click and revenue per click.

<!-- 

ov2/c_using-a-redirector-to-pass-costs-per-click-and-revenue-per-click.xml

 -->

## Passing Costs per Click {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Use a redirector to pass the costs per click.

>[!NOTE]
>
>Best practice is to determine the cost value using the **Score per visit** engagement metric, as described in [Engagement](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Add `&mboxPageValue=-value` to the URL. Note the negative value.

Example: For a .10 cents cost per click:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

## Passing Revenue per Click {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Use a redirector to pass the revenue per click.

>[!NOTE]
>
>Best practice is to determine the revenue value using the **Score per visit** engagement metric, as described in [Engagement](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Add `&mboxPageValue=value` to the URL.

Example: For a .10 cents revenue per click.

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```

