---
description: This topic contains answers to questions that are frequently asked about
  classifications and using Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications
  importer;post-tnt-action
seo-description: This topic contains answers to questions that are frequently asked
  about classifications and using Analytics as the reporting source for Target (A4T).
seo-title: Classifications - A4T FAQ
solution: Target
title: Classifications - A4T FAQ
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Classifications - A4T FAQ{#classifications-a-t-faq}

This topic contains answers to questions that are frequently asked about classifications and using Analytics as the reporting source for Target (A4T).

## After using the Classifications Importer to download classifications, how do I match the post-tnt-action value with an activity name? {#section_6045DAC488B248418F430E663C38D001}

You can download the classifications for the A4T/TNT string from the Admin Tools [Classification Importer](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html). The variable is called “TNT” in the export list. The downloaded data includes the friendly names for activities, experiences, and so forth.

This lookup file is useful for customers that receive Adobe’s clickstream data feed. The file provides friendly names for the `post_tnt` and `post_tnt_action` columns.

The string format of the TNT variable is `activityID:experienceID:targettype|event`.

* targettype will always be 0 for A4T.
* Event = 0 represents an experience entrance.
* Event = 1 represents an experience visit.
* Event = 2 represents an activity impression.
* Event = 32767 represents an activity conversion.

You can download the classification file on a frequent basis from the UI using a [browser export](https://marketing.adobe.com/resources/help/en_US/reference/browser_export.html) or an [FTP export](https://marketing.adobe.com/resources/help/en_US/reference/ftp_export.html). You can also engage with Engineering Services to obtain the file as a lookup table along with a clickstream data feed.
