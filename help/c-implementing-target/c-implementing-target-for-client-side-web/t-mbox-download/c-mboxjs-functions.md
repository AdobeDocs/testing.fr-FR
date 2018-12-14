---
description: List of mbox.js functions to use when implementing with mbox.js.
keywords: mbox functions
seo-description: List of mbox.js functions to use when implementing with mbox.js.
seo-title: mbox.js functions
solution: Target
title: mbox.js functions
uuid: f503bc44-a664-4d09-82dc-80a1198ad9d0
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# mbox.js functions{#mbox-js-functions}

List of mbox.js functions to use when implementing with mbox.js.

>[!NOTE]
>
>If you are using [!DNL at.js], these methods do not apply.

<table id="table_0E99AD9702944F749BE37DCBAA34DD76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Notes </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.getName() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.getURL() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.getDiv() </span> </p> </td> 
   <td colname="col2"> Returns the <span class="codeph"> div </span> associated with the mbox (containing default content or an offer) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.getParameters() </span> </p> </td> 
   <td colname="col2"> An array of parameters with two fields, name and value </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.setOnError() </span> </p> </td> 
   <td colname="col2"> Example: <p> <span class="codeph"> mbox.setOnError(function() { alert(this.getName() +" had error"}); </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mbox.setMessage(message) </span> </p> </td> 
   <td colname="col2"> You can see message in debug window . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.activate() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.cancelTimeout() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.finalize() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getDefaultDiv() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getDiv() </span> </p> </td> 
   <td colname="col2"> Returns the <span class="codeph"> div </span> associated with the mbox (containing default content or an offer) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getEventTimes() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getFetcher() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getId() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getImportName() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getName() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getOffer() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getParameters() </span> </p> </td> 
   <td colname="col2"> An array of parameters with two fields, name and value . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getURL() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.getURLBuilder() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.hide() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.isActivated() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.load() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.loaded() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.setEventTime() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.setFetcher() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.setMessage() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.setMessage(message) </span> </p> </td> 
   <td colname="col2"> View message in debug window . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.setOffer() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.setOnError() </span> </p> </td> 
   <td colname="col2"> Example: <p> <span class="codeph"> mboxCurrent.setOnError(function(){ alert(this.getName() +" had error"}); </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.setOnLoad() </span> </p> </td> 
   <td colname="col2"> Example: <p> <span class="codeph"> mboxCurrent.setOnLoad(function(){alert(this.getName()+" loaded")}); </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.show() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxCurrent.showContent() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.addOnLoad(action) </span> </p> </td> 
   <td colname="col2"> Action is called when page loads. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getMboxes().each() </span> </p> </td> 
   <td colname="col2"> Example: <p> <span class="codeph"> mboxFactoryDefault.getMboxes().each(function() { alert(mbox.getName()) }; </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getMboxes().length() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getPageId() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getPCId().getId() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getSessionId().getId() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactories.get('default').getSessionId()​.forceId("1276011116668"); </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactories.get('default').getPCId()​.forceId("1276011116668"); </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.create() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.disable() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.enable() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.get() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getCookieManager() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getDisableReason() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getEllapsedTime() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getEllapsedTimeUntil() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getMboxes() </span> </p> </td> 
   <td colname="col2"> Returns an <span class="codeph"> mboxList </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getSignaler() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getURLBuilder() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.isAdmin() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.isDomLoaded() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.isEnabled() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.isSupported() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.limitTraffic() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.update() </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getCookieManager()​.getCookie("name")//!= null) { </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxFactoryDefault.getCookieManager()​.setCookie(_name,_value, _duration); </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

