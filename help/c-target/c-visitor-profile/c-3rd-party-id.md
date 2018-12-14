---
description: The mbox3rdPartyID is your company's visitor ID, such as the membership
  ID for your company's loyalty program.
keywords: mbox;mbox3rdPartyID;profile syncing;profile synch
seo-description: The mbox3rdPartyID is your company's visitor ID, such as the membership
  ID for your company's loyalty program.
seo-title: Real-time profile syncing for mbox3rdPartyID
solution: Target
title: Real-time profile syncing for mbox3rdPartyID
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Real-time profile syncing for mbox3rdPartyID{#real-time-profile-syncing-for-mbox-rdpartyid}

The mbox3rdPartyID is your company's visitor ID, such as the membership ID for your company's loyalty program.

When a visitor logs in to a company's site, the company typically creates an ID that is tied to the visitor's account, loyalty card, membership number, or other applicable identifiers for that company.

When a visitor accesses a page on which Target is enabled, that visitor is assigned a Target PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyID to Target, Target connects that visitor's mbox3rdPartyID with the Target PCID.

Every three to five minutes, updates are synced with the database. When the visitor logs out, the merged data replaces the previous data associated with the mbox3rdPartyID, creating a more complete record of that visitor's actions. If the same attribute exists in both IDs--for example, the PCID has category=hats and the mbox3rdPartyID has category=skis, or if the visitor saw experience A before logging in, but experience B is stored in the mbox3rdPartyID--the attribute stored in the mbox3rdPartyID overwrites the attribute from the PCID. If the visitor was in one activity or experience before logging in, but a different activity and experience are stored in the mbox3rdPartyID, after logging in that visitor is placed into the mbox3rdPartyID activity and experience.

| PCID (Not Logged In) | mbox3rdPartyID (Logged In) | Merged and Saved to mbox3rdPartyID |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Activity 1, Experience A | Activity 1, Experience B | Activity 1, Experience B |
| Activity 1 |  | Activity 1 |

When the visitor logs out, the merged profile is maintained.
