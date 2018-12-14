---
description: Information to help you set several settings on the mbox.js Settings
  page.
keywords: advanced mbox.js settings;client;server domain;xdomain;compression level;client
  session id support;secureOnly;client pc id support;pass page;referring url;traffic
  level;traffic duration;mboxParameters() function body;mboxSupported() function body;mboxCookieDomain()
  function body;Extra JavaScript;SiteCatalyst plug-in;Get mbox.js as self-extracting
  JavaScript;flicker;body hiding;hide body
seo-description: Information to help you set several settings on the mbox.js Settings
  page.
seo-title: Configure mbox.js
solution: Target
title: Configure mbox.js
uuid: e79c7af7-f8bd-4e2b-8e67-b04eddf0c65d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Configure mbox.js{#configure-mbox-js}

Information to help you set several settings on the mbox.js Settings page.

The default settings of the [!DNL mbox.js] function library serve the needs of most [!DNL Target] customers.

If needed, consult your account representative to change the [!DNL mbox.js] settings.

<table id="table_279063834235446A858D3CCFDA1F68A6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Client </p> </td> 
   <td colname="col2"> <p>The client code for your account. </p> <p>When viewing <span class="uicontrol"> Setup </span> > <span class="uicontrol"> Implementation </span> > <span class="uicontrol"> Edit Mbox.js Settings </span>, the Client at the top is the client code for your account. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Timeout </p> </td> 
   <td colname="col2"> <p>The Target request timeout. </p> <p>When viewing Setup > Implementation > Edit Mbox.js Settings, the Timeout after Compression Level is your Target request timeout. By default this value is set to 15 seconds, but we recommend setting it to a value between 2 seconds and 5 seconds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XDomain </p> </td> 
   <td colname="col2"> <p>Determines whether the browser sets cookies in your own domain (1st party cookies), Target's domain, or both. </p> <p>Changing this setting affects both mbox.js and at.js. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compression Level </p> </td> 
   <td colname="col2"> <p>Determines how compressed the <span class="filepath"> mbox.js </span> library file is. Increasing the compression level decreases the page-load time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mboxParameters() function body </p> </td> 
   <td colname="col2"> <p>Returns extra parameters to pass to each mbox call. </p> <p>For example: </p> <p> <span class="codeph"> return "test=123"; </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mboxSupported() function body </p> </td> 
   <td colname="col2"> <p>Returns false to exclude specific users. </p> <p>For example: </p> <p> <span class="codeph"> return !navigator.userAgent.indexOf('Safari') != -1; </span> </p> <p>The following browsers can be accepted or excluded: </p> <p> 
     <ul id="ul_571938793D6340558C9EA1996B503847"> 
      <li id="li_CCE7658BDB3F46E69B90534380D45EAF"> IE 5.0 or greater (Windows) </li> 
      <li id="li_FBA2D7ABCDF84166A79EB74D3498E881"> Netscape 5.0 or greater (Mac, Windows, Linux) </li> 
      <li id="li_E3594D180230474DAC872926DB1253CE"> Safari 1.2.4 or greater (Mac) </li> 
      <li id="li_70D8B310F60B4271997F07BDC8316032"> Mozilla Firefox 1.0 or greater (Mac, Windows, Linux) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mboxCookieDomain() function body </p> </td> 
   <td colname="col2"> <p>Returns a string describing the domain to set first-party cookies. </p> <p>For example: </p> <p> <span class="codeph"> return "YOUR-DOMAIN"; </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Extra JavaScript </p> </td> 
   <td colname="col2"> <p>Includes any additional JavaScript you want to execute on each page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SiteCatalyst plug-in </p> </td> 
   <td colname="col2"> <p>Enables the <span class="keyword"> Analytics Target </span> plug-in. </p> <p>If enabled, the <span class="keyword"> Analytics </span> plug-in generates plug-in code in <span class="filepath"> mbox.js </span>. This sends <span class="keyword"> Analytics </span> tag information to <span class="keyword"> Target </span> servers as an mbox request on every page tagged with <span class="keyword"> Analytics </span>. </p> <p>Note that the <span class="keyword"> Analytics </span> plug-in must still be referenced on the page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>secureOnly </p> </td> 
   <td colname="col2"> <p>Indicates whether mbox.js should use HTTPS only or be allowed to switch between HTTP and HTTPS based on the page protocol. This is an advanced setting that defaults to False. </p> </td> 
  </tr> 
 </tbody> 
</table>

