---
description: This topic contains answers to questions that are frequently asked about
  inflated visit and visitor counts when using Analytics as the reporting source for
  Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;inflated;visit;visitor;partial
  hit;orphaned;orphan;partial-hit
seo-description: This topic contains answers to questions that are frequently asked
  about inflated visit and visitor counts when using Analytics as the reporting source
  for Target (A4T).
seo-title: Inflated visit and visitor counts - A4T FAQ
solution: Target
title: Inflated visit and visitor counts - A4T FAQ
topic: Standard
uuid: 5d1b77bb-9053-4533-bd01-d6f53f0751e9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Inflated visit and visitor counts - A4T FAQ{#inflated-visit-and-visitor-counts-a-t-faq}

This topic contains answers to questions that are frequently asked about inflated visit and visitor counts when using Analytics as the reporting source for Target (A4T).

## Why does my Analytics data show visits that have no page views or other variable values? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

When [!DNL Adobe Analytics] is used to measure [!DNL Target] activities (called A4T), [!DNL Analytics] collects additional data that is not available when there is no [!DNL Target] activity on the page. This is because the [!DNL Target] activity fires a call at the top of the page, but [!DNL Analytics] typically fires its data collection calls at the bottom of the page. In the implementation of A4T to date, we included this additional data whenever a [!DNL Target] activity was active.

For more information, see [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## What is a partial-data hit? {#section_59A203E289564576BF6821F96B0B9E11}

A partial-data hit occurs when a [!DNL Target] tag at the top of the page fires but an [!DNL Analytics] tag at the bottom of the page does not fire. There are various reasons why this happens. In the [!DNL A4T] implementation to date, we included partial data about these hits whenever a [!DNL Target] activity was active. Going forward, we will include this additional data only when both the [!DNL Target] and [!DNL Analytics] tags have fired.

For more information, see [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## I can see a spike in visits. How can I tell if I these were caused by partial-data hits? {#section_28506672C6224ED18AC74F6A02F6F811}

You can contact [Adobe Customer Care](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to retrieve a Partial Data report. This information is not available directly in the [!DNL Analytics] UI.

## What are the potential causes of partial-data hits? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Partial-data hits are often the result from improper implementation, such as misaligned report suite IDs. There are also legitimate causes, which include slow pages, page errors, redirect offers in an activity, or outdated library versions.

For more information, see "What Contributes to Partial Data" in [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## I have partial-data hits. What can I do to clean up my data? {#section_CBE778A9D07A469E8FF98F68BACC7124}

You can create a virtual report suite to exclude historical partial data from your reports.

For more information, see "How Can I View Historical Trends Without Partial Data?" in [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Is there anything I can do to prevent my pages from generating partial-data hits? {#section_4B00E7E618444BE98A0798DE98F08B21}

After November 14, 2016, we will include data only when both the [!DNL Target] and [!DNL Analytics] tags have fired. This change is not retroactive. If your historical reports show inflated counts, and you would like to exclude them from your reports, you can create a virtual report suite, as explained in "How Can I View Historical Trends Without Partial Data?" in [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

There are also steps you can perform to minimize partial-data hits. For more information, see "What are the Best Practices to Reduce Partial Data?" in [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## If partial-data-hit data is removed from reporting, aren’t we losing valuable Target or Analytics data? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

Including partial data in [!DNL Analytics] reporting does provide additional information, it also creates inconsistency with historical data from periods when there were no [!DNL Target] activities running. This can cause problems for [!DNL Analytics] users who are analyzing trends over time.

There are steps you can perform to minimize partial-data hits. For more information, see "What are the Best Practices to Reduce Partial Data?" in [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Are there any particular types of Target activities that are more likely to cause partial-data hits? {#section_69837442A9B84366BEFDA4588B31E574}

Redirect offers immediately send a user to a different page, which means the [!DNL Analytics] call does not fire on the first page.
