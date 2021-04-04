---
keywords: recommendation;backup;back up
description: Learn how to use backup recommendations in Adobe Target Recommendations. Recommendation that do not have enough recommended items displays the results of the backup algorithm.
title: How Do I Use a Backup Recommendation in Recommendations?
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
---
# ![PREMIUM](/help/assets/premium.png) Use a backup recommendation{#use-a-backup-recommendation}

If you use the backup recommendation feature in Adobe Target, any recommendation that does not have enough recommended items will not display default content. Instead, recommendations display the results of the backup algorithm.

If you do not use a backup recommendation, if a recommendation does not have enough items to fill the display, the system displays default content to the user.

>[!NOTE]
>
>Additional information is included in the [Content section of the Create criteria](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content) topic, including a matrix that explains the results you'll observe when using the [!UICONTROL Partial Design Rendering] and [!UICONTROL Show Backup Recommendations] options together or separately.

The backup recommendation feature always uses the top-viewed items on the site to fill in any remaining slots after the algorithm's data is used. For example, your template is configured to show five recommended items, and you're using the *Purchase Affinities* algorithm. However, you only have enough data to fill two of the five slots, so the backup recommendation feature fills the other three spots with top-viewed items.

Backup recommendations are randomly chosen from the top 500 most-viewed products across the entire site. The data time period for backup recommendations is one week.

The 500 most-viewed results are ordered sequentially and then split into buckets of 20. The buckets are served in order, but the results inside each bucket are randomized and returned to the page. If users refresh the page, they are presented with new, randomized results. If the result set from the union of the collection and the filtering rules is smaller than 20, it will randomly select from the collection.

This bucketing process means that backup recommendations are displayed in the following order:

1. Show the 20 most-viewed items, randomized, then 
1. Show the next 20 most-viewed items, randomized, then 
1. Show the next 20 most-viewed items, randomized, 
1. And so forth

Without the bucketing of backup recommendations, it would have been possible to show the 499th most-viewed item, followed by the 200th most-viewed item, followed by the 380th most-viewed item, and so on. The bucketing process ensures that the most viewed items are recommended first.

>[!NOTE]
>
>If you group your items into catalogs, the backup recommendations generated for each algorithm within the recommendation also uses the catalog, so only items in the catalog are included in the backup recommendation.

Any item that is excluded by global exclusion rules is not served as a backup recommendation.

Backup recommendations are enabled by default and fill in the extra slots in a template with a random selection of the most popular items on the site.

Duplicates are removed from batches of recommendations.

Using backup recommendations is usually part of the discussion with the implementation team during your initial setup. If you want to change the backup recommendation setting after implementation, contact your account manager.

If Enable Partial Design Rendering (see [Content Settings](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)) is not enabled and the template doesn't show, then either the backup recommendation or default content is shown instead.
