---
description: If you use the backup recommendation feature, any recommendation that
  does not have enough recommended items will not display default content. Instead,
  recommendations display the results of the backup algorithm.
keywords: recommendation;backup;back up
seo-description: If you use the backup recommendation feature, any recommendation
  that does not have enough recommended items will not display default content. Instead,
  recommendations display the results of the backup algorithm.
seo-title: Use a backup recommendation
solution: Target
title: Use a backup recommendation
title-outputclass: premium
topic: Premium
uuid: 2910a844-9dd6-4e69-8652-b2215fed1545
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Use a backup recommendation{#use-a-backup-recommendation}

If you use the backup recommendation feature, any recommendation that does not have enough recommended items will not display default content. Instead, recommendations display the results of the backup algorithm.

If you do not use a backup recommendation, if a recommendation does not have enough items to fill the display, the system displays default content to the user.

The backup recommendation feature always uses the top-viewed items on the site to fill in any remaining slots after the algorithm's data is used. For example, your template is configured to show five recommended items, and you're using the *Purchase Affinities* algorithm. However, you only have enough data to fill two of the five slots, so the backup recommendation feature fills the other three spots with top-viewed items.

Backup recommendations are randomly chosen from the top 500 most-viewed products across the entire site. The data time period for backup recommendations is one week.

The 500 most-viewed results are ordered sequentially and then split into buckets of 20. The buckets are served in order, but the results inside each bucket are randomized and returned to the page. If users refresh the page, they are presented with new, randomized results. If the result set from the union of the collection and the filtering rules is smaller than 20, it will randomly select from the collection.

This bucketing process means that backup recommendations are displayed in the following order:

1. Show the 20 most-viewed items, randomized, then
1. Show the next 20 most-viewed items, randomized, then
1. Show the next 20 most-viewed items, randomized,
1. And so forth

Without the bucketing of backup recommendations, it would have been possible to show the 499th most-viewed item, followed by the 200th most-viewed item, followed by the 380th most-viewed item, and so on. The bucketing process ensures that the most viewed items are recommended first.

>[!NOTE] {class="- topic/note "}
>
>If you group your items into catalogs, the backup recommendations generated for each algorithm within the recommendation also uses the catalog, so only items in the catalog are included in the backup recommendation.

Any item that is excluded by global exclusion rules is not served as a backup recommendation.

Backup recommendations are enabled by default and fill in the extra slots in a template with a random selection of the most popular items on the site.

Duplicates are removed from batches of recommendations.

Using backup recommendations is usually part of the discussion with the implementation team during your initial setup. If you want to change the backup recommendation setting after implementation, contact your account manager.

If Enable Partial Design Rendering (see [Content Settings](../../c-recommendations/c-algorithms/t-create-new-algorithm.md#concept_BC16005C7A1E4F1A87E33D16221F4A96)) is not enabled and the template doesn't show, then either the backup recommendation or default content is shown instead.
