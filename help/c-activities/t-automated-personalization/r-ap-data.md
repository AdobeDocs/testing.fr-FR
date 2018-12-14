---
description: Target automatically collects and uses a variety of data to build its
  personalization algorithms in Automated Personalization (AP) and Auto-Target (AT)
  activities. When a visitor enters the AP or AT activity, a snapshot of information
  is passed to a set of "training records" (the visitor data that the personalization
  algorithms will learn on).
seo-description: Target automatically collects and uses a variety of data to build
  its personalization algorithms in Automated Personalization (AP) and Auto-Target
  (AT) activities. When a visitor enters the AP or AT activity, a snapshot of information
  is passed to a set of "training records" (the visitor data that the personalization
  algorithms will learn on).
seo-title: Data collection for Target's personalization algorithms
solution: Target
title: Data collection for Target's personalization algorithms
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Data collection for the Target personalization algorithms{#data-collection-for-the-target-personalization-algorithms}

Target automatically collects and uses a variety of data to build its personalization algorithms in Automated Personalization (AP) and Auto-Target (AT) activities. When a visitor enters the AP or AT activity, a snapshot of information is passed to a set of "training records" (the visitor data that the personalization algorithms will learn on).

To learn more about the Target personalization algorithms, see [Random Forest Algorithm](../../c-activities/t-automated-personalization/c-algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

The following table shows the data collected by Automated Personalization by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/c-personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). You can augment the input data set at any time. To learn more about how to upload additional data, see [Uploading Data for the Target Personalization Algorithms](../../c-activities/t-automated-personalization/c-uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

<table id="table_F46105983FD14051BBE9C429EE9B2ACB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Type </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col03" class="entry"> Data Type Naming Convention </th> 
   <th colname="col3" class="entry"> Example Attributes </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL Parameters </p> </td> 
   <td colname="col2"> <p>Target inspects the URL to extract the URL parameters. </p> </td> 
   <td colname="col03"> <p>Custom - URL Parameter - [URL Parameter] </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_499CF984C34D454491EAC4A8791F544C"> 
      <li id="li_6B86A75E1EAF4C98B2E7A3C66A5297CA"> <p>Custom data </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Referring URL Parameters </p> </td> 
   <td colname="col2"> <p> In general, the referring URL is the URL that referred to a particular page that initiated the mbox call. </p> <p> Note that this variable can be impacted by the users' activity on your site as well as the technical implementation of your site. </p> </td> 
   <td colname="col03"> <p>Custom - [Referring URL Parameter] - [Parameter value] </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_1A1A063B239B4F0A8A8F09B2068E2F28"> 
      <li id="li_57112ADD82D14170A3E2311340D1CA68"> <p>Custom data </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Environmental and Session data </p> </td> 
   <td colname="col2"> <p>Information about how and when the user is accessing the activity. </p> </td> 
   <td colname="col03"> <p> 
     <ul id="ul_91FD14FB9BA94A079A0BB91F097FDF4E"> 
      <li id="li_4E2B828672574F32917DAFFF3A5C3B75"> <p>Visitor Profile - [attribute name] </p> </li> 
      <li id="li_1519FE988DEC490E9C8C03AEA570CDB2"> <p>Browser - [browser attribute] </p> </li> 
      <li id="li_33ECE3B6EF014767BFD4769ED728EC0C"> <p>Operating System - [OS attribute] </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_EEECF8FD839A4C938CFD27DC1EA16F24"> 
      <li id="li_1F33C21112954F51A444FEC69A74ABB8"> <p>Visitor Profile - Start of Most Recent Visit </p> </li> 
      <li id="li_BE781803D7BF4C95B6A01B8CE1D06147"> <p>Visitor Profile -Total Visits </p> </li> 
      <li id="li_39B446FAEDC44247AD11C48A2D1240EA"> <p>Visitor Profile - Average Time per Visit </p> </li> 
     </ul> </p> <p> 
     <ul id="ul_748D3E8BEB714EF389CD633CA3ACF5FF"> 
      <li id="li_51697C43E1944243993E9C8431643EEA"> <p>Browser - Timezone </p> </li> 
      <li id="li_2D8D58AD18134FC0926B7CC77BC082F0"> <p>Browser - Day of Week </p> </li> 
      <li id="li_96B56BF96D4646359B6DD08D2CB945B2"> <p>Browser - Language Setting </p> </li> 
      <li id="li_E3FAA5527534482095AE5724BEC781A2"> <p>Browser - Type </p> </li> 
     </ul> </p> <p> 
     <ul id="ul_B9883D3A7565468698B635CAFDC24880"> 
      <li id="li_40D2D56E734843F1B8E01C23BA2D6F25"> <p>Operating System - Version </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geography </p> </td> 
   <td colname="col2"> <p>Information on where the visitor is located. </p> </td> 
   <td colname="col03"> Geo - [geo attribute] </td> 
   <td colname="col3"> <p> 
     <ul id="ul_E0C55DFA265344D0B955E8248A3B49B5"> 
      <li id="li_7BEEBD57056D4520AE15938AF17CB9F1"> <p>City </p> </li> 
      <li id="li_1C0190C4B3734C7B8892DAB5546D847D"> <p>Country </p> </li> 
      <li id="li_8C562CB1CE104A0B9DF7A7FF01CDF111"> <p>Region/State </p> </li> 
      <li id="li_C24C3F629C524961B35D6B079B22266F"> <p>Zip Code </p> </li> 
      <li id="li_E9D9AEBCC021491799352D24D9927933"> <p>Latitude </p> </li> 
      <li id="li_D73EB93C55094AE29839B69B6F85ED4D"> <p>Longitude </p> </li> 
      <li id="li_39E5A629A1AA45E197B2012EB6945999"> <p>ISP or Mobile Carrier </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Device and Mobile Data </p> </td> 
   <td colname="col2"> <p> Device and mobile-specific information. </p> </td> 
   <td colname="col03"> <p> 
     <ul id="ul_17AFB42C5821474BB49B902B855589E0"> 
      <li id="li_AE430A3788CE4108958ED812A9467942"> <p>Device - [device attribute] </p> </li> 
      <li id="li_D8EF1D289913431A8FFE705A964FBFE0"> <p>Mobile - [mobile attribute] </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_0BFD068CD5CA41FFBAD37429CBE72CD6"> 
      <li id="li_537AEBE6177B47E4B4A2D5B8B24DAFB9"> <p>Mobile Device OS </p> </li> 
      <li id="li_4298268BFF614F6F914C16F38268F4AF"> <p>Mobile Screen Size </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

