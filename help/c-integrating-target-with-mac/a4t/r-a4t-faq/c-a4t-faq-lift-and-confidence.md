---
description: This topic contains answers to questions that are frequently asked about
  lift and confidence when using Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report
  builder;confidence
seo-description: This topic contains answers to questions that are frequently asked
  about lift and confidence when using Analytics as the reporting source for Target
  (A4T).
seo-title: Lift and confidence - A4T FAQ
solution: Target
title: Lift and confidence - A4T FAQ
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Lift and confidence - A4T FAQ{#lift-and-confidence-a-t-faq}

This topic contains answers to questions that are frequently asked about lift and confidence when using Analytics as the reporting source for Target (A4T).

## Can I perform offline calculations for A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

You can perform offline calculations for A4T, but it requires a step with data exports in [!DNL Analytics]. For more information, see "Performing Offline Calculations for Analytics for Target (A4T)" in [Confidence Level and Confidence Interval](../../../c-reports/c-conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## How is lift calculated? {#section_8CAE788EED5646C4B1D64A0D22070734}

Lift is the percent difference between your control page results and a successful test variant.

## How is confidence calculated? {#section_97DB24D833E742988318CA65DA65DAD9}

The confidence level is the probability that the measured conversion rate differs from the champion page conversion rate for reasons other than chance alone.

## Why can't I see lift and confidence on calculated metrics? {#section_D3E44E24782A409DBD88AE4D1595CB58}

Lift and confidence can't currently be generated for calculated metrics. However, in most cases, this should not be a problem because lift is normalized by the normalization metric. For example, if you select lift for orders and the normalization metric is visits, lift is calculate on the ratio of the two, which is conversion rate.

## How does A4T handle confidence calculations? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T uses non-binary metric calculations with the sum of square data. The variance is calculated using the sum of squares data. Extreme orders are not taken into account.

Any Analytics segment can be applied to the report. That is how you can get the "extreme order" among other segment options. A metric could also be built to limit things like how many times a visitor converted.

## Do lift and confidence work in Ad Hoc and Report Builder? If it's not native, can I do it in there myself? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

Lift and confidence do not work in Ad Hoc or Report Builder, and cannot be calculated yourself for continuous variables. It is possible to calculate it manually for binary metrics.
