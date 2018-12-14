---
description: If your activity does not appear on your site, these troubleshooting
  suggestions should help you find your solution.
keywords: troubleshoot target;troubleshooting target;default content;test not live;activity
  not live;targeting not working;previous experience displays;cannot create activities;can't
  create activities;create activities;page structure changed;page structure modified;error
  message;error delete profile script;ajax not working
seo-description: If your activity does not appear on your site, these troubleshooting
  suggestions should help you find your solution.
seo-title: Troubleshoot activities
solution: Target
title: Troubleshoot activities
topic: Advanced,Standard,Classic
uuid: 5b22c369-0efc-48c0-a0dc-0179b18536fe
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Troubleshoot activities{#troubleshoot-activities}

If your activity does not appear on your site, these troubleshooting suggestions should help you find your solution.

>[!NOTE]
>
>In addition to the following troubleshooting information, see [Troubleshooting Target](../../r-troubleshooting-target/r-troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) for links to additional troubleshooting topics, FAQs, and other useful information about troubleshooting activities and other features in [!DNL Adobe Target].

<table id="table_E64C8310F6C24FBFAFC91BA89EA1F335"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problem </th> 
   <th colname="col2" class="entry"> Solution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>You are seeing default content. </p> </td> 
   <td colname="col2"> <p>Make sure your activity is complete and has been activated. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activity is not live. </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b> Go to overview tab and see if test is marked inactive or draft . </p> <p> <b>Options:</b> </p> <p> 
     <ul id="ul_EA9C04EF47CC409AA9C6C5A451025E48"> 
      <li id="li_268F3ED02948417D9CF1DE9F17AFC774"> <p>Activate test. </p> </li> 
      <li id="li_E60A753780E84578B9D3E5A7A5877386">Use Preview Links to display inactive test. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You don't qualify for the audience targeting conditions. </p> </td> 
   <td colname="col2"> <p> <b>Validate: </b>Review targeting conditions on overview page. </p> <p><b>Options:</b> </p> <p> 
     <ul id="ul_485E1B9FBC204CD980A9F2D94161DD35"> 
      <li id="li_2C5FF5B606C5443DAF4A73D6FA616CD4"> <p>Qualify and try again. </p> </li> 
      <li id="li_8A922A1CFA5A4797BEBFCE96F8686505"> <p> Use Preview Links to bypass targeting conditions. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>The page doesn't qualify for the page targeting conditions. </p> </td> 
   <td colname="col2"> <p> <b>Validate: </b> On the overview page, determine if the page falls outside of the targeting conditions. </p> <p><b>Options:</b> </p> <p> 
     <ul id="ul_7C4C60AA9CB54E80B6F0F265D7FE84D1"> 
      <li id="li_9FE8EAD4C6CF48C39568E5EB877CD0E5"> <p> Go to the Visual Experience Composer, click <span class="uicontrol"> URL</span>><span class="uicontrol"> Advanced</span>>current page. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A previous experience displays rather than the new experience. </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b> Try one of the options below and attempt to view the experience again. </p> <p> <b>Options:</b> </p> <p> 
     <ul id="ul_45DD212D70C74BD5B35E1975B1B2CA80"> 
      <li id="li_3C632D33F1BA49959B198DDFA006B82D"> <p>Clear cache and cookies, then try again. </p> </li> 
      <li id="li_F9DF0CB86DCC40BF9FD5F2D4C04F3747"> <p>Try a different browser. </p> </li> 
      <li id="li_FAFEC7C332154447A80CDA9784E70655"> <p>Use Private/Incognito mode. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You were recently added to Target but cannot create activities. </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b>Click <span class="uicontrol"> Create Activity</span>. If the option is not available, you most likely have not been given sufficient rights to create an activity. </p> <p> <b>Options:</b> </p> <p>Once you are added as a user in Target you need to have the Approver role in order to create Activities. </p> <p> 
     <ul id="ul_817DD00057774B06827A6451A2B46BE0"> 
      <li id="li_2E7A1D33C2CF4BEA8782C2AD78F4874E"> <p>Ask the Admin of your account to make you an Approver. </p> </li> 
      <li id="li_A3BABEB70AA1419C8B709F8FDB3BDBA8"> <p>If you are the Admin, give yourself the Approver role from <span class="uicontrol"> Setup</span> > <span class="uicontrol"> Users</span> in Target Standard. </p> <p> See <a href="../../administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7" format="dita" scope="local"> Assign Yourself the Approver Role</a>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>The structure of the page changed since setting up activity. </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b> Go to the Visual Experience Composer for the existing activity. Look for warning message indicating that the selectors (or structure) has changed. </p> <p> <b>Options:</b> </p> <p> 
     <ul id="ul_8CACB4017E0048D88A21433785827B6A"> 
      <li id="li_E7AF83ABC5FE4759AB77ECA4AA71D3EB"> <p>Rebuild the activity. </p> </li> 
     </ul> </p> <p>For more information about how page modifications affect Target's ability to display, see <a href="../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/c-vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB" format="dita" scope="local"> Page Modification Scenarios</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>The structure of the page is modified during page load (at run time). </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b> Ask developer. </p> <p> <p>Note:  In order for Target to recognize where activity changes should be applied, avoid dynamically inserting an elements with the same class or dynamically modifying the class of any siblings. </p> </p> <p> <b>Options:</b> </p> <p> 
     <ul id="ul_8C2E2601DA6B4E4CA388EF0D9C748759"> 
      <li id="li_9E970E0E9B1847C7AD030CB67C032AF7"> <p> Update page code to uniquely identify each element that will be tested (using an <span class="codeph"> id</span>). </p> </li> 
      <li id="li_2523B1A8518E45F2B4130ED52DE7A0CF"> <p> Stop dynamically modifying the class or siblings as described above. </p> </li> 
     </ul> </p> <p>For more information about how page modifications affect Target's ability to display, see <a href="../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/c-vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB" format="dita" scope="local"> Page Modification Scenarios</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Mbox.js</span> is popping all subsequent code out of the head and into the body. </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b> View source to determine if an declarations follow the <span class="filepath"> mbox.js</span> file before the closing <span class="codeph"> &lt;/body></span> tag. </p> <p> <b>Options:</b> </p> <p> 
     <ul id="ul_55305F2ADE094588AC41D338F498377B"> 
      <li id="li_5FCC7F1DE19A4361A244A096AD63827D"> <p> Place <span class="filepath"> mbox.js</span> as the last item inside the <span class="codeph"> &lt;head></span> section of your page. </p> </li> 
      <li id="li_6EB754FFC45B48D397AFBDACF587728B"> <p> Use unique <span class="codeph"> div id</span>s on the highest-level elements inside the body. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Other activities are running on the same page. </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b> Use the Collisions tab to see of other activities are running. </p> <p> <p>Note:  The Collisions tab does not work with the Template Testing module. </p> </p> <p> <b>Options:</b> </p> <p> 
     <ul id="ul_CE71A5DF47294F828AD4184E64903B71"> 
      <li id="li_FDD33A6EC6904DC899094102D7AAC9AA"> <p> Increase the priority of this activity. </p> </li> 
      <li id="li_8EFAE4F34AD949DD92BFB27DDFDF8BA5"> <p> Decrease the priority of other activities. </p> </li> 
      <li id="li_4133739AC11C458AA33C3927665D3983"> <p> Deactivate other activities. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>An error message appears when you delete a profile script. </p> </td> 
   <td colname="col2"> <p> <b>Validate:</b> Deleting a profile script from Target Standard/Premium displays the error message, "Failed to delete profile script." </p> <p> <b>Options:</b> </p> <p>Do one of the following: </p> <p> 
     <ul id="ul_11DE7952A83C4881A0A15A1F1A1655C7"> 
      <li id="li_06EBBB9B5F7944E6B2F05A563EEB0D3F"> <p>Delete again. The success message appears. </p> </li> 
      <li id="li_D20987979535440FB110185838B06AF4"> <p>Wait about 10 minutes for the Target Standard/Premium importer to run. The importer updates the profile script list. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Some ajax mbox calls are not working. </p> </td> 
   <td colname="col2"> <p> <p>Note:  Multiple ajax mbox calls with the same mbox name but different parameters will not work on the same page. Only the first call will be made. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You activated an activity using the Target API, but the activity shows a status of Inactive in the Target UI. </p> </td> 
   <td colname="col2"> <p>When you perform certain actions, such as activating an activity outside of the UI using the Target API, the update can take up to ten minutes to propagate to the UI. </p> </td> 
  </tr> 
 </tbody> 
</table>

