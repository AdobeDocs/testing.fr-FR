---
description: This topic contains suggestions for resolving some issues that might
  occur when designing an MVT test.
keywords: Mobile Web Experience Editor
seo-description: This topic contains suggestions for resolving some issues that might
  occur when designing an MVT test.
seo-title: Troubleshoot Multivariate Tests
solution: Target
subtopic: Mobile Viewports
title: Troubleshoot Multivariate Tests
topic: Standard
uuid: 4de03e03-cbbd-4e8f-a1b9-19ba8b2e6951
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Troubleshoot Multivariate Tests{#troubleshoot-multivariate-tests}

This topic contains suggestions for resolving some issues that might occur when designing an MVT test.

* When editing an activity, if you used Analytics-based metrics and the report suite doesn't load (spinner displays), switch the metrics to Target metrics and then switch again to Analytics-based metric. The report suite should now load.
* If make changes to a test that is already running, you might reset the test and its data.

   Target allows you to edit a live activity. Be aware that editing an activity that is in progress could reset the test, so reports might not recognize some of the changes.

   It is safe to make small changes, such as editing existing text or html offers.

   The specific actions that reset experience names and reports are:

   * Adding a new location
   * Deleting a location
   * Adding new offers or deleting offers from an exiting location

