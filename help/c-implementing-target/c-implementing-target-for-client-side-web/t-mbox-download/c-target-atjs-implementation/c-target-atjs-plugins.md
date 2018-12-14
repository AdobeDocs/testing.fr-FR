---
description: Information about supported and not-supported at.js plug-ins.
keywords: at.js plugins;supported plugins;unsupported plugins
seo-description: Information about supported and not-supported at.js plug-ins.
seo-title: at.js Plug-ins
solution: Target
title: at.js Plug-ins
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# at.js Plug-ins{#at-js-plug-ins}

Information about supported and not-supported at.js plug-ins.

Many people have built customized plugins and response plug-ins for [!DNL mbox.js]. These custom plug-ins might not be supported by [!DNL at.js] without being updated.

If you are using a plug-in that is not listed here and you would like to know the status, please contact your account representative.

Here is the current status of some of the plug-ins that are used by many customers when used with [!DNL at.js]:

<table id="table_51B92B09370E4A03B28ACE358CC12BCE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Plugin </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mboxTrack </td> 
   <td colname="col2"> <p>Not supported. </p> <p>This is replaced by the <a href="../../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_7E0F19368F9C4BC38F1E5DC5E717E487" format="dita" scope="local"> adobe.target.trackEvent(options)</a> function. Update your plug-ins to apply the new function. </p> <p> See the <a href="../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/c-target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39" format="dita" scope="local"> integrations</a> page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Persistent Profile Backup Plugin </td> 
   <td colname="col2"> <p>Not supported. </p> <p> This plug-in was deprecated when the <span class="keyword"> Target</span> profile lifetime was extended from two weeks to 90 days. Check the expiration date of your mbox cookie to see the profile lifetime setting on your account. </p> <p>Contact ClientCare if you would like to extended the profile lifetime to 90 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ttMeta </td> 
   <td colname="col2"> <p>Supported. </p> <p> This plug-in should continue to work with <span class="filepath"> at.js</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

