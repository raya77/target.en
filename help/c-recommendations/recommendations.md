---
keywords: Recommendations;Recommendations criteria;recommendations algorithms;recommendations activity;criteria;recommendations targeting;recs
description: Learn about Recommendations activities in Adobe [!DNL Target] that automatically display content that might interest your customers based on previous user activity or other algorithms.
title: What is [!DNL Target] Recommendations?
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
---
# ![PREMIUM](/help/assets/premium.png) Recommendations

[!DNL Adobe Target Recommendations] activities automatically display products, services, or content that might interest your visitors based on previous user activity, preferences, or other criteria. [!DNL Target Recommendations] helps direct visitor to relevant items they might otherwise not know about. [!DNL Recommendations] lets you provide your visitors with relevant content at the right time and in the right place.

>[!NOTE]
>
>[!DNL Recommendations] activities are available as part of the [Target Premium solution](/help/c-intro/intro.md#premium). They are not available in [!DNL Target Standard] without a [!DNL Target Premium] license.
>
>If you currently have [!DNL Recommendations Classic], see [Recommendations Classic versus Recommendations Activities in Target Premium](/help/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5) for more information about the two solutions.

[!DNL Recommendations] helps you optimize and customize real-time suggestions across channels, apps, pages, email messages, and other delivery options to increase engagement and conversion while reducing management effort.

[!DNL Recommendations] helps you:

* Create sophisticated criteria (rules) to automate recommendations 
* Automatically display the recommendations by using a few JavaScript snippets 
* Test and optimize the recommendations criteria and designs that display the recommendations 
* Report on the results of your recommendations activities

The following illustration shows recommendations on a web page:

![](assets/velocity_example.png)

A recommendation determines how a product is suggested to a visitor, depending on that visitor's activities on the site. For example:

| Desired Action | Recommendation |
|--- |--- |
|Encourage people who purchase a backpack to consider buying hiking shoes and trekking poles.|Create a recommendation that shows items that are often purchased together, using the "People who bought this also bought that" criteria.|
|Increase the time visitors spend on your media site by recommending media content similar to what they are watching.|Create a recommendation that suggests other videos, using the "People who viewed this viewed that" criteria.|
|Suggest that customers who viewed information about savings plans at your bank also read about IRA accounts.|Show other products people purchased after viewing one product without showing the first product in the recommendations, using the "people who viewed this also bought" criteria.|

For more information about these and other [!DNL Recommendations] criteria, see [Criteria](/help/c-recommendations/c-algorithms/algorithms.md).

## Terms

Before you get started using [!DNL Recommendations], it is helpful to become familiar with some of the terms used in this section. Don't worry if you don't fully understand these terms yet, you'll become more familiar with them as you set up your [!DNL Recommendations] activities.

|Term|Definition|
| --- | --- |
|Activity|Activities in [!DNL Target] let you personalize content to specific audiences and test page designs. [!DNL Recommendations] is just one of the many activity types available in [!DNL Target]. For more information, see [Target activity types](/help/c-activities/target-activities-guide.md).|
|Entities|Entities refer to the items you want to recommend. Entities can be anything such as products, content (articles, slide shows, images, movies, and tv shows), job listings, restaurants, and so forth. For more information, see [Entities](/help/c-recommendations/c-products/products.md).|
|Feeds|Feeds are used to get entities imported into [!DNL Recommendations]. Entities can be sent using CSV files, the Google Product Search feed format, and Adobe Analytics product classifications. For more information, see [Feeds](/help/c-recommendations/c-products/feeds.md).|
|Catalog|Catalogs refer to your entire product set (entities). Your catalog can contain many collections--a way to organize your products in logical buckets. |
|Collection|Collections refer to a set of similar or related items, such as a single product category. However, you can group whichever items into a category that makes sense to your business, such as products in a certain price range or color, or items that are likely to be interesting in a particular geographical area. For more information, see [Collections](/help/c-recommendations/c-products/collections.md).|
|Criteria|Criteria are rules that determine which products to recommend based on a predetermined set of visitor behaviors.<br>A few examples of criteria include: <ul><li>People Who Bought This, Bought That</li><li>People Who Viewed This, Viewed That</li><li>Items with similar attributes</li><li>Last Purchased Item</li><li>Favorite Category</li></ul>  For more information, see [Criteria](/help/c-recommendations/c-algorithms/algorithms.md).|
|Designs|Designs define the appearance of the recommendations in a [!DNL Recommendations] activity, such as a row, column, table, or grid. The illustration at the top of this article shows a 4 x 1 design. For more information, see [Create a design](/help/c-recommendations/c-design-overview/create-design.md).|
|Locations|Locations refer to a specific content area on a webpage, mobile app, or email where you run an activity for personalization and optimization purposes.|
|Audiences|Audiences are groups of similar activity entrants who will see a targeted activity. An audience is group of people with the same characteristics, such as a new visitor, a returning visitor, or returning visitors from the Midwest. The Audience feature allows you to target different content and experiences to specific audiences to optimize your digital marketing by displaying the right messages to the right people at the right time. For more information, see [Audiences](/help/c-target/target.md).|
|Recommendations as an offer|A feature that lets you include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md).|

## Training video: Activity Types ![Overview badge](/help/assets/overview.png)

This video explains the activity types available in [!DNL Target Standard/Premium]. [!DNL Recommendations] is discussed beginning at 7:20.

* Describe the types of activities included in [!DNL Adobe Target] 
* Select the appropriate activity type to achieve your goals 
* Describe the three-step guided workflow that applies to all activity types

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Adobe [!DNL Target] Basics Webinar: Introduction to Recommendations ![Tutorial badge](/help/assets/tutorial.png) {#intro-to-recs}

The *Introduction to Recommendations* webinar includes an in-depth exploration of how to leverage the value of [!DNL Adobe Target Recommendations]. Find out how this [!DNL Target] activity automatically displays products or content that might interest your customers by optimizing real-time suggestions based on previous visits. Further, dive into the [!DNL Target] UI for a step-by-step overview of how to build a [!DNL Recommendations] activity.

[Introduction to Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
