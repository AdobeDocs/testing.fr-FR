---
description: Information about how to safely deploy at.js to a non-production environment.
seo-description: Information about how to safely deploy at.js to a non-production
  environment.
seo-title: Deploy at.js to a Non-Production Environment
title: Deploy at.js to a Non-Production Environment
uuid: 7f1adc43-35b4-442c-bb06-feab60604a87
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Deploy at.js to a Non-Production Environment{#deploy-at-js-to-a-non-production-environment}

Information about how to safely deploy at.js to a non-production environment.

<table id="table_D7E62869F2B040DD8E7DDF1A1F1BCC37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Technique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Deploy to DTM Staging </td> 
   <td colname="col2"> <p>If you use DTM, you can easily save <span class="filepath"> at.js</span> in your Adobe Target Tool configuration. </p> <p>After you have saved the library, use the DTM Switch tool to test it against your production code. This will also make it easy for your Adobe consultants to support you. </p> <p>For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/dtm/target/t_implementing-target-manually-js-hosted-dtm.html" format="html" scope="external"> Option 3: Implement Target Manually with the Target JavaScript Library Hosted by DTM</a> in the <i>Best Practices for Implementing Adobe Target using Dynamic Tag Management </i>guide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use "Requestly" Chrome extension to map to another file </td> 
   <td colname="col2"> <p> <a href="https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en" scope="external" format="http"> Requestly</a> is a free Chrome extension that lets you redirect requests to an alternate URL. </p> <p>You deploy <span class="filepath"> at.js</span> to a URL, and then use Requestly to map your current <span class="filepath"> mbox.js</span> file URL to the new <span class="filepath"> at.js</span> URL. Then, any time your website tries to load <span class="filepath"> mbox.js</span>, it loads <span class="filepath"> at.js</span> instead. This approach also make it easier for Adobe to provide support. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Deploy to a development, staging, or QA environment </td> 
   <td colname="col2"> <p>If you host <span class="filepath"> mbox.js</span> in your codebase and are able to easily make updates to your code environments, deploy <span class="filepath"> at.js</span> to one of your lower environments. </p> <p>For better support from Adobe, deploy the file to an environment that Adobe can access. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use Charles or Fiddler to map to a local file </td> 
   <td colname="col2"> <p> <a href="https://www.charlesproxy.com/" scope="external" format="http"> Charles Web Debugging Proxy</a> is an application available for Mac and Windows whose Map Local feature can be used to map the loading of your production <span class="filepath"> mbox.js</span> file to a local copy of <span class="filepath"> at.js</span>. A free trial version is available for download for Mac and Windows. </p> <p><a href="https://www.telerik.com/fiddler" scope="external" format="http"> Fiddler</a> is a similar tool available as a free download for Windows. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Deploy to another tag manager environment </td> 
   <td colname="col2"> <p>If you are using another tag manager, it probably has a way to deploy <span class="filepath"> at.js</span> safely without impacting your production traffic. </p> </td> 
  </tr> 
 </tbody> 
</table>

