---
description: By default, visitor profiles are stored for 14 days. This profile lifetime
  can be extended.
keywords: Overview and Reference
seo-description: By default, visitor profiles are stored for 14 days. This profile
  lifetime can be extended.
seo-title: Visitor profile lifetime
solution: Target
subtopic: Getting Started
title: Visitor profile lifetime
topic: Standard
uuid: 01ccda60-7e28-4d26-8d5d-1c0a022bbef0
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Visitor profile lifetime{#visitor-profile-lifetime}

By default, visitor profiles are stored for 14 days. This profile lifetime can be extended.

[Contact Client Care or your Adobe consultant](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to extend the profile lifetime at no additional cost. The lifetime can be set to as many as 90 days.

The [!DNL Target] JavaScript library you are using ( [!DNL mbox.js] or [!DNL at.js]) determines whether or not you need to download a new file:

<table id="table_2BD28C564EE44016A2B241DB7205F1DE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Target Library </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>mbox.js </p> </td> 
   <td colname="col2"> <p>If your profile is extended beyond the 14-day default, you must download a new <span class="filepath"> mbox.js</span> file after your consultant or Client Care changes your settings. The cookie extension to support the changed profile lifetime is included in the updated <span class="filepath"> mbox.js</span> file. After you start using the new library, your visitors' profile lifetimes will update. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at.js </p> </td> 
   <td colname="col2"> <p>You do not need to download a new <span class="filepath"> at.js</span> file if your profile is extended beyond the default. </p> </td> 
  </tr> 
 </tbody> 
</table>

The expiration date is not reset for existing profiles. If a previous visitor does not return for 15 days, that profile expires. If a previous visitor returns before the original two-week profile expires, the profile is reset to the extended lifetime. All new visitor profiles are set to the extended profile lifetime.

If you have two sites under one client code and a visitor visits both sites, the profile is set to the lifetime of profiles on whichever site was visited last. For example, if Site 1 has an 84-day profile lifetime and Site 2 has a 14-day lifetime, and the visitors visits Site 1 and then Site 2, that visitor's profile will expire in14 days. If the visitor visits Site 1 after visiting Site 2, the profile will expire in 84 days.
