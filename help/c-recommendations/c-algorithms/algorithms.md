---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Learn how to use criteria in Adobe [!DNL Target] [!DNL Recommendations].
title: How Do I Use Criteria in [!DNL Target] Recommendations?
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
---
# ![PREMIUM](/help/assets/premium.png) Criteria

Criteria in [!DNL Adobe Target] [!DNL Recommendations] are rules that determine which products or content to recommend based on a predetermined set of visitor behaviors. Criteria can be based on popular trends, a visitor's current and past behaviors, or similar products and content. You can test multiple recommendation types against each other by adding multiple criteria.

The following sections explain more about criteria keys and the recommendation logic you can use for each key. Click the links for more detailed information.

## Industry Vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

While creating a criteria, you select an industry vertical based on the goals of your recommendations activity.

| Industry Vertical | Goal |
|--- |--- |
|Retail/Ecommerce|Conversion resulting in purchase|
|Lead Generation/B2B/Financial Services|Conversion with no purchase|
|Media/Publishing|Engagement|

Other criteria options change based on the industry vertical you select. You can set your default industry vertical on the **[!UICONTROL Recommendations > Settings]** page or you can specify the industry vertical for each criteria.

## Algorithm Type {#section_885B3BB1B43048A88A8926F6B76FC482}

The algorithm type you select determines the available algorithms. There are several algorithm types, which are represented as criteria cards when you set up a [!DNL Recommendations] activity.

![Criteria page](assets/criteria-page.png)

The following table explains the various algorithm types and their accompanying algorithms.

|Algorithm type|When to use|Available algorithms|
| --- | --- | --- |
|[!UICONTROL Cart-Based]|Make recommendations based on the user's cart contents.|<ul><li>People Who Viewed These, Viewed Those</li><li>People Who Viewed These, Bought Those</li><li>People Who Bought These, Bought Those</li></ul>For more information, see [Cart-Based](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) in *Base the recommendation on a recommendation key*.|
|[!UICONTROL Popularity-Based]|Make recommendations based on the overall popularity of an item across your site or based on the popularity of items within a user's favorite or most-viewed category, brand, genre, and so forth.|<ul><li>Most Viewed Across the Site</li><li>Most Viewed by Category</li><li>Most Viewed by Item Attribute</li><li>Top Sellers Across the Site</li><li>Top Sellers by Category</li><li>Top Sellers by Item Attribute</li><li>Top by Analytics Metric</li></ul>|
|[!UICONTROL Item-Based]|Make recommendations based on finding similar items to an item that the user is currently viewing or has recently viewed.|<ul><li>People Who Viewed This, Viewed That</li><li>People Who Viewed This, Bought That</li><li>People Who Bought This, Bought That</li><li>Items with Similar Attributes</li></ul>|
|[!UICONTROL User-Based]|Make recommendations based on the user's behavior.|<ul><li>Recently Viewed Items</li><li>Recommended for You</li></ul>|
|[!UICONTROL Custom Criteria]|Make recommendations based on a custom file you upload.|<ul><li>Custom Algorithm</li></ul>|

For more information about each algorithm, see [Base the recommendation on a recommendation key](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Using a custom recommendation key {#custom-key}

You can also base recommendations on the value of a custom profile attribute.

>[!NOTE]
>
>Custom profile parameters can be passed to [!DNL Target] through JavaScript, API, or integrations. For more information about custom profile attributes, see [Visitor profiles](/help/c-target/c-visitor-profile/visitor-profile.md).

For example, suppose that you want to display recommended movies based on the movie that a user most recently added to the queue.

1. Click **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Fill in the information in the [Basic Information section](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. In the [Recommended Algorithm](/help/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo) section, select **[!UICONTROL Item Based]** from the **[!UICONTROL Algorithm Type]** list.

1. Select **[!UICONTROL People Who Viewed This, Viewed That]** from the **[!UICONTROL Algorithm]** list.

1. Select your custom profile attribute from the **[!UICONTROL Recommendation Key]** list (for example, [!UICONTROL Last Show Added to Watchlist]).

   ![Create New Criteria dialog box](assets/custom-key1.png)

## Viewing criteria information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

You can view criteria details on a pop-up card by hovering over a card and by clicking the Information icon on a criteria card without opening the criteria.

![Criteria Card hover](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Click the **[!UICONTROL Algorithm Info]** tab to view general information about the selected criteria, including its Name, Descriptions, Industry Vertical, Page Type(s), Recommendation Key, Recommendation Logic, and Algorithm ID.

![Algorithm Info tab](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Click the **[!UICONTROL Algorithm Usage]** tab to view a list of activities that reference the selected criteria. The card lists active, inactive, and draft activities. Click the Live Activities/Inactive Activities/Draft Activities drop-down lists to view the entire list of activities that reference that criteria. You can click the activity link to open the activity for editing.

![Algorithm Usage tab](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>The [!UICONTROL Algorithm Usage] feature is currently supported for Recommendations activities only. This feature is not currently supported for A/B Test, Auto-Allocate, Auto-Target, and Experience Targeting (XT) activities that include [recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md).
