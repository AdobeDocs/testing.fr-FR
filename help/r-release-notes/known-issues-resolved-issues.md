---
description: Information about known issues for this release of Target. Also includes
  information about issues that have been resolved.
keywords: known issues;resolved issues;release notes
seo-description: Information about known issues for this release of Target. Also includes
  information about issues that have been resolved.
seo-title: Known issues and resolved issues
solution: Target
title: Known issues and resolved issues
topic: Premium
uuid: f8e8e057-1842-4922-ab7f-4d5441048573
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Known issues and resolved issues{#known-issues-and-resolved-issues}

Information about known issues for this release of Target. Also includes information about issues that have been resolved.

>[!NOTE]
>
>The issue numbers in parentheses are for internal Adobe use.

## Known Issues {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

The following table lists the known issues for this release:

<table id="table_929058720A9E451CB414D9FD5975A804"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Geo targeting </p> </td> 
   <td colname="col3"> <p>Searching for a string that contains special characters (such as a space or a comma) is currently not working when creating geo-targeting audiences. This issue surfaces, for example, when creating audiences based on cities, states, countries, etc. For example, when searching for "new york", the search does not return valid results. </p> <p>Workaround: We have increased the number of items in the list so that users are not blocked. For example, while searching for "new york", search for "new" and then scroll the list to see the "new york" item. This issue will be fixed in a future release. (TGT-32364) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusion groups </p> </td> 
   <td colname="col3"> <p>The following are known issues with exclusion groups: </p> <p> 
     <ul id="ul_02C8799C07AD482692BDFEC180549331"> 
      <li id="li_33078A32F9EC427FB02CB8ACDAE37144"> <p>When auto-dedupe is applied after creating exclusion groups, the count on the activity diagram might be incorrect in the UI. </p> </li> 
      <li id="li_888157037C824C83B36852803201B95F"> <p>When existing activity with Exclusion Group is edited, the manual inclusions might not be correctly reflected in the UI. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recommendations </p> </td> 
   <td colname="col3"> <p>The following are known issues with Recommendations activities: </p> <p> 
     <ul id="ul_CEFE1D0E9CCE4A0AB641DF6E667CAF63"> 
      <li id="li_51505434C8134075BDD0D270A165174F"> <p>Recommendations "error.restapi.algorithmProfileAttributeInvalid" error occurs when specific profile attributes are used as the criteria key. </p> </li> 
      <li id="li_57221CEAABBB4CE3BE4BDC0D542013A6"> <p>When Back Promotion is used in a Recommendations activity, Criteria inclusion filters don't apply on backup ERs. </p> </li> 
      <li id="li_A7C21AFDAEEA4A66A82D7F06968530EE"> <p>The Recommendation Feeds UI does not show the correct status of indexing. The backend jobs are functioning correctly, but the UI is not able to fetch and display the current state. </p> <p>Workaround: An Alternative way to determine if a Recommendation Feed for a given Host Group has indexed properly is to check the Product Search UI (logged in as Admin) and view the last indexing time. This timestamp represents the last time the feed for a given host group was indexed. (TGT-27116) </p> </li> 
      <li id="li_76600BEA49E24BB6A0BC619A0B16495F"> <p>Recommended products might not display values up to two decimal points. For example, if you try to display the value in the design as 35.00, Recommendations displays 35 (no decimal points rather than two decimal points). (RECS-5972) </p> <p>Workaround: Pass the value of the entity into two <span class="codeph"> entity.attributes </span>. The first, `entity.value`, is a reserved parameter that expects a double. The second, can be a custom <span class="codeph"> entity.attribute </span> that will store the value of the entity as a string to allow for proper rending. </p> <p>For example: </p> <p> 
        <codeblock>
          "entity.value" : 35.00, 
          "entity.displayValue" : "35.00", 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multivariate Test (MVT) activities </td> 
   <td colname="col3"> <p>In an MVT activity, the winner shown in the table and graph are not consistent when checking metrics. This occurs if a user switches from Summary to Graph View, then switches back to Summary View, changes a metric and then switches to Graph View. When this issue occurs, the Summary View always shows the correct winner. If the user never switches Graph View between Summary views, the Graph View shows the correct winner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col3"> <p>The following are known issues with <span class="codeph"> at.js </span>: </p> <p> 
     <ul id="ul_31477BC709A84ECEBA8F5DDF1DC9335F"> 
      <li id="li_4E4ACBC00B03428F9965DBA56EB69838"> <p>When a page is loaded into the Visual Experience Composer (VEC), Target needs to determine if the global mbox setting is enabled or disabled and whether entityID or categoryID is present at the location where the user is trying to apply the recommendation in the VEC. Based on this information the criteria list is filtered. The default list has filtered algorithms, but the <a href="https://marketing.adobe.com/resources/help/en_US/target/recs/t_algo_select_recs.html" format="html" scope="external"> Compatible checkbox </a> lets you view the complete algorithms list. </p> <p>When using <span class="filepath"> at.js </span>, the <span class="wintitle"> Compatibility </span> checkbox is hidden, so you cannot see incompatible algorithms. </p> <p>This issue applies only to Recommendations activities that use the VEC. </p> <p>As a workaround, you should disable the <span class="wintitle"> Filter Incompatible Criteria </span> option in Recommendations > Settings. After disabling this setting, all criteria (compatible and incompatible) will be shown in the criteria picker. (TGT-25949) </p> </li> 
      <li id="li_93AFF74669DB4E44A59AEE966B95EDDB"> <p>Mboxes not firing on Microsoft Explorer 11 browsers after upgrading to <span class="codeph"> at.js </span> version 1.0 due to the interaction between <span class="keyword"> at.js </span> and Visitor API 2.2.0. This issue affects <span class="codeph"> at.js </span> version 0.9.6 and later. (TNT-27600) </p> </li> 
      <li id="li_D8EC246312F24D0585EA8998AF38A8B9"> <p> <span class="codeph"> at.js </span> might not work with Cordova/Hybrid apps because first-party cookies are not currently supported in them. (TNT-26166) </p> <p>As a workaround, configure <span class="codeph"> at.js </span> with the "x-only" option enabled and pass <span class="filepath"> mboxThirdPartyId </span> in calls to manage users. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mbox.js </p> </td> 
   <td colname="col3"> <p>The <span class="codeph"> mbox.js </span> library does not support client-side templating languages, such as Handlebars and Mustache. The <span class="codeph"> at.js </span> library does support these languages. </p> <p> <p>Note:  The <span class="codeph"> mbox.js </span> library is no longer being developed. All customers should migrate from <span class="codeph"> mbox.js </span> to <span class="codeph"> at.js </span>. For more information, see <a href="../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/t-target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA" format="dita" scope="local"> Migrate to at.js from mbox.js </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Redirect offers </p> </td> 
   <td colname="col3"> <p>The following are known issues with redirect offers: </p> <p> 
     <ul id="ul_961891B771FA40A3A34D48CF08E28F55"> 
      <li id="li_496FD2182D654079944732439E3A5837"> <p>A race condition on your page might cause page views on the original page and on the redirect page to be counted. Updates are planned in Q2 2018 to the <span class="filepath"> at.js </span> implementation to ensure that this race condition can be avoided. For more information about the issue and a workaround, see <a href="../c-integrating-target-with-mac/a4t/r-a4t-faq/c-a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905" format="dita" scope="local"> Redirect Offers - A4T FAQ </a>. </p> </li> 
      <li id="li_63A5A8139A96453F84A7E095B2A93FF0"> <p>Redirect activities in <span class="codeph"> at.js </span> implementations might cause the preview URL to enter into a loop (the offer is delivered repeatedly). You can use <a href="../c-activities/c-activity-qa/c-activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40" format="dita" scope="local"> QA Mode </a> instead to perform Preview and QA. This issue does not impact the actual delivery of the offer. (TGT-23019) </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Implementation: Global Mbox Auto Create </p> </td> 
   <td colname="col3"> <p>On the <span class="wintitle"> Implementation </span> tab ( <span class="wintitle"> Setup </span> > <span class="wintitle"> Implementation </span>) the <span class="wintitle"> Global Mbox Auto Create </span> field will be "false" by default for a newly provisioned tenant. </p> <p>When <span class="filepath"> mbox.js </span> is downloaded for the first time after provisioning, the <span class="wintitle"> Global Mbox Auto Create </span> field is set to "true" in the downloaded <span class="filepath"> mbox.js </span> file and in the <span class="keyword"> Target </span> backend, but it will continue to display as "false" on the <span class="wintitle"> Implementation </span> page in the UI until the page is refreshed (after the page is refreshed, the status will be "true.") </p> <p> <span class="filepath"> at.js </span> will be downloaded with <span class="codeph"> global_mbox_autocreate = false </span> for a newly provisioned tenant. If <span class="filepath"> mbox.js </span> is downloaded first, <span class="codeph"> global_mbox_autocreate </span> is set to "true" and <span class="filepath"> at.js </span> will also be downloaded with <span class="codeph"> global_mbox_autocreate = true </span>. (TGT-15929) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Success metrics </p> </td> 
   <td colname="col3"> <p>Success metrics with the advanced option "How will the count be incremented" set to "every impression" or "every impression (excluding refreshes)" cannot be used as a success metric that another metric is dependent on. </p> <p>When a success metric is set to be incremented on every impression, Target counts the visitor again every time the visitor visits this success metric. Target then resets the success metric "membership" to 0 so it can count again on the next impression. Thus, if another metric requires this metric to have been seen first, Target will never recognize that the user has seen the first metric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Analytics for Target (A4T) </p> </td> 
   <td colname="col3"> <p>Target activity impressions and conversions are currently counted incorrectly in <span class="keyword"> Analysis Workspace </span>. </p> <p>As a workaround, please rely on A4T data in <span class="keyword"> Reports &amp; Analytics </span> until this issue is fixed. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resolved Issues {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

As known issues above are resolved, they will be moved to the following table and additional notes, if necessary, will be added.

<table id="table_EB9EA3918D594B5CB8155E77E5931793"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col3" class="entry"> Description </th> 
   <th colname="col4" class="entry"> Notes </th> 
  </tr> 
 </thead>
 <tbody> 
 <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col3"> <p>Mboxes not firing on Microsoft Explorer 11 browsers after upgrading to at.js version 1.0 due to the interaction between at.js and Visitor API 2.2.0. This issue affects at.js version 0.9.6 and later. (TNT-27600)</p> </td> 
   <td colname="col4"> <p>Fixed with the release of API 2.3.0 or later. </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p>Geo targeting</p> </td> 
   <td colname="col3"> <p>Searching for a string that contains special characters (such as a space or a comma) is currently not working when creating geo-targeting audiences. This issue surfaces, for example, when creating audiences based on cities, states, countries, etc. For example, when searching for "new york", the search does not return valid results.</p> </td> 
   <td colname="col4"> <p>Fixed in November, 2018. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col3"> <p>When using <span class="codeph"> at.js </span> version 1.6.0, Analytics for Target (A4T) redirects occur, but without activity qualification. </p> </td> 
   <td colname="col4"> <p>Fixed with the release of at.js 1.6.2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activities </p> <p>Workspaces </p> <p>Delete activity API </p> </td> 
   <td colname="col3"> <p>Activities in the default workspace deleted via API continue to display in the Target UI. As a workaround, delete all activities in the default workspace using the Target UI. (TGT-31315) </p> </td> 
   <td colname="col4"> <p>Fixed October 25, 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Automated Personalization (AP) offer-level reporting </p> </td> 
   <td colname="col3"> <p>When you click the targeted experience in an Automated Personalization (AP) activity's report to view offer-level reporting, currently you see empty results, an error message, or a spinning icon. (TNT-30695) </p> </td> 
   <td colname="col4"> <p>Fixed September 27, 2018. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Editor </p> </td> 
   <td colname="col3"> <p>If you reload the VEC on step 1 of the three-step guided workflow while working with the Code Editor in Firefox and Internet Explorer, the Modifications tab does not render properly; however, the VEC's functionality is not impacted. (TGT-28730) </p> </td> 
   <td colname="col4"> <p>This was fixed in the 18.9.1 release. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recommendations activity that uses an Attribute Promotion rule. </p> </td> 
   <td colname="col3"> <p>When you edit or copy a Recommendations activity that uses an Attribute Promotion rule, the "Has missing field" error displays when clicking <span class="wintitle"> Save </span>. </p> </td> 
   <td colname="col4"> <p>This was fixed in the 17.8.1 release. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recommendations Feeds index status </p> </td> 
   <td colname="col3"> <p>The Recommendation Feeds UI does not show the correct status of indexing. The backend jobs are functioning correctly, but the UI is not able to fetch and display the current state. </p> </td> 
   <td colname="col4"> <p>This was fixed in the 17.10.1 release. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Backup Recommendations </p> </td> 
   <td colname="col3"> <p>Backup recommendations erroneously display "Enabled" on Recently Viewed Items cards in the Target UI. (TGT-29308) </p> </td> 
   <td colname="col4"> <p>This was fixed in the 18.4.1 release so that "Disabled" displays. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Auto-Target activities and reporting audiences </p> </td> 
   <td colname="col3"> <p>When a reporting audience's name used in an Auto-Target activity is changed, further updates from Target for that activity might fail with an error message. </p> </td> 
   <td colname="col4"> <p>This issue was fixed with the Target 18.5.1 (May 22, 2018) release. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col3"> <p>The algorithm for extracting the top-level domain that should be used when saving cookies has changed in <span class="codeph"> at.js </span> version 0.9.6. Because of this change, cookies cannot be saved to addresses that use IP. Most of the time, IP addresses are used for testing purposes, but as workarounds you can use DNS entries, adjust the hosts file on a local box, or use the  targetGlobalSettings() at.js function to insert a code snippet to support IP addresses. </p> </td> 
   <td colname="col4"> <p>This issue was remedied in at.js version 1.2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enterprise User Permissions for Target Premium </p> </td> 
   <td colname="col3"> <p>As part of the Enterprise Permissions migration, all Target Premium user management was moved from the Adobe Target UI to Adobe Admin Console. </p> <p>As a result of the migration, there are two potential issues you should be aware of: </p> <p> 
     <ul id="ul_1EEA21A2B8A6467B8F3DD4C5637DA0F0"> 
      <li id="li_0AF3A22632A34709A8BD0BAF24546DE9"> <p>Non-admin users received an email indicating that they now have access to Adobe Target. This indicates that the migration was completed for your organization. The email itself can be disregarded. </p> </li> 
      <li id="li_B55732FDA9244FC08331204C09427002"> <p>Following the migration, there have been some reports of previously disabled users reappearing in the Adobe Admin Console. This could be an issue for your organization if disabled users in the Adobe Admin Console were still appearing on your user list in Target prior to the migration. We recommend that administrators review the list of users in Admin Console to validate access. </p> </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>This issue was fixed on August 30, 2017 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activity Creation </p> </td> 
   <td colname="col3"> <p>An issue with the 17.6.2 release may have affected activities created and/or updated between June 22, 2017 and June 29, 2017. Activities with the following were affected: </p> <p> 
     <ul id="ul_1B2B60770A584FB0A10B368040BCD2AA"> 
      <li id="li_AF342C0F1A684830999D70EE8740317E">Any experiences that were rearranged in Experience Targeting (XT) would have reverted back to the original order </li> 
      <li id="li_759123BB5827459D95445A78E5641B4E">Any segment rules local to the activity (not saved within an audience) would have been lost: combined audiences, location refinements, and any rules on success metrics. </li> 
     </ul> </p> <p>No other activities were affected. </p> <p> <p>Important:  This issue is not fixed automatically. You must re-save any activity that was affected to fix the issue. </p> </p> </td> 
   <td colname="col4"> <p>This issue was fixed on June 29, 2017 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Form-Based Experience Composer </p> </td> 
   <td colname="col3"> <p>The following known issues have been reported when using the Form-Based Experience Composer: </p> <p> 
     <ul id="ul_25843F865BCE43E6A81361FD43AD8B15"> 
      <li id="li_83F6C9576DE64EF1A8FDE3E3FCDD3606"> <p>If you use the Form-Based Experience Composer with an mbox other than the auto-created global mbox ( <span class="codeph"> target-global-mbox </span>), and then choose an engagement metric as a success metric, the metric increments only on pages that have the mbox used in the activity. As an example, if your mbox is <span class="codeph"> homepage_mbox </span>, the <span class="wintitle"> Pages Per Visit </span> metric is the number of hits to the <span class="codeph"> homepage_mbox </span> during that visit. (TGT-22789) </p> </li> 
      <li id="li_6296B3AD67F94577BED07A8E05AE6DB5"> <p>A JavaScript exception is thrown when you delete an experience in an Experience Targeting (XT) activity when using the Form-Based Experience Composer during step 1 of the process. (TGT-24366) </p> </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>The first issue was fixed in the Target 17.3.1 release (March 2017). </p> <p>The second issue was fixed in the Target 17.6.1 release (June 2017). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col3"> <p>Since the release of <span class="keyword"> Target </span> 17.4.1 (April 27, 2017), using the Insert Image action in the Visual Experience Composer (VEC) causes the offer content to not be delivered when using the at.js library. </p> </td> 
   <td colname="col4"> <p>A fix for this issue has been made to <span class="codeph"> at.js </span> version 0.9.7 released May 22, 2017. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recommendations </p> </td> 
   <td colname="col3"> <p> <span class="keyword"> Recommendations </span> feeds take longer to process than expected. (COR-2836) </p> </td> 
   <td colname="col4"> <p>Fixed in the Target 16.10.1 release. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reporting: A/B and Experience Targeting (XT) activities </p> </td> 
   <td colname="col3"> <p>Between April 27 at 9:00 p.m. PST and May 5 at 6:00 a.m. PST, A/B and XT activities created or edited with any metrics using the “Viewed a Page” conversion action (that were not based on other metrics), might have incorrectly recorded conversions. This issue is now resolved; however, reporting on the “Viewed a Page” conversion action for these activities during the impacted time period might not be accurate and, unfortunately, cannot be corrected. We recommend that for any decisions based on “Viewed a Page” conversion actions for these activities you rely only on data recorded before or after the impacted period. </p> <p>Reporting data for other metrics can still be used because they were not impacted. </p> </td> 
   <td colname="col4"> <p>Fixed in the Target 17.4.3 hotfix. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Offers: A/B and Experience Targeting (XT) activities </p> </td> 
   <td colname="col3"> <p> The delivery and preview was impacted for offers in A/B and XT activities having at least two experiences and that were either created or edited using the Form-Based Experience Composer between Friday April 28 (9 p.m. PT) and Monday May 1 (9:15 p.m. PT). Only offers with default content were displayed. </p> </td> 
   <td colname="col4"> <p>Fixed in the Target 17.4.3 hotfix. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col3"> <p>The following actions caused the offer to not be delivered when using the Visual Experience Composer (VEC) and at.js: Move and Rearrange. </p> </td> 
   <td colname="col4"> <p>A fix for this issue was made to <span class="codeph"> at.js </span> version 0.9.6. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reports </p> </td> 
   <td colname="col3"> <p>The ability to view multiple metrics in a report, included in the Target 17.3.1 release (March 30, 2017) has been removed due to unexpected behavior. This feature will be available again in an upcoming release. </p> </td> 
   <td colname="col4"> <p>The ability to view multiple metrics in a report was included in the Target 17.4.1 release (April 27, 2017). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Offers </p> </td> 
   <td colname="col3"> <p>Images deleted from the <span class="wintitle"> Image Offers </span> library ( <span class="wintitle"> Offers </span> > <span class="wintitle"> Image Offers </span>) remain visible in the UI. In an upcoming release, these deleted images will no longer display. In the meantime, deleted images display in the UI, but have a status of <span class="wintitle"> Deleted </span>. (TGT-23793) </p> </td> 
   <td colname="col4"> <p>Fixed in the Target 17.4.1 release (April 27, 2017). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Redirect offers </p> </td> 
   <td colname="col3"> <p>For Recently Viewed criteria, entity based dynamic rules will lead to no recommendation if the <span class="codeph"> entity.id </span> parameter is not passed in the mbox request. (RECS-6241) </p> </td> 
   <td colname="col4"> <p>This issue was fixed after the Recommendations release (March 22, 2018). After the Recommendations release, Target skips the entity-based dynamic rules if <span class="codeph"> entity.id </span> is not passed in the mbox request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col3"> <p>When users attempt to download <span class="codeph"> at.js </span> from the Implementations details page after updating <span class="codeph"> at.js </span> settings, <span class="codeph"> mbox.js </span> is downloaded instead of <span class="codeph"> at.js </span>. (TGT-23069) </p> </td> 
   <td colname="col4"> <p>Fixed in the Target 17.3.1 release (March 30, 2017). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Global exclusion rules </p> </td> 
   <td colname="col3"> <p>Global exclusion rules are taking 10-20 minutes to propagate to the edge for Premium Recommendations. (RECS-5270) </p> </td> 
   <td colname="col4"> <p>Fixed in the <span class="keyword"> Recommendations </span> 17.2.2.0 release (March 6, 2017). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Analytics for Target (A4T) reporting </p> </td> 
   <td colname="col3"> <p>Reports are not updated when the reporting metric is switched. This is a UI issue. There is no impact on reporting data collection or delivery. (TGT-22970) </p> </td> 
   <td colname="col4"> <p>Fixed in the <span class="keyword"> Target </span> 17.2.2.0 release (February 24, 2017). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CSV reports </p> </td> 
   <td colname="col3"> <p>Downloaded reports do not honor the <span class="wintitle"> Exclude Extreme Orders </span> setting. (TGT-21871) </p> </td> 
   <td colname="col4"> <p>Fixed in the <span class="keyword"> Target </span> 17.2.1.0 release. </p> </td> 
  </tr> 
 </tbody> 
</table>
