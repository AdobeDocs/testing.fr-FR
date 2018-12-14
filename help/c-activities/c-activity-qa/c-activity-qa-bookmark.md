---
description: Information to help you use the Target QA bookmarklet to force Target
  to release you from QA mode.
keywords: qa;preview;bookmarklet;preview links
seo-description: Information to help you use the Target QA bookmarklet to force Target
  to release you from QA mode.
seo-title: Activity QA bookmarklet
solution: Target
title: Activity QA bookmarklet
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Activity QA bookmarklet{#activity-qa-bookmarklet}

Information to help you use the Target QA bookmarklet to force Target to release you from QA mode.

Because [QA mode](../../c-activities/c-activity-qa/c-activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) is sticky, after you browse a website in QA mode, your Target session must expire or you need to have Target release you from QA mode before you can view your site like a typical visitor. Use the QA Target bookmarklet to force yourself out of QA mode.

To use the Target QA bookmarklet, drag the following bookmarklet to your browser's Bookmarks Toolbar:

**Bookmarklet:** [Release Adobe Target Activity QA](javascript:(function () {var parts = window.location.href.split('at_preview_token',2); if (parts.length > 1) {window.location.href = parts[0].concat('at_preview_token=');} })();)

The bookmarklet should then appear on the toolbar for re-use.

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value (for example, `https://www.mysite.com/?at_preview_token=`).
