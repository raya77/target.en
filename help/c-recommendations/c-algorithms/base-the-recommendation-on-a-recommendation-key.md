---
keywords: recommendation key;recommendation logic;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: Learn how to use recommendations based on keys that use visitor behavior context to show relevant results in Adobe [!DNL Target] Recommendations activities.
title: How Do I Base the Recommendation on a Recommendation Key?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
---
# Base the recommendation on a recommendation key

Recommendations based on algorithms use visitor behavior context to show relevant results in [!DNL Adobe Target] [!DNL Recommendations] activities. 

There are five algorithm types in [!DNL Target Recommendations]:

* [!UICONTROL Cart-Based]
* [!UICONTROL Popularity-Based]
* [!UICONTROL Item-Based]
* [!UICONTROL User-Based]
* [!UICONTROL Custom Criteria]

Each algorithm type provides different algorithms appropriate for its type, as shown in the following table:

|Algorithm type|When to use|Available algorithms|
| --- | --- | --- |
|[!UICONTROL Cart-Based]|(Coming Soon) Make recommendations based on the user's cart contents.|<ul><li>People Who Viewed These, Viewed Those</li><li>People Who Viewed These, Bought Those</li><li>People Who Bought These, Bought Those</li></ul>|
|[!UICONTROL Popularity-Based]|Make recommendations based on the overall popularity of an item across your site or based on the popularity of items within a user's favorite or most-viewed category, brand, genre, and so forth.|<ul><li>Most Viewed Across the Site</li><li>Most Viewed by Category</li><li>Most Viewed by Item Attribute</li><li>Top Sellers Across the Site</li><li>Top Sellers by Category</li><li>Top Sellers by Item Attribute</li><li>Top by Analytics Metric</li></ul>|
|[!UICONTROL Item-Based]|Make recommendations based on finding similar items to an item that the user is currently viewing or has recently viewed.|<ul><li>People Who Viewed This, Viewed That</li><li>People Who Viewed This, Bought That</li><li>People Who Bought This, Bought That</li><li>Items with Similar Attributes</li></ul>|
|[!UICONTROL User-Based]|Make recommendations based on the user's behavior.|<ul><li>Recently Viewed Items</li><li>Recommended for You</li></ul>|
|[!UICONTROL Custom Criteria]|Make recommendations based on a custom file you upload.|<ul><li>Custom Algorithm</li></ul>|

Each criteria is defined in its own tab. Traffic is split evenly across your different criteria tests. In other words, if you have two criteria, traffic is divided equally between them. If you have two criteria and two designs, traffic is split evenly between the four combinations. You can also specify a percentage of site visitors who see the default content, for comparison. In that case, the specified percentage of visitors sees the default content, and the rest are split between your criteria and design combinations. 

For more information about creating criteria and defining its algorithm types and algorithms, see [Create criteria](/help/c-recommendations/c-algorithms/create-new-algorithm.md). 

Different recommendations algorithms lend themselves to placement on different types of pages. Refer to the following sections for more information about each algorithm type and its available algorithms.

## Cart-Based {#cart-based}

The [!UICONTROL Cart-Based] algorithm type lets recommend items based on the contents of the visitor’s current cart.

Cart-based recommendation logic is similar to the "[!UICONTROL Recommended For You]"  user-based algorithm and to the "[!UICONTROL People Who Viewed These, Bought Those]" and "[!UICONTROL People Who Bought These, Bought Those]" item-based algorithms. 

[!DNL Target] uses collaborative filtering techniques to determine similarities for each item in the visitor's cart, then combines these behavioral similarities across each item to get a merged list. 

[!DNL Target] also gives marketers the choice of looking at visitor behavior within a single session or across multiple sessions:

* **[!UICONTROL Single Session]**: Based on what other visitors did within a single session.

  Looking at behavior within a single session might make sense when there's a sense that products strongly "go with" each other based on a usage, occasion, or event. For example, a visitor is buying a printer and might also need ink and paper. Or, a visitor is buying peanut butter and might also need bread and jelly.

* **[!UICONTROL Across Sessions]**: Based on what other visitors did across multiple sessions.

  Looking at behavior across multiple sessions might make sense when there's a sense that products strongly "go with" each other based on visitor preference or taste. For example, a visitor likes Star Wars and might also like Indiana Jones, even if the visitor doesn't necessarily want to watch both movies in the same sitting. Or, a visitor likes the board game "Codenames" and might also like the board game "Avalon," even if the visitor cannot play both games simultaneously. 

[!DNL Target] makes recommendations for each visitor based on the items in their current cart, regardless whether you look at visitor behavior within a single session or across multiple sessions.

The following algorithms are available with the [!UICONTROL Cart-Based] algorithm type:

### [!UICONTROL People Who Viewed This, Viewed Those]

Recommends items that are most often viewed in the same session that the specified item is viewed.

This logic returns other products people viewed after viewing this one; the specified product is not included in the results set.

This logic lets you create additional conversion opportunities by recommending items that other visitors who viewed an item also viewed. For example, visitors who view road bikes on your site might also look at bike helmets, cycling kits, locks, and so forth. You can create a recommendation using this logic that suggests other products help you increase revenue.

If you select this algorithm, you can select the following Recommendations Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

### People Who Viewed This, Bought Those

Recommends items that are most often purchased in the same session that the specified item is viewed. This criteria returns other products people purchased after viewing this one, the specified product is not included in the results set.

This logic returns other products people purchased after viewing this one; the specified product is not included in the results set.

This logic lets you increase cross-selling opportunities by displaying a recommendation on a product page, for example, that displays items that other visitors who viewed the item purchased. For example if the visitor is viewing a fishing pole, the recommendation could show additional items other visitors purchased, such as tackle boxes, waders, and fishing lures. As visitors browse your site, you provide them with additional purchasing recommendations.

If you select this algorithm, you can select the following Recommendations Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

### People Who Bought This, Bought That Those

Recommends items that are most often purchased by customers at the same time as the specified item.

This logic returns other products people purchased after buying this one; the specified product is not included in the results set.

This logic lets you increase cross-selling opportunities by displaying a recommendation on a shopping cart summary page, for example, that displays items that other buyers also purchased. For example if the visitor is purchasing a suit, the recommendation could display additional items other visitors purchased along with the suit, such as ties, dress shoes, and cufflinks. As visitors review their purchases, you provide them with additional recommendations.

If you select this algorithm, you can select the following Recommendations Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

## [!UICONTROL Popularity-Based]

The [!UICONTROL Popularity-Based] algorithm type lets you make recommendations based on the overall popularity of an item across your site or based on the popularity of items within a user's favorite or most-viewed category, brand, genre, and so forth.

The following algorithms are available with the [!UICONTROL Popularity-Based] algorithm type:

### Most Viewed Across the Site {#most-viewed}

The recommendation is determined by the item that has been viewed most often. This is determined by recency/frequency criteria that works as follows:

* 10 points for first product view
* 5 points for every subsequent view
* At end of session divide all values by 2

For example, viewing surfboardA then surfboardB in one session results in A: 10, B: 5. When the session ends, you have A: 5, B: 2.5. If you view the same items in the next session, the values change to A: 15 B: 7.5.

Use this algorithm on general pages, such as home or landing pages and offsite ads.

### Most Viewed by Category {#most-viewed-category}

The recommendation is determined by the category that has received the most activity, using the same method used for "most viewed item" except that categories are scored instead of products.

This is determined by recency/frequency criteria that works as follows:

* 10 points for first category view
* 5 points for every subsequent view

Categories visited for the first time are given 10 points. 5 points are given for subsequent visits to the same category. With each visit, non-current categories that have been viewed before are decremented by 1.

For example, viewing categoryA then categoryB in one session results in A: 9, B: 10. If you view the same items in the next session, the values change to A: 20 B: 9.

Use this algorithm on general pages, such as home or landing pages and offsite ads.

If you select the Most Viewed by Category algorithm, you can select the following Recommendations Keys:

* Current Category
* Favorite Category

### Most Viewed by Item Attribute

(Info coming soon)

### Top Sellers Across the Site {#top-sellers}

Displays the items that are included in the most completed orders from across the site. Multiple units of the same item in a single order are counted as one order.

This algorithm lets you create recommendations for top-selling items on your site to increase conversion and revenue. This logic is especially suited for first-time visitors to your site.

### Top Sellers by Category

Displays the items that are included in the most completed orders by category. Multiple units of the same item in a single order are counted as one order.

This algorithm lets you create recommendations for top-selling items on your site based on category to increase conversion and revenue. This logic is especially suited for first-time visitors to your site.

If you select the Most Viewed by Category algorithm, you can select the following Recommendations Keys:

* Current Category
* Favorite Category

### Top Sellers by Item Attribute

(Info coming soon)

### Top by Analytics Metric

(Info coming soon)

## [!UICONTROL Item-Based]

The [!UICONTROL Item-Based] recommendation type lets you make recommendations based on finding similar items to an item that the user is currently viewing or has recently viewed.

The following algorithms are available with the [!UICONTROL Item-Based] algorithm type:

### People Who Viewed This, Viewed That {#viewed-viewed}

Recommends items that are most often viewed in the same session that the specified item is viewed.

This logic returns other products people viewed after viewing this one; the specified product is not included in the results set.

This logic lets you create additional conversion opportunities by recommending items that other visitors who viewed an item also viewed. For example, visitors who view road bikes on your site might also look at bike helmets, cycling kits, locks, and so forth. You can create a recommendation using this logic that suggests other products help you increase revenue.

If you select this algorithm, you can select the following Recommendations Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

### People Who Viewed This, Bought That {#viewed-bought}

Recommends items that are most often purchased in the same session that the specified item is viewed. This criteria returns other products people purchased after viewing this one, the specified product is not included in the results set.

This logic returns other products people purchased after viewing this one; the specified product is not included in the results set.

This logic lets you increase cross-selling opportunities by displaying a recommendation on a product page, for example, that displays items that other visitors who viewed the item purchased. For example if the visitor is viewing a fishing pole, the recommendation could show additional items other visitors purchased, such as tackle boxes, waders, and fishing lures. As visitors browse your site, you provide them with additional purchasing recommendations.

If you select this algorithm, you can select the following Recommendations Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

### People Who Bought This, Bought That {#bought-bought}

Recommends items that are most often purchased by customers at the same time as the specified item.

This logic returns other products people purchased after buying this one; the specified product is not included in the results set.

This logic lets you increase cross-selling opportunities by displaying a recommendation on a shopping cart summary page, for example, that displays items that other buyers also purchased. For example if the visitor is purchasing a suit, the recommendation could display additional items other visitors purchased along with the suit, such as ties, dress shoes, and cufflinks. As visitors review their purchases, you provide them with additional recommendations.

If you select this algorithm, you can select the following Recommendations Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

### Items with Similar Attributes {#similar-attributes}

Recommends items or media similar to items or media based on current page activity or past visitor behavior.

If you select Items/Media with Similar Attributes, you have the option to set content similarity rules.

Using content similarity to generate recommendations is especially effective for new items, which are not likely to show up in recommendations using People Who Viewed This, Viewed That, and other logic based on past behavior. You can also use content similarity to generate useful recommendations for new visitors, who have no past purchases or other historical data.

If you select this algorithm, you can select the following Recommendations Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

For more information, see [Content Similarity](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL User-Based]

The User-Based algorithm type lets you make recommendations based on the user's behavior.

The following algorithms are available with the [!UICONTROL User-Based] algorithm type:

### Recently Viewed Items {#recently-viewed}

Uses the visitor's history (spanning sessions) to present the last *x* items the visitor has viewed, based on the number of slots in the design.

The Recently Viewed Items algorithm returns result specific to a given [environment](/help/administrating-target/hosts.md). If two sites belong to different environments and a visitor switches between the two sites, each site shows only recently viewed items from the appropriate site. If two sites are in the same environment and a visitor switches between the two sites, the visitor sees the same recently viewed items for both sites.

>[!NOTE]
>
>You cannot use the [!UICONTROL Recently Viewed Items] criteria for backup recommendations.

[!UICONTROL Recently Viewed Items]/Media can be filtered so that only items with a particular attribute are displayed.

* Recently Viewed criteria are configurable, like other criteria in recommendations.
* You can use [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), and [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (including the special rules for Price and Inventory) in the same way as any other criteria.

Possible use-cases include, a multi-national company with multiple businesses might have a visitor view items across multiple digital properties. In this case, you can limit the recently viewed items to display only for the respective property where it was viewed. This prevents recently viewed items from displaying on another digital property's site.

Use this algorithm on general pages, such as home or landing pages and offsite ads.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] respects both exclusions global settings and the selected collection setting for the activity. If an item is excluded by a global exclusion, or is not contained in the selected collection, it will not be displayed. Therefore, when using a [!UICONTROL Recently Viewed Items] criteria, the "All Collections" setting should generally be used.

### Recommended for You {#recommended-for-you}

Recommends items based off each visitor's browsing, viewing, and purchasing history.

This algorithm lets you deliver personalized content and experiences to both new and returning visitors. The list of recommendations is weighted towards the visitor's most-recent activity and is updated in-session and become more personalized as the user browses your site.

Both views and purchases are used to determine the recommended items. The specified recommendation key (for example, Current Item) is used to apply any inclusion rule filters you select. 

For example, you can:

* Exclude items that don't meet certain criteria (products out of stock, articles published more than 30 days ago, movies rated R, and so forth).
* Limit included items to a single category or to the current category.

If you select this algorithm, you can select the following Filtering Keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item

## Custom Criteria {#custom}

The Custom Criteria algorithm type lets you make recommendations based on a custom file you upload.

Recommendation is determined by an item that is stored in a visitor's profile, using either user.*x* or profile.*x* attributes.

When this option is selected, the `entity.id` value must be present in the profile attribute.

When you base recommendations on custom attributes, you must select the custom attribute and then select the recommendation type.

You can perform real-time filtering on top of your own custom criteria output. For example, you can limit your recommended items to only those from a visitor's favorite category or brand. This gives you the power to combine off-line calculations with real-time filtering.

This functionality means that you can use [!DNL Target] to add personalization on top of your offline calculated recommendations or custom-curated lists. This combines the power of your data scientists and research with Adobe's tried-and-true delivery, run-time filtering, A/B testing, targeting, reporting, integrations, and more.

With the addition of inclusion rules on Custom criteria, this turns otherwise static recommendations into dynamic recommendations based a visitor's interests.

* Custom criteria are configurable, like other criteria in recommendations.
* You can use [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), and [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (including the special rules for Price and Inventory) in the same way as any other criteria.

Possible use-cases include:

* You want to recommend movies from a custom-curated list, but only if the visitor hasn't already watched them.
* You want to run an offline algorithm and use the results to power your recommendations, but you must ensure that out-of-stock items are never recommended.
* You want to include only items that are from this visitor's favorite category.

## Recommendation keys

The following recommendation keys are available from the [!UICONTROL Recommendation Key] drop-down list:

### Current Item {#current-item}

The recommendation is determined by the item the visitor is currently viewing. 

Recommendations display other items that might interest visitors who are interested in the specified item.

When this option is selected, the `entity.id` value must be passed as a parameter in the display mbox.

Can be used with the following algorithms:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Use the [!UICONTROL Current Item] recommendations key on your site on:

* Single-item pages, such as product pages.
* Do NOT use on null search results pages.

### Last Purchased Item {#last-purchased}

The recommendation is determined by the last item that was purchased by each unique visitor. This is captured automatically, so no values must be passed on the page.

Can be used with the following algorithms:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Use the [!UICONTROL Last Purchased Item] recommendations key on your site on:

* Home page, My Account page, offsite ads.
* Do NOT use on product pages or pages relevant to purchases.

#### Custom recommendations key

You can base recommendations on the value of a custom profile attribute. For example, suppose that you want to display recommended movies based on the movie that a visitor most recently added to his or her queue.

1. Select your custom profile attribute from the **[!UICONTROL Recommendation Key]** drop-down list (for example, “Last Show Added to Watchlist”).
1. Then select your **[!UICONTROL Recommendation Logic]** (for example "People Who Viewed This, Viewed That").

   ![Create new criteria dialog box](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

If your custom profile attribute doesn't directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur. For example, suppose that you want to display the top selling items from a visitor’s favorite brand.

1. Select your custom profile attribute from the **[!UICONTROL Recommendation Key]** drop-down list (for example, “Favorite Brand”).

1. Then select the **[!UICONTROL Recommendation Logic]** you want to use with this key (for example, "Top Sellers").

   The [!UICONTROL Group By Unique Value Of] option displays. 

1. Select the entity attribute that matches to the key you’ve chosen. In this case “Favorite Brand” matches to `entity.brand`.

   [!DNL Recommendations] now produces a “Top Sellers” list for each brand and shows the visitor the appropriate “Top Sellers” list based on the value stored in the visitor's Favorite Brand profile attribute.

   ![Create new criteria dialog box 2](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Last Viewed Item {#last-viewed}

The recommendation is determined by the last item that was viewed by each unique visitor. This is captured automatically, so no values must be passed on the page.

Can be used with the following algorithms:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Use the [!UICONTROL Last Viewed Item] recommendations key on your site on:

* Home page, My Account page, offsite ads.
* Do NOT use on product pages or pages relevant to purchases.

### Most Viewed Item {#most-viewed-logic}

Displays the items or media that are viewed most often on your site.

This logic lets you display recommendations based on the most-viewed items on your site to increase conversions for other items. For example, a media site could display recommendations on its home page for its most-viewed videos to encourage visitors to watch additional videos.

This recommendation key can be used with the following algorithms:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

### Current Category {#current-category}

The recommendation is determined by the product category that the visitor is currently viewing.

Recommendations display items in the specified product category.

When this option is selected, the `entity.categoryId` value must be passed as a parameter to the display mbox.

This recommendation key can be used with the following algorithms:

* Top Sellers
* Most Viewed

Use the [!UICONTROL Current Category] recommendations key on your site on:

* Single-category pages.
* Do NOT use on null search results pages.

### Favorite Category {#favorite-category}

The recommendation is determined by the visitor's favorite product category.

Recommendations display items in the specified product category.

When this option is selected, the `entity.categoryId` value must be passed as a parameter to the display mbox.

This recommendation key can be used with the following algorithms:

* Top Sellers
* Most Viewed

Use the [!UICONTROL Current Category] recommendations key on your site on:

* Single-category pages.
* Do NOT use on null search results pages.

### Site Affinity {#site-affinity}

Recommends items based on the certainty of a relationship between items. You can configure this criteria to determine how much data is required before a recommendation is presented using the Inclusion Rules slider. For example, if you select very strong, the products with the strongest certainty of a match are recommended.

For example, if you set a very strong affinity and your design includes five items, three of which meet the strength of connection threshold, the two items that do not meet the minimum strength requirements are not displayed in your recommendations and are replaced by your defined backup items. The items with the strongest affinity display first.

For example, an online retailer can recommend items in subsequent visits that a visitor has shown interest in during past sessions. Activity for each visitor's session is captured to calculate an affinity based on a recency and frequency model. As this visitor returns to your site, site affinity is used to display recommendations based on past actions on your site.

Some customers with diverse product collections and diverse site behaviors might get the best results if they set a weak site affinity.

This logic can be used with the following recommendation keys:

* Current Item
* Last Purchased Item
* Last Viewed Item
* Most Viewed Item
