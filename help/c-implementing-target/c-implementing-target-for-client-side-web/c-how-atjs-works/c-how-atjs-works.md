---
description: Target system diagram showing the flow of calls and information sent
  or collected for an auto-created global mbox using at.js.
keywords: system diagram;flicker;Target Standard;at.js;implementation
seo-description: Target system diagram showing the flow of calls and information sent
  or collected for an auto-created global mbox using at.js.
seo-title: How at.js works
solution: Target
title: How at.js works
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# How at.js works{#how-at-js-works}

Target system diagram showing the flow of calls and information sent or collected for an auto-created global mbox using at.js.

In the Target implementation illustrated below, the following Experience Cloud solutions are implemented: Analytics, Target, and Audience Management. In addition, the following Experience Cloud core services are implemented: Dynamic Tag Management (Activation), Audiences, and Visitor ID Service.

![](assets/target-flow.png)

<table id="table_BF424454762C45C6ABED85FC49A7809E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Call </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Call </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <img href="assets/step1_red.png" id="image_93C806D5A60A4F03BA258780E99C9EA9" /> </td> 
   <td colname="col2"> <p>Call returns the <span class="keyword"> Experience Cloud ID </span> (MCID) if the user is authenticated; another call syncs the customer ID. </p> </td> 
   <td colname="col3"> <img href="assets/step2_red.png" id="image_6FC6C3541AF34BA5B53843D573D726B7" /> </td> 
   <td colname="col4"> <p>The <span class="filepath"> at.js </span> library loads synchronously and hides the document body. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <img href="assets/step3_red.png" id="image_54CB02239B994478A20AC192EDF90DC4" /> </td> 
   <td colname="col2"> <p>A global mbox request is made including all configured parameters, MCID, SDID, and customer ID (optional). </p> </td> 
   <td colname="col3"> <img href="assets/step4_red.png" id="image_6AF7D59C1127417E9718A027AB304BD3" /> </td> 
   <td colname="col4"> <p>Profile scripts execute and then feed into the Profile Store. The Store requests qualified audiences from the Audience Library (for example, audiences shared from <span class="keyword"> Adobe Analytics </span>, <span class="keyword"> Audience Management </span>, etc.). </p> <p>Customer attributes are sent to the Profile Store in a batch process. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <img href="assets/step5_red.png" id="image_978B5A368D9A4929B9CD98CEAF261136" /> </td> 
   <td colname="col2"> <p>Based on the URL, mbox parameters, and profile data, <span class="keyword"> Target </span> decides which activities and experiences to return to the visitor. </p> </td> 
   <td colname="col3"> <img href="assets/step6_red.png" id="image_8CC1644F6C8A49DFA74678FC484ADCDD" /> </td> 
   <td colname="col4"> <p>Targeted content is sent back to page, optionally including profile values for additional personalization. </p> <p>The experience is revealed as quickly as possible without flicker of default content. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <img href="assets/step7_red.png" id="image_BA305C16960247A0B55D66CD3A664B02" /> </td> 
   <td colname="col2"> <p> <span class="keyword"> Analytics </span> data is sent to Data Collection servers. </p> </td> 
   <td colname="col3"> <img href="assets/step8_red.png" id="image_01FCF7749E2A42EA9C8AF0F46B219846" /> </td> 
   <td colname="col4"> <p> <span class="keyword"> Target </span> data is matched to <span class="keyword"> Analytics </span> data via the SDID and is processed into the <span class="keyword"> Analytics </span> reporting storage. </p> <p> <span class="keyword"> Analytics </span> data can then be viewed in both <span class="keyword"> Analytics </span> and <span class="keyword"> Target </span> via <span class="wintitle"> Analytics for Target </span> (A4T) reports. </p> </td> 
  </tr> 
 </tbody> 
</table>

