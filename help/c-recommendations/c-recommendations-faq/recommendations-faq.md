---
keywords: troubleshooting;frequently asked questions;FAQ;FAQs;recommendations;special characters;attribute weighting;content similarity
description: View a list of frequently asked questions and answers about Adobe [!DNL Target] Recommendations activities.
title: Where Can I find Questions and Answers about [!DNL Target] Recommendations?
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
---
# ![PREMIUM](/help/assets/premium.png) Recommendations FAQ

List of frequently asked questions (FAQs) about [!DNL Adobe Target] [!DNL Recommendations] activities.

## Why does [!UICONTROL Catalog Search] not show the correct results when I search on a custom attribute with a numeric value?

When you perform a catalog search on a custom attribute with a numeric value, the results treat the custom attribute to be a string type instead of a numeric value.

Currently, there is no functionality available that allows customers to change the type of an attribute. To make a change, [open a customer issue](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) referencing the attributes that need the type changed from string to numeric.

## How long does it take for updates to items in my catalog to be reflected on my site?

The time frame and results vary, depending on how the items are updated.

|Source|Details|
| --- | --- |
|Item attributes updated via mbox or API|<ul><li>Recommendations are updated within 15 minutes.</li><li>Existing recommendations and item attributes are shown until updates are available.</li><li>Catalog Search is updated after catalog index (3-8 hours).</li></ul>|
|Item attributes updated via feed|<ul><li>Recommendations are updated after feed ingest (2-8 hours).</li><li>Existing recommendations and item attributes are shown until updates are available.</li><li>Catalog Search is updated after feed ingest (2-8 hours) and after subsequent catalog index (3-8 hours). Catalog Search is updated within 5-16 hours total.</li></ul>|
|Item deleted from the catalog via Target UI or API|<ul><li>Recommendations are updated within 15 minutes.</li><li>Existing recommendations and item attributes are shown until updates are available.</li><li>Catalog Search is updated after catalog index (3-8 hours).</li></ul>|
|Item added to the catalog via mbox or API|<ul><li>Recommendations are updated after algorithm run. Algorithm runs are scheduled every 12 hours for 1-2 day algorithms and every 24 hours for 7+ day algorithms.</li><li>Existing recommendations are shown until updates are available if the added item is not a requested key.</li><li>Backup recommendations are shown until updates are available if the added item is a requested key.</li><li>Catalog Search is updated after catalog index (3-8 hours).</li></ul>|
|Item added to the catalog via feed|<ul><li>Recommendations are updated after the feed is ingested (2-8 hours). Subsequent algorithm runs are scheduled every 12 hours for 1-2 day algorithms and every 24 hours for 7+ day algorithms. Recommendations are updated within 2-32 hours total.</li><li>Existing recommendations are shown until updates are available if the added item is not a requested key.</li><li>Backup recommendations are shown until updates are available if the added item is a requested key.</li><li>Catalog Search is updated after feed ingest (2-8 hours) and after catalog index (3-8 hours). Catalog Search is updated within 5-16 hours total.</li></ul>|

After importing a feed file, or after receiving entity updates via API or mbox, the following changes are reflected in under 60 minutes:

* If an item was previously excluded but should now be included, the item will be included on the next algorithm run (12-24 hours).

  This situation occurs because [!DNL Target] applies exclusions both online and offline. When an item is newly excluded, the online exclusion applies quickly. When an item is newly included, the online exclusion goes away quickly but the offline exclusion doesn't go away until the next algorithm run.

* If an item was previously included but should now be excluded, the item is excluded per the "Item attributes updated..." time line discussed above depending on feed source (15 minutes via mbox/API or 12-24 hours via feed).

The following changes are not reflected until the next algorithm run occurs (within 12-24 hrs):

* Item attributes used in the Collection rules used for the activity.
* Item attributes used in a promotion based on an attribute or collection associated with the activity.
* Item category that the item appears in for a "Current Category" or "Favorite Category" in the Top Sellers or Most Viewed algorithm.
* Ranking of recommended items when the attribute changed is a custom attribute that is used as the custom key for an algorithm.
* Ranking of recommended items based on one or more changed attributes when the recommendation logic is "Items with similar attributes," when "Content Similarity" weighting factors are used, or when "Attribute Weighting" factors are used.

>[!NOTE]
>
>A feed file is considered imported when its status changes from "Importing Items" to "Preparing Search Index Updates". Updates can take more than 60 minutes to be reflected in the Catalog Search user interface; Catalog Search is up to date when the feed status changes to "Updates Completed". Even if Catalog Search is not yet up to date, your site reflects updates on the time frames listed above. The most recent Catalog Search index update time is displayed on the Catalog Search page.

## How long does it take for a change to the configuration of my [!UICONTROL Recommendations] activity, offer, promotions, or criteria settings to be reflected on my site?

* A change to the promotion settings can take up to five hours to be reflected onsite.
* A change to other criteria settings might not be reflected until the next algorithm run:

  * Some criteria settings (for example, “addition of a dynamic inclusion rule”) are reflected instantly.
  * Other criteria settings (for example “removal of a dynamic inclusion rule”, change of lookback window, and so forth) can’t be incorporated until the next algorithm run.
  * Algorithm runs are triggered by these changes but can take up to 24 hours to be completed. Algorithms also run on a scheduled basis every 12-24 hours.

## How long does it take for a user’s behavior (for example, clicking product A and buying product B) to be reflected in the recommendations *that* user receives?

*  Currently viewed/purchased product/content influence the recommendations the user receives on the same pageview/Target content request.
* Historical user behavior, such as “last viewed product,” “most viewed product,” and overall viewing/purchasing history is updated with that request and influence the recommendations that user receives on the next pageview/Target content request. For example, “Recently Viewed Items” and “Recommended For You” algorithms update with each product view/purchase and are reflected on the subsequent content request.

## How long does it take for a user’s behavior (for example, clicking product A and buying product B) to be reflected in the recommendations *other* users receive?

The behavior of users in aggregate is incorporated into offline algorithm processing with every algorithm run occurring every 12-24 hours.

## What should I do if special characters are breaking my array? {#section_D27214116EE443638A60887C7D1C534E}

Use escaped values in JavaScript. Quotation marks ( " ) can break the array. The following code snippet is an example of escaped values:

```
#set($String='') 
#set($escaper=$String.class.forName('org.apache.commons.lang.StringEscapeUtils')) 
<script type="text/javascript"> 
console.log("$escaper.escapeJavaScript($entity1.name)") 
console.log("$escaper.escapeJavaScript($entity2.name)") 
console.log('$escaper.escapeJavaScript($entity3.name)') 
names.push("$escaper.escapeJavaScript($entity4.name)") 
</script>
```

## Why aren't all criteria, including custom criteria, available for selection when creating a Recommendations activity? {#section_B2265AC8B8A94E0298D495A05C5D817F}

The available criteria is based on the current category. When you are creating recommendations offers, the algorithm picker displays criteria based on category Id.

If the location on which you're applying this criteria doesn't contain the category Id, certain criteria is not available in the algorithm picker.

If you use a location where category Id is present in the mbox, the criteria picker contains all applicable criteria.

Target has a [Filter Incompatible Criteria](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) setting to control intelligent filtering of the algorithm picker.

>[!NOTE]
>
>This setting applies to activities created in the Visual Experience Composer (VEC) only. This setting does not apply to activities created in the Form-Based Experience Composer (Target does not have location context).

To access the [!UICONTROL Filter Incompatible Criteria] setting, click [!UICONTROL Recommendations] > [!UICONTROL Settings]:

![](assets/recs_settings_filter.png)

If the [!UICONTROL Filter Incompatible Criteria] setting is NOT enabled, Target does not filter algorithms in the Algorithm Picker and all algorithms are displayed.

If the [!UICONTROL Filter Incompatible Criteria] setting is enabled, in VEC activities, Target reads entityId and category Id from the selected location and then displays algorithms based on `currentItem|currentCategory` (if respective values are present on that location). As a result, only compatible algorithms for the selected location are shown in the algorithm picker, by default.

If the [!UICONTROL Filter Incompatible Criteria] setting is enabled, you can still view non-compatible algorithms by deselecting the [!UICONTROL Compatible] checkbox while selecting criteria.

![](assets/compatible_checkbox.png)

The following list contains special cases in which Target does not display the [!UICONTROL Compatible] checkbox:

* Both entityId and category Id are present on the location, then nothing is being filtered. 
* You are using [!DNL mbox.js] version 55 or earlier. 
* No mbox call is being fired from the page (!config.isAutoCreateGlobalMbox && !config.isRegionalMbox) 
* Target parameters are not defined.

## What should I do if a collection in Recommendations goes to zero (0)? {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

Consider the following information if you see a collection go to zero that previously was not at zero:

* You can resave the collection and see if it updates the number. By resaving, the collection reruns all algorithms that are using that collection. 
* Are you looking at the right environment? Go to [!DNL /target/products.html#recsSettings] to double check (as shown below).

  ![](assets/product_catalog.png)

* Is your index up to date? Go t o [!DNL /target/products.html#productSearch] and check how many hours old the index is (for example, “Indexed 3 hours ago”). You can refresh the index as needed. 
* Did you change something in the feed or the data layer that resulted in your entities no longer matching the collection rules? Make sure your CASE matches (case-sensitive). 
* Did your feed run successfully? Did someone change the FTP directory, password, and so forth? 
* Target does its best to make updates to the delivery (on the customer’s page/app) happen as quickly as possible. Yet, Target also has to provide some representation in the UI for the marketer. Target does not delay delivery updates to wait for the UI updates to be in sync. You can use [mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md) to see what is in the system at the time a request comes in.

## What's the difference between general Attribute Weighting and Content Similarity-specific attribute weighting? {#section_FCD96598CBB44B16A4C6C084649928FF}

Attribute weighting exists in two forms: "standard attribute weighting" and "content similarity attribute weighting."

"Standard attribute weighting" applies to most, if not all, criteria types (not just Content Similarity). This type of weighting gives more weight to certain attribute values. In the following example, Nike products get a bump in the output recommendations.

![](assets/attribute_weighting_example.png)

"Content similarity attribute weighting” applies to Content Similarity criteria only.

This type of weighting is more dynamic, and is based on the current “recommendation key” (the currently viewed item). In the following example (brand x 16), if a visitor were viewing Nike sneakers, that visitor is more likely to be recommended other Nike products (not necessarily only sneakers) rather than competitors’ sneakers. If a visitor is viewing Adidas sneakers, that visitor is more likely to be recommended Adidas products.

![](assets/content_similarity_example.png)

## Why is [!DNL Target] sometimes unable to show recommendations? {#section_DB3F40673AED42228E407C05437D99E9}

Target sometimes cannot show recommendations due to the low number of available recommendations.

The number of values generated per criteria is three times the number of entities specified in the design. Runtime filtering (for example, inventory, mbox attribute matching) is applied after the 3x values are generated, so it is possible end up with fewer than 3x values at delivery time. To mitigate this situation, increase the number of entities in the design by hiding other entities.

The following JavaScript can be used at the beginning of the design to increase the number of requested entities. In this example, the requested entity count would be 30 (3x10).

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## What is the size limit of an API call for insert/update products? Can I update 50,000 products in one call using the API instead of a feed? {#section_434FE1F187B7436AA39B7C14C7895168}

Target imposes a 50-MB post limit at the application level; however, that is only when you pass the `application/x-www-form-urlencoded` content type header.

You could certainly try to send 50,000 products in a single call. If it fails, you can break it up into batches. Adobe recommends that customers break their calls into 5,000 or 10,000 product batches to decrease the likelihood of a timeout due to system load.

## Must I specify the mbox name when creating Recommendations criteria, promotions, or template testing rules? {#section_FFA42ABCC5954B48A46526E32A3A88A2}

When creating a Recommendations criteria, promotions, or template testing rule based on an mbox parameter, `mboxParameter` no longer prompts you for `mboxName`. mbox name is now optional. This change lets you use parameters from multiple mboxes or reference a parameter that has not yet been recorded on the edge.

To select the desired parameter:

* While creating a criteria, promotion, or template testing rule, select a parameter name from the list. Start typing the first characters of the desired parameter name, or type the full name of the desired parameter name. 
* If you remember the mbox name, but not the parameter name, use the checkbox to filter on a known mbox passing the desired parameter.

Using either method, there is no link between the mbox and the parameter. The criteria, promotion, or template testing rule works based on parameter across all mboxes that pass that parameter.

If you edit an existing criteria, promotion, or template testing rule, the filtering criteria displays with the mbox name that was supplied during creation.

## Why can't I save my legacy Recommendations activity after defining a new audience? {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

Ensure that the audience has a unique name. If you gave the audience the same name as an existing audience, you cannot save your legacy Recommendations activity (a Recommendations activity created before October 2016).

## What is the maximum size of a CSV file for a feed upload? {#section_20F1AF4839A447B9889B246D6E873538}

There is no hard limit on the number of rows or file size for a feed's CSV file upload. However, as a best practice, Adobe recommends limiting the CSV file size to 1 GB to avoid failures during the file upload process. If the size of the file exceeds 1 GB, it can ideally be split into multiple feed files. The maximum number of custom attribute columns is 100 and custom attributes are limited to 4096 characters. Other limits on the length of required columns are available on the [Target Limitations page](/help/r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1).

## Can I dynamically exclude an entity? {#exclude}

In the query string, you can pass entity IDs for entities that you want to exclude from your recommendations. For example, you can exclude items that are already in the shopping cart.

To enable the exclusion functionality, use the `excludedIds` mbox parameter. This parameter points to a list of comma-separated entity IDs. For example, `mboxCreate(..., "excludedIds=1,2,3,4,5")`. The value is sent when requesting recommendations.

The exclusion is performed for the current Target call only; items are not excluded on subsequent Target calls unless the `excludedIds` value is passed again. To exclude items in the cart from recommendations on every page, continue to pass the `excludedIds` value on every page.

>[!NOTE]
>
>If too many entities are excluded, recommendations behave as if there aren't enough entities to fill the recommendation template.

To exclude `entityIds`, append the `&excludes=${mbox.excludedIds}` token to the offer content url. When the content url is extracted, the required parameters are substituted using current mbox request parameters.

By default, this feature is enabled for newly created recommendations. Existing recommendations must be saved to support Dynamically Excluded entities.

## What does the NO_CONTENT response sometimes returned in the Recommendations content trace mean?

NO_CONTENT is returned when recommendations are unavailable for the requested algorithm and key combination. Generally speaking, this situation occurs when backups are disabled for the algorithm and one or more of the following is also true:

* Results are not yet ready. 

  This situation typically occurs when first saving a newly created activity or after configuration changes are made to the collection, criteria, or promotions used in the activity.
  
* Results are ready, but not yet cached at the nearest edge server, for the requested algorithm/key combination. 

  The request initiates a caching operation, so this issue should resolve itself after a few page reloads and/or a few minutes pass.
  
* Results are ready, but not available for the provided key value.

  This situation typically occurs when requesting recommendations for an item that was added to the catalog after the most recent algorithm run and will resolve itself after the next algorithm run.
  
* Partial template rendering is disabled and not enough results are available to fill the template.

  This situation typically occurs when you have a dynamic inclusion rule, which aggressively filters many items from the possible results. To avoid situation, enable backups and do not apply the inclusion rule to backups, or use the criteria in sequence with a less-aggressively filtered criteria.

## Do recommendations based on recently viewed items persist across multiple devices for a single visitor? {#persist-across-devices}

When a visitor initiates a session, the session ID is tied to a single edge machine and a temporary profile cache is stored on this edge machine. Subsequent requests from the same session read this profile cache, including recently viewed items.

When the session ends (generally, when it expires after 30 minutes of no activity), the session state, including recently viewed items, is then persisted to a more permanent profile storage in the same geographic edge.

Subsequent sessions from different devices are then able to access these recently viewed items as long as the new session is linked to the customer profile via the same Marketing Cloud ID (MCID), Experience Cloud ID (ECID), or CustomerID/mbox3rdPartyId.

If a visitor has two active sessions at the same time, recently viewed items on one device do not update the recently viewed items on the other device, unless the devices are forced to share the session ID. There is a potential workaround for the issue, but [!DNL Target] does not directly support sharing a session ID across multiple devices. The customer must manage this ID sharing themselves.

This behavior still occurs if a visitor is active on one device and then becomes active on the other device a few minutes later. The first device's session does not expire for 30 minutes and there can be up to five minutes of delay before the profile state is written to the permanent state and processed. Allow 35 minutes for the session to expire and the profile to be stored when testing this behavior.

If the visitor does not have two active sessions at the same time, recently viewed items on one device update the recently viewed items on the other device as long as the session has ended. Allow 35 minutes for the session to expire when testing this behavior.
