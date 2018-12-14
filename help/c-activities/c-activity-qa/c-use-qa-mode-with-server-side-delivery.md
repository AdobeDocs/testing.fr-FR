---
description: Use QA URLs with server-side delivery to perform easy end-to-end activity
  QA with preview links that never change, optional audience targeting, and QA reporting
  that stays segmented from live activity data.
keywords: qa;server side;server-side;preview;preview links
seo-description: Use QA URLs with server-side delivery to perform easy end-to-end
  activity QA with preview links that never change, optional audience targeting, and
  QA reporting that stays segmented from live activity data.
seo-title: Use Activity QA with server-side delivery
solution: Target
title: Use Activity QA with server-side delivery
topic: Advanced,Standard,Classic
uuid: c1875243-e37f-4205-9e6b-6e96cadf4a7f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Use Activity QA with server-side delivery{#use-activity-qa-with-server-side-delivery}

Use QA URLs with server-side delivery to perform easy end-to-end activity QA with preview links that never change, optional audience targeting, and QA reporting that stays segmented from live activity data.

The standard implementation of Activity QA supports passing `qa_mode` parameters via `pageUrl` mbox parameters. This approach is convenient for standard/ajax mbox calls. However, for server-to-server calls, this is not the best approach for a Mobile SDK case when `pageUrl` is not available.

The following code sample shows Activity QA in a server-side call:

```
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

The following table explains a server-side request's details:

<table id="table_B114F67E9F154558B2ECC135D17655BF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Default Value </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> token</span> </p> </td> 
   <td colname="col2"> <p>Encrypted token </p> </td> 
   <td colname="col3"> <p>None. </p> <p> It cannot be empty. </p> </td> 
   <td colname="col4"> <p>An encrypted entity that contains the list of activity IDs that are allowed to be executed in Activity QA. </p> <p>Validation rules: Should be an encrypted token belonging to the client specified in the mbox request. All activities specified in the token should belong to the client. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> bypassEntryAudience</span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>False </p> </td> 
   <td colname="col4"> <p>Specifies whether entry step targets for QA activities should be evaluated or if they should be considered as matching. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> listedActivitiesOnly</span> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>False </p> </td> 
   <td colname="col4"> <p>Specifies whether QA activities should be executed in isolation or if they should be evaluated as active activities for the current environment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> evaluateAsTrueAudienceIds</span> </p> </td> 
   <td colname="col2"> <p>List of IDs </p> </td> 
   <td colname="col3"> <p>Empty list. </p> </td> 
   <td colname="col4"> <p>List of audience IDs that should always be evaluated as true in the scope of the mbox request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> evaluateAsFalseAudienceIds</span> </p> </td> 
   <td colname="col2"> <p>List of IDs </p> </td> 
   <td colname="col3"> <p>Empty list. </p> </td> 
   <td colname="col4"> <p>List of audience IDs that should always be evaluated as false in the scope of the mbox request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> activityIndex</span> </p> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>Null. </p> <p> It cannot be empty. </p> </td> 
   <td colname="col4"> <p>Activity index in the encrypted token. If <span class="codeph"> activityIndex</span> is out of boundaries of the activity in the token or if null, it will be ignored. Index starts with 1. </p> <p>Validation rules: Should be at least one activity index, and should reference an activity specified in the token. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>experienceIndex </p> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>Null. </p> </td> 
   <td colname="col4"> <p>When specified, selects an experience by index in the activity definition. If not specified or out of boundaries, it will fall-back to the activity's experience selector strategy. Index starts with 1 </p> <p>Validation rules: Can be null, or should reference an experience in the activity. </p> </td> 
  </tr> 
 </tbody> 
</table>

