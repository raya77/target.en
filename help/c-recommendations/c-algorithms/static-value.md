---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Learn how to manually enter one or more static values to filter using inclusion rules in Adobe Target Recommendations.
title: How Do I Filter By Static Values In Recommendations Activities?
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
---
# ![PREMIUM](/help/assets/premium.png) Static Filter

Manually enter one or more static values to filter using inclusion rules in [!DNL Adobe Target] [!DNL Recommendations].

For example, only recommend content with a Motion Picture Association (MPA) rating of "G" or "PG."

You can create as many inclusion rules as necessary. The inclusion rules are joined with an AND operator. All rules must be met to include an item in a recommendation.

>[!NOTE]
>
>If you are familiar with how inclusion rules were configured prior to the Target 17.6.1 release (June 2017), you'll notice that some of the options and operators have changed. Only those operators applicable to the selected option display and some operators were renamed ("matches" is now "equals") to be more consistent and intuitive. All existing exclusion rules created prior to this release were automatically migrated into the new structure. No restructuring is necessary on your part.

## Recommend content rated G or PG

To create an inclusion rule with static values to recommend content with an MPA rating of "G" or "PG" only (exclude "R" and "NC17" content), you could create the following filtering rules "movie-rating equals g-rated" and "movie-rating equal pg-rated", as shown below.

![movie-rating example](/help/c-recommendations/c-algorithms/assets/movies.png)
