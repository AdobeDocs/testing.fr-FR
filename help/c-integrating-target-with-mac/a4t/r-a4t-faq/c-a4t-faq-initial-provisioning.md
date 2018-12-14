---
description: This topic contains answers to questions that are frequently asked about
  provisioning Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4t;provisioning;provisioning;adobe
  Experience Cloud
seo-description: This topic contains answers to questions that are frequently asked
  about provisioning Analytics as the reporting source for Target (A4T).
seo-title: Initial provisioning - A4T FAQ
solution: Target
title: Initial provisioning - A4T FAQ
topic: Standard
uuid: cc80f879-ad2a-46d6-adc2-df616e8ab0b5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Initial provisioning - A4T FAQ{#initial-provisioning-a-t-faq}

This topic contains answers to questions that are frequently asked about provisioning Analytics as the reporting source for Target (A4T).

## How can I tell whether A4T is enabled on my Target account? {#section_4437D284448F4313BF953D4B6EDBACA6}

Before a report suite can be selected when defining an Analytics activity, you need both an Analytics user account and a Target user account. Your user accounts must be configured as described in the documentation. See [User Permission Requirements](../../../c-integrating-target-with-mac/a4t/c-account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083) .

Once you are a member of one or more Experience Cloud groups that have access to Analytics and Target and you have access to all report suites, you should see the option to create an A/B test using Analytics under **[!UICONTROL Create Activity]**.

If provisioning issues occur, check whether A4T is provisioned correctly.

## Why are my report suites not loading? {#section_6CC8B2B3568A46C499895EB9811FDC2E}

Check the following if any of these problems occur:

* Make sure your Analytics and Target accounts are linked in the Experience Cloud.
* If you are using multiple Analytics company logins in the same Experience Cloud company, make sure that the last Analytics company you logged in to is the one that is tied to the Target account for the integration.
* If you have been logged in to the Experience Cloud for several hours, sometimes the Analytics session can expire. Log out and log back in to try again.

## Why don't I see Analytics options in Target? {#section_EDD996AFB08B4DB196DD934BE55BF48D}

See "Why are my report suites not loading?" above. The root cause of this problem is the same.

## Why don't I see A4T reports in Analytics? {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

See "Why are my report suites not loading?" above. The root cause of this problem is the same.

## Why are my reports in Target empty? {#section_3837104757464CB488C5A83014A669A1}

See "Why are my report suites not loading?" above. The root cause of this problem is the same.
