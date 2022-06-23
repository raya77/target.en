---
keywords: collection;Targeting
description: Learn how to use collections in Adobe [!DNL Target] Recommendations. A collection is a set of products or items that are eligible for a recommendation.
title: How Do I Use Collections in Recommendations Activities?
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
---
# ![PREMIUM](/help/main/assets/premium.png) Collections 

A collection is a set of products or items that are eligible for a recommendation. A collection is defined by specifying the conditions that must be met by items to be part of it.

Commonly, a collection is a set of similar or related items, such as a single product collection. However, you can group whichever items into a category that makes sense to your business, such as products in a certain price range or color or items that are likely to be interesting in a particular geographical area.

Use collections to organize your products in logical buckets. For example, if some items are available in one region but not another, you can create a collection that excludes items that are unavailable in the visitor's region. You can also use collections to organize seasonal items, or any other organizational parameters that apply to your business.

The [backup recommendations](/help/main/c-recommendations/c-algorithms/backup-recs.md) generated for each criteria within the recommendation also uses this collection, so only items in the collection are included in the backup recommendation. With collections, you can be sure that only products that make sense to show in a location are displayed.

Collections are rebuilt or updated every time each criteria runs.

You can group your items into catalogs, then create separate recommendations for each collection.

Inclusion criteria allow you to do similar things as a collection, but they must be set up every time you create an activity. Collections allow you to create a set of items one time, then use it whenever it is appropriate to do so without having to set it up again.

When you are creating or editing a [!DNL Recommendations] activity, the collection name appears next to the [!UICONTROL Criteria] label on the activity diagram.

>[!NOTE]
>
>Collections are not applied when using the [!UICONTROL Recently Viewed Items] recommendation key.

## Create a Collection {#task_1256DFF6842141FCAADD9E1428EF7F08}

Create a collection to organize the products or content you want to show in your recommendations.

1. Click **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** to display the list of existing collections.

   ![Collections list](assets/collections_list.png)

   The [!UICONTROL Collections] page displays a list of your existing collections. You create new collections by clicking the [!UICONTROL Create Collection] button. You can also edit, copy, and delete existing collections by hovering over the desired collection and clicking the desired icon.

   ![Hover icons: edit, copy, and delete](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   The "Number of Items" reported for each collection on the [!UICONTROL Collections] list view is the number of products matching the rules for that collection within the configured default Recommendations [host group](/help/main/administrating-target/hosts.md) (environment). See [Settings](https://developer.adobe.com/target/implement/recommendations/){target=_blank} to change the default host group.

1. Click **[!UICONTROL Create Collection]**.

1. (Conditional) Choose an environment from the **[!UICONTROL Environment]** filter while creating (or updating) a collection to preview the contents of the collection in that environment. By default, results from the default host group are displayed.

   ![Create Collection](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. Type a **[!UICONTROL Name]** for the collection.

   You can also enter an optional **[!UICONTROL Description]**.

1. Set the rules used to build the collection.

   For example, your collection might be built around a product ID or category, margin, or any other parameter in the list.

   You can add rules to use multiple parameters to define a collection. Multiple rules are joined with an AND operator. All specified rules must be matched for the collection to apply.

1. Click **[!UICONTROL Save]**.

## Create a collection using Advanced Search

You can also create collections using Advanced Search on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The Advanced Search functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned.

## Edit, copy, or delete a collection

Hover over the desired collection in the list, then click the appropriate icon: edit, copy, or delete.

![Hover icons for an collection](/help/main/c-recommendations/c-products/assets/hover-collections.png)

You can copy an existing collection to create a duplicate collection that you can then modify. This lets you create a similar exclusion with less effort.

Be aware that collections are available across the entire account. Ensure that you consider this before deleting a collection. Deleted collections cannot be recovered.

## Use a collection in a Recommendations activity

1. Create a collection by using one of the methods mentioned above.

1. Click **[!UICONTROL Activities]** and [create a new Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) activity or edit an existing activity.

1. After you select a criteria and design, the [!UICONTROL Options] page displays were you select the desired collection.

   ![Choose collection option](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Conditional) To change an existing collection setting, on the **[!UICONTROL Experiences]** page (step 2 of the three-part guided workflow), click a location where you placed recommendations, click **[!UICONTROL Change Collection]**, then select the desired collection.

   ![Change Collection option](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Training video: Create collections and exclusions in Recommendations (7:05) ![Tutorial badge](/help/main/assets/tutorial.png)

This video contains the following information:

* Create a collection
* Create an exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)
