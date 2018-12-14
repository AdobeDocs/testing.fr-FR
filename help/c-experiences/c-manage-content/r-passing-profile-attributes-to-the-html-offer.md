---
description: You can display profile values and campaign information directly in an
  HTML or Flash Offer.
keywords: dynamic data;assets;data;offers
seo-description: You can display profile values and campaign information directly
  in an HTML or Flash Offer.
seo-title: Pass dynamic data into offers
solution: Target
title: Pass dynamic data into offers
topic: Premium
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Pass dynamic data into offers{#pass-dynamic-data-into-offers}

You can display profile values and campaign information directly in an HTML or Flash Offer.

**Business Case**

A visitor arrives on your landing page with `keyword=world` `cup`. You display the term *World cup* in the offer.

**Technical Advantages**

Because it is stored in the user profile, you can repeat this message on his next visits. Just one offer or campaign can manage these custom messages for all your visitors. As the visitor's intent changes your website content automatically reflects those changes.

**Example**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* HTML Offer code: `Get your ${profile.keyword} information here!`
* User sees: Get your World Cup information here!

The following values can be "token replaced":

<table id="table_392FA513A3494227A00DCB2B464FFE95"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Values </th> 
   <th colname="col2" class="entry"> Examples </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>In-mbox profile parameters </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ${profile.age} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Script profile parameters </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ${user.lifetimeSpend} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mbox parameters </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ${mbox.favoriteColor} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign information </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ${campaign.name}, ${campaign.recipe.name}, ${campaign.id}, </span> </p> <p> <span class="codeph"> ${campaign.recipe.id} </span> </p> <p> <span class="codeph"> ${campaign.recipe.trafficType} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unique visitor id </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ${user. pcId} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unique session id </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ${user.sessionId} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitor's first session (true or false) </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> ${user.isFirstSession} </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Tip:** This information can be useful for debugging.

**Implementation**

For profile parameters passed into an mbox, use the syntax: `${profile.parameter}` For profile parameters created in a script, use the syntax:

`${user.parameter}`

These variables are replaced with the value on the server side, so no quotes or other JavaScript is required for the proper display.

Default values can also be specified for values you wish to expose to offers. The syntax is like this:

`${user.testAttribute default="All Items!"}`

When `testAttribute` doesn’t exist or is blank, "All Items!" will be written out. If an empty attribute value is valid, and you want to write it out instead of showing the default, you can use:

`${user.testAttribute default="All Items!" show_blank="true"}`

You can also escape and unescape values to be displayed. If your value has an apostrophe for example, you would want to escape the value so it does not break the JavaScript on the page. (Offers are written in JavaScript, so a single apostrophe can be confused for a quote.) For example:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`

>[!NOTE]
>
>Please work with your representative to use this feature.

