---
description: Launch is the next-generation tag management platform from Adobe and
  is the preferred method to implement Adobe Target. Launch gives customers a simple
  way to deploy and manage all of the analytics, marketing, and advertising tags necessary
  to power relevant customer experiences.
keywords: implement;implementing;implementation;adobe launch;launch;race;redirect
seo-description: Launch is the next-generation tag management platform from Adobe
  and is the preferred method to implement Adobe Target. Launch gives customers a
  simple way to deploy and manage all of the analytics, marketing, and advertising
  tags necessary to power relevant customer experiences.
seo-title: Implement Target using Adobe Launch
title: Implement Target using Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Implement Target using Adobe Launch{#implement-target-using-adobe-launch}

Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.

## Implement Target using Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.

The following table lists the various sources where you can get more information about Launch:

<table id="table_A85F2CEBF9C54DE780DB1668755D9DFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Resource </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension" format="https" scope="external"> Adobe Target Extension</a> </p> </td> 
   <td colname="col2"> <p>Information about implementing Target using Launch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-guides.html" format="html" scope="external"> Launch by Adobe Reference Architectures</a> </p> </td> 
   <td colname="col2"> <p>Guides that provide best practices and instructions on how to implement Adobe Analytics, Adobe Target, Adobe Audience Manager, and the Experience Cloud ID Service using Launch in a variety of web architectures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> Adobe Launch Documentation</a> </td> 
   <td colname="col2"> <p>Information about deploying and managing all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Advantages of Implementing at.js Using the Target Launch Extension {#section_48B3F938B6F8491DAF798E0DB54EF304}

The following advantages apply only if you use Adobe Launch to implement at.js. For this reason we strongly suggest that you use Adobe Launch rather than DTM or a manual implementation of at.js.

* **Allows for Asynchronous Deployment of Target: ** For more information, see "Adobe Target Extension with an Asynchronous Deployment" in [Adobe Target Extension](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension).
* **Solves Analytics and Target Race Condition: **Because the Analytics call could be fired before the Target call, the Target call is not stitched to the Analytics call, which can lead to incorrect data. Starting with Launch 0.6.0, the Target Launch extension ensures that the Analytics beacon call will wait until the Target call completes, successfully or not. This should solve the data inconsistency customers might have experienced.
* **Prevents Incorrect Redirect Offer Handling: **When you have both Target and Analytics on the page, and there is a redirect offer being executed by Target, you might run into a situation when the Analytics tracker fires a request when it shouldn’t, because the user is being redirected to a different URL. If you implement Target and Analytics via Launch, you’ll not experience this issue, because using Launch, Target will instruct Analytics to abort the Analytics beacon request.

