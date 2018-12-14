---
description: Several steps are required when implementing Adobe Analytics as the reporting
  source for Target (A4T).
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report
  suite;Analytics Target integration;configure report suite
seo-description: Several steps are required when implementing Adobe Analytics as the
  reporting source for Target (A4T).
seo-title: Analytics for Target implementation
solution: Target
title: Analytics for Target implementation
topic: Premium
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Analytics for Target implementation{#analytics-for-target-implementation}

Several steps are required when implementing Adobe Analytics as the reporting source for Target (A4T).

## Implementation Steps {#section_73961BAD5BB4430A95E073DE5C026277}

The following table describes the steps required to deploy this integration to your site.

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Step </th> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"><img href="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> <p>Request provisioning for Analytics and Target. </p> </td> 
   <td colname="col2"> <p>After you implement <span class="keyword"> Analytics</span> as the reporting source for <span class="keyword"> Target</span>, you must be provisioned for <span class="keyword"> Analytics</span> and <span class="keyword"> Target</span>. Use <a href="https://www.adobe.com/go/audiences" format="http" scope="external"> this form</a> to request to be provisioned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step2_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> <p>Set up user permissions </p>. </td> 
   <td colname="col2"> <p>User account requirements must be met before you can create an <span class="keyword"> Adobe Analytics</span>-based activity in <span class="keyword"> Adobe Target</span>. See <a href="../../c-integrating-target-with-mac/a4t/c-account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083" format="dita" scope="local"> User Permission Requirements</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step3_icon.png" id="image_9933AC9D3A884BD9814A6B697610CAE9" /> </td> 
   <td colname="col1"> <p>Implement the Experience Cloud Visitor ID service. </p> </td> 
   <td colname="col2"> <p>The visitor ID service lets you identify users across <span class="keyword"> Experience Cloud</span> solutions. You must implement or migrate to the required version of the Experience Cloud Visitor ID. For more information, see "Implementation Requirements" in <a href="../../c-integrating-target-with-mac/a4t/c-before-implement.md#concept_046BC89C03044417A30B63CE34C22543" format="dita" scope="local"> Before You Implement</a>. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-target.html" format="html" scope="external"> Implement the Experience Cloud ID Service for Target</a> in the <i>Experience Cloud Visitor ID Service documentation</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step4_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> <p>Update AppMeasurement for JavaScript or s_code. </p> </td> 
   <td colname="col2"> <p>You must implement or migrate to the required version of <span class="codeph"> appMeasurement.js</span>. For more information, see "Implementation Requirements" in <a href="../../c-integrating-target-with-mac/a4t/c-before-implement.md#concept_046BC89C03044417A30B63CE34C22543" format="dita" scope="local"> Before You Implement</a>. </p> <p>For new implementations, see <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=js_implementation" format="https" scope="external"> Analytics JavaScript Implementation</a>. </p> <p>For a migration, see <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=appmeasure_mjs_migrate" format="http" scope="external"> Migrating to AppMeasurement for JavaScript</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step5_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> <p>Download and update <span class="codeph"> at.js</span> or <span class="codeph"> mbox.js</span>. </p> </td> 
   <td colname="col2"> <p>You must implement or migrate to the required version of <span class="codeph"> at.js</span> or <span class="codeph"> mbox.js</span> using your production account. No modifications are required on the code. </p> <p>For more information, see "Implementation Requirements" in <a href="../../c-integrating-target-with-mac/a4t/c-before-implement.md#concept_046BC89C03044417A30B63CE34C22543" format="dita" scope="local"> Before You Implement</a>. </p> </td> 
  </tr> 
  <!-- <row> <entry colname="col01"><image href="graphics/step3_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7"></image> </entry> <entry colname="col1"> <p>Edit <codeph>mbox.js</codeph> </p> </entry> <entry colname="col2"> <p>On the <uicontrol>Mbox Edit</uicontrol> page in Adobe Target, add the following code to the <uicontrol>Extra JavaScript</uicontrol> portion of your <codeph>mbox.js</codeph> file: </p> <codeblock outputclass="syntax javascript">document.write('&lt;script&nbsp;src="'&nbsp;+&nbsp;document.location.protocol&nbsp;+&nbsp;'//cdn.tt.omtrdc.net/cdn/target.js"&gt;&lt;/script&gt;');</codeblock> </entry> </row> --> 
  <tr> 
   <td colname="col01"><img href="assets/step6_icon.png" id="image_C17DA86A4D9A483DB862F5970A1EEEF1" /> </td> 
   <td colname="col1"> <p>Host <span class="codeph"> mbox.js</span> or <span class="codeph"> at.js</span>. </p> </td> 
   <td colname="col2"> <p>If you previously deployed <span class="codeph"> mbox.js</span> or <span class="codeph"> at.js</span>, you can replace your existing file with the updated version. For more information, see "Implementation Requirements" in <a href="../../c-integrating-target-with-mac/a4t/c-before-implement.md#concept_046BC89C03044417A30B63CE34C22543" format="dita" scope="local"> Before You Implement</a>. </p> <p>Otherwise, this file can be hosted along with the Visitor ID service and AppMeasurement for JavaScript files. These files must be hosted on a web server that is accessible to all pages on your site. You need the path to these files in the next step. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step7_icon.png" id="image_CA8C5C4F0B7C40CEBFD7725663EE7BFD" /> </td> 
   <td colname="col1"> <p>Reference <span class="codeph"> at.js</span> or <span class="codeph"> mbox.js</span> on all site pages. </p> </td> 
   <td colname="col2"> <p> Include <span class="codeph"> at.js</span> or <span class="codeph"> mbox.js</span> below <span class="codeph"> VisitorAPI.js</span> by adding the following line of code in the <span class="codeph"> &lt;head></span> tag on each page: </p> <p>For<span class="codeph"> at.js</span>: </p> 
    <code class="syntax html">
     &lt;script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js">&lt;/script>
    </code> <p>For <span class="codeph"> mbox.js</span>: </p> 
    <code class="syntax html">
     &lt;script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js">&lt;/script>
    </code> <p>It is essential that <span class="codeph"> VisitorAPI.js</span> is loaded before <span class="codeph"> at.js</span> or <span class="codeph"> mbox.js</span>, so if you are updating an existing <span class="codeph"> at.js</span> or <span class="codeph"> mbox.js</span> file, make sure that you verify the load order. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step8_icon.png" id="image_D44ABBFE1308454B955F733D2E6C88EA" /> </td> 
   <td colname="col1"> <p>Validate the implementation. </p> </td> 
   <td colname="col2"> <p>Load your pages after you have updated the JavaScript libraries to confirm that the <span class="codeph"> mboxMCSDID</span> parameter values in Target calls match the <span class="codeph"> sdid</span> parameter value in the Analytics page-view call. </p> <p>This is especially important to confirm in Single Page Applications (SPAs) where the order of calls is not always predictable. </p> <p> <p>Note:  The matching of these values is required in order for A4T to function correctly. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step9_icon.png" id="image_57C8A469F046405D87CEEECBD8B37815" /> </td> 
   <td colname="col1"> <p>(Optional) Remove previous integration code. </p> </td> 
   <td colname="col2"> <p>We recommend that you remove the previous integration to simplify your implementation and eliminate the need to sort out discrepancies between the systems. You can remove any code you might have deployed for a previous SC to T&amp;T integration, including <span class="codeph"> mboxLoadSCPlugin</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"><img href="assets/step10_icon.png" id="image_9F30EFDCBBE140368431A18F39B50DE5" /> </td> 
   <td colname="col1"> <p>Enable the options for using Analytics as the reporting source for Target. </p> </td> 
   <td colname="col2"> <p>In <span class="keyword"> Target</span>, click <span class="uicontrol"> Setup</span> > <span class="uicontrol"> Preferences</span> and choose either <span class="uicontrol"> Select per activity</span> or <span class="uicontrol"> Adobe Analytics</span> to enable the options. </p> <p> 
     <ul id="ul_151FF5A080E14A10879710E599626DD6"> 
      <li id="li_25DB177CEC6142A9A5039D0A6E892BEB"> <span class="uicontrol"> Select per activity</span> lets you choose between <span class="keyword"> Target</span> and <span class="keyword"> Analytics</span> when creating each activity. </li> 
      <li id="li_DFD453742EA245DBB827E6F3C02362D4"> <span class="uicontrol"> Adobe Analytics</span> sets <span class="keyword"> Analytics</span> as the reporting source for all activities that you create. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
