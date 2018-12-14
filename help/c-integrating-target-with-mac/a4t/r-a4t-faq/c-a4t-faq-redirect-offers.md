---
description: This topic contains answers to questions that are frequently asked about
  using redirect offers when using Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;redirect;redirect
  offer;adobe-mc-sdid;adobe_mc_ref
seo-description: This topic contains answers to questions that are frequently asked
  about using redirect offers when using Analytics as the reporting source for Target
  (A4T).
seo-title: Redirect offers - A4T FAQ
solution: Target
title: Redirect offers - A4T FAQ
topic: Standard
uuid: a45cef89-3003-4177-bf84-3d5a486b950d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Redirect offers - A4T FAQ{#redirect-offers-a-t-faq}

This topic contains answers to questions that are frequently asked about using redirect offers when using Analytics as the reporting source for Target (A4T).

## Does Analytics for Target (A4T) support redirect offers? {#section_46B8B03ED4D542C6AD875F5F61176298}

Yes, provided that your implementation uses [!DNL at.js]. However, your implementation must meet the minimum requirements listed below in order to use [redirect offers](../../../c-experiences/c-manage-content/t-offer-redirect.md#task_33C80CD722564303B687948261484F94) in activities that use Analytics as the reporting source.

## What are the minimum requirements needed to use redirect offers with A4T? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Your implementation must meet the following minimum requirements:

* Experience Cloud Visitor ID Service: [!DNL visitorAPI.js] version 2.3.0 or later.
* Adobe Analytics: [!DNL appMeasurement.js] version 2.1.
* Adobe Target: [!DNL at.js] version 0.9.6 or later (except version 1.1.0 if using redirect offers with A4T).

   The [!DNL mbox.js] library does not support redirect offers with A4T. Your implementation must use [!DNL at.js].

The three libraries must be included on both the page with the redirect offer and the page to which the visitor is redirected.

## Why are page views on the original page and on the redirect page sometimes counted? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

There is a possibility that a race condition can occur that might cause the Analytics call to fire before the redirect executes on the first page. This can cause page views on the original page and on the redirect page to all be counted. This situation results in an extra page view on the first page, when the visitor never really "saw" this first page.

Using the form-based composer to build a redirect activity is recommended to increase the speed of the page redirect. This is because of where the code gets executed on the page. Also, creating a redirect offer for every experience, even the default experience, where the redirect would return the original page is recommended. This ensures that if mis-counting occurs, it happens across all experiences so reporting and analysis is still valid for the test.

For more information about this issue, see the "Redirect offers" column in the [Known Issues](../../../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541) table.

## Can I use redirect offers with A4T if I'm using the mbox.js JavaScript library? {#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

The [!DNL mbox.js] library does not support redirect offers with A4T. Your implementation must use [!DNL at.js].

## Are both the Visual Experience Composer (VEC) and Form-Based Experience Composer supported? {#section_FDA26FE7909B48539DA770559E687677}

Yes, both composers are supported as long as you use the built-in redirect offers.

If you use your own custom code for the redirect, you must ensure that you populate the two new parameters associated with redirect URLs ( `adobe_mc_sdid` and `adobe_mc_ref`, explained below).

## What are the new query string parameters added to the redirect URLs? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

The following query string parameters are associated with redirect offers:

<table id="table_59CFDE3E9B62468588C75B3BCC2020F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> adobe_mc_sdid</span> </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> adobe_mc_sdid</span> parameter passes the Supplemental Data Id (SDID) and Experience Cloud Org Id from the default page to the new page in order for A4T to "stitch" together the <span class="keyword"> Target</span> request on the default page with the <span class="keyword"> Analytic</span> request on the new page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> adobe_mc_ref</span> </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> adobe_mc_ref</span> parameter passes the referring URL of the default page to the new page. When used with <span class="filepath"> AppMeasurement.js</span> version 2.1 (or later), <span class="keyword"> Analytics</span> will use this parameter value as the referring URL on the new page. </p> </td> 
  </tr> 
 </tbody> 
</table>

These parameters are automatically added to the redirect URLs when using the built-in redirect offers in the VEC and Form-Based Experience Composer when the Visitor Id service is implemented on the page. If you are using your own custom redirect code in the VEC or Form-Based Composer, you must be sure to pass these parameters with your custom code.

## My web servers are stripping these parameters from my URLs, what should I do? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

You will need to work with your IT team to have these parameters ( `adobe_mc_sdid` and `adobe_mc_ref`) whitelisted.

## What if I am not using A4T with my redirect activity and don't want to have these extra parameters added to my URLs? {#section_9E608D75FF9349FE96C65FEDD7539F45}

If you are not using A4T with your redirect activity, you have the Visitor Id service implemented, and you don't want these parameters to be automatically added to your URLs, you must use a custom-coded redirect.

However, as best practice, you might want to keep the `adobe_mc_ref` parameter in the URL in order to report the referrer information to [!DNL Analytics] correctly.

## Why are the adobe_mc_ref and adobe_mc_sdid parameters double URL encoded in my implementation? {#section_5EFE5F012B944C40865731EA18E7E79E}

If you use A4T and redirect offers, Target appends the `adobe_mc_ref` and `adobe_mc_sdid` parameters to the URL. These values are already URL encoded. Most of the time everything works as expected, however, some customers might have load balancers or WEB servers that try to encode the query string parameters one more time.

Because of this double encoding when the Visitor API tries to decode the `adobe_mc_sdid` value, it can't extract the SDID value and generates a new SDID. This leads to incorrect SDID values being sent to Target and Analytics and you'll see uneven split for redirects in Analytics reports.

We recommend that you talk to their IT team to ensure that `adobe_mc_ref` and `adobe_mc_sdid` are white-listed so that these values are not transformed in any way.

## Why does the referring URL need to be passed to the new page? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Suppose a visitor clicks a link on [!DNL `www.google.com`] to your homepage ( [!DNL `www.mysite.com/index.html]`) on which a redirect activity is live and is then redirected to a new page ( [!DNL `www.mysite.com/index2.html`]).

Previously, the [!DNL Analytics] request on the new page would report a referring URL of [!DNL `www.mysite.com/index.html`] instead of [!DNL `www.google.com`]. This caused inaccurate reporting in [!DNL Analytics] associated with the referring URLs (Marketing Channel reports, for example). The reports had lost the fact that you came to the site from [!DNL `www.google.com`].

With [!DNL at.js] version 0.9.6 (or later) and [!DNL AppMeasurement.js] 2.1 (or later), the [!DNL Analytics] request on the new page will report a referring URL of [!DNL `www.google.com`].

## Can I use custom/HTML redirect offers? {#section_E49F9A83A286488C8F1098A040203D7E}

No, you must use a built-in redirect offer for activities that use [!DNL Analytics] as the reporting source (A4T). From the [!DNL Target] perspective, HTML offers are opaque: [!DNL Target] can't know that a particular piece of HTML contains JavaScript that instantiates a redirect.
