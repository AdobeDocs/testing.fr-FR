---
description: This topic contains answers to questions that are frequently asked about
  metric definitions and using Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
seo-description: This topic contains answers to questions that are frequently asked
  about metric definitions and using Analytics as the reporting source for Target
  (A4T).
seo-title: Metric definitions - A4T FAQ
solution: Target
title: Metric definitions - A4T FAQ
topic: Standard
uuid: 41d41665-9057-479d-b0a8-7cffb90ca843
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Metric definitions - A4T FAQ{#metric-definitions-a-t-faq}

This topic contains answers to questions that are frequently asked about metric definitions and using Analytics as the reporting source for Target (A4T).

## What's the expiration for activity membership? How long after visitors enter the activity will their actions be counted in the activity if they don't see it again? {#section_41B4958F33534E4B96DEE0C981227A79}

The default expiration for the activity is 90 days after a visitor's last interaction with the activity. This can be adjusted by ClientCare if needed. This setting is global for all activities, however, so it should not be adjusted for one case.

## Do the advanced options for success metrics in Target work with A4T? {#section_F060E3438F4144258BB95813EDEABDAA}

These options do not currently work with A4T.

## What are calculated metrics and how do they replace the SiteCatalyst:Event mbox I used to use? {#section_D59F4719E6B94758A2187427C17F8EF3}

Calculated metrics let you create custom metrics that are derived from segments or mathematical calculations. In the past, when you might have used the `SiteCatlayst:Event` mbox where `evar27=shoes` and the event is `purchase`, you would now create a segment where `evar27=shoes` and then create a calculated metric where the event is `purchase` with the segment applied. The advantage to this is these metrics can be created at any time, even after the activity is underway. They can then be used on any report in Analytics.

## Does A4T attribute conversions to multiple campaigns? {#section_7F15C727206440CD86B3A8CE77087DF9}

Yes. This is done using the "Full Allocation" setting.
