---
keywords: criteria;algorithm;industry vertical;page type;recommendation key;recommendation logic;logic;data range;lookback window;behavior data source;partial design;backup recommendations;inclusion rules;attribute weighting;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: Learn how to create criteria that controls the content of your Adobe Recommendations activities to show the recommendations that are most appropriate for your activity.
title: How Do I Create Criteria in Recommendations?
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
---
# ![PREMIUM](/help/assets/premium.png) Create criteria

Criteria in [!UICONTROL Adobe Target] [!UICONTROL Recommendations] control the content of your [!UICONTROL Recommendations] activities. Create criteria to show the recommendations that are most appropriate for your activity. These criteria use the visitor's actions to determine which content or products to display.

The following sections explain how to create a new criteria.

## Access the Create New Criteria screen

There are multiple ways to reach the [!UICONTROL Create New Criteria] screen. Some screen options vary depending on how you reach the screen.

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Criteria you create here are automatically made available for all [!DNL Recommendations] activities.
* When you are creating a [!DNL Recommendations] activity using the [!UICONTROL Visual Experience Composer] (VEC), you are immediately taken to the [!UICONTROL Select Criteria] screen after you select an element on your page and click [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before], or [!UICONTROL Insert Recommendations After]. You can then select an available criteria or you can click **[!UICONTROL Create Criteria]**. If you create a new criteria, you have the option to save your criteria for use with other [!DNL Recommendations] activities. For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* When you are editing a [!DNL Recommendations] activity, click in a [!UICONTROL Recommendations Location] box on your page, and select **[!UICONTROL Change Criteria]**. On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. You will have the option to save your new criteria for use with other [!DNL Recommendations] activities.

The following steps assume you access the [!UICONTROL Create New Criteria] screen by using the first method: the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen.

1. Click **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

   ![Create New Criteria](assets/CreateNewCriteria_full-new.png)

1. Configure the information in the following sections.

## [!UICONTROL Basic Information] {#info}

1. Type a **[!UICONTROL Criteria Name]**.

   This is the "internal" name used to describe the criteria. For example, you might want to call your criteria "Highest margin products," but you don't want that title to display publicly. See the next step to set the public-facing title.

   ![Basic Information section](assets/basic-information.png)

1. Type a public-facing **[!UICONTROL Display Title]** to appear on the page for any recommendations that use this criteria.

   For example, you might want to display "People who viewed this viewed that" or "Similar products" when you use this criteria to show recommendations.

1. Type a short **[!UICONTROL Description]** of the criteria.

   The description should help you identify the criteria and might include information about the purpose of the criteria.

1. Select an industry vertical based on the goals of your recommendations activity.

   | Industry Vertical | Goal |
   |--- |--- |
   |Retail/Ecommerce|Conversion resulting in purchase|
   |Lead Generation/B2B/Financial Services|Conversion with no purchase|
   |Media/Publishing|Engagement|

   Other criteria options will change based on the industry vertical you select. 

1. Select a **[!UICONTROL Page Type]**.

   You can select multiple page types.

   Together, the industry vertical and page types are used to categorize your saved criteria, making it easier to reuse criteria for other [!DNL Recommendations] activities.

## [!UICONTROL Recommendations Algorithm] {#rec-algo}

1. Select an **[!UICONTROL Algorithm Type]** and **[!UICONTROL Algorithm]**:

   ![Recommended Algorithm section](assets/recommended-algorithm.png)

   |Algorithm type|When to use|Available algorithms|
   | --- | --- | --- |
   |[!UICONTROL Popularity-Based]|Make recommendations based on the overall popularity of an item across your site or based on the popularity of items within a user's favorite or most-viewed category, brand, genre, and so forth.|<ul><li>Most Viewed Across the Site</li><li>Most Viewed by Category</li><li>Most Viewed by Item Attribute</li><li>Top Sellers Across the Site</li><li>Top Sellers by Category</li><li>Top Sellers by Item Attribute</li><li>Top by Analytics Metric</li></ul>|
   |[!UICONTROL Item-Based]|Make recommendations based on finding similar items to an item that the user is currently viewing or has recently viewed.|<ul><li>People Who Viewed This, Viewed That</li><li>People Who Viewed This, Bought That</li><li>People Who Bought This, Bought That</li><li>Items with Similar Attributes</li></ul>|
   |[!UICONTROL User-Based]|Make recommendations based on the user's behavior.|<ul><li>Recently Viewed Items</li><li>Recommended for You</li></ul>|
   |Cart-Based|(Coming Soon) Make recommendations based on the user's cart contents.|<ul><li>People Who Viewed These, Viewed Those</li><li>People Who Viewed These, Bought Those</li><li>People Who Bought These, Bought Those</li></ul>|
   |[!UICONTROL Custom Criteria]|Make recommendations based on a custom file you upload.|<ul><li>Custom Algorithm</li></ul>|


   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

1.  As required, select an **Item Attribute** and **Profile Attribute to Match**, a **Recommendation Key**, **Filtering Key**, and/or **Analytics Metric** to configure the algorithm.

For more information about choosing a Recommendation Key, see [Base the recommendation on a recommendation key](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Data Source] {#data-source}

1. Select the desired **[!UICONTROL Behavioral Data Source]**: [!UICONTROL Adobe Target] or [!UICONTROL Analytics].

   >[!NOTE]
   >
   >The [!UICONTROL Behavioral Data Source] section displays only if your implementation uses [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Behavioral Data Source section](assets/data-source.png)

   If you chose [!UICONTROL Analytics], select the desired report suite.

   If the criteria uses [!DNL Adobe Analytics] as the behavioral data source, once created, the time for criteria availability depends on whether the selected report suite and lookback window has been used for any other criteria, as explained below:

   * **One-time report suite setup**: The first time a report suite is used with a given data range lookback window, [!DNL Target Recommendations] can take from two to seven days to fully download the behavioral data for the selected report suite from [!DNL Analytics]. This time frame is dependent on the [!DNL Analytics] system load.
   * **New or edited criteria using an already available report suite**: When creating a new criteria or editing an existing criteria, if the selected report suite has already been used with [!DNL Target Recommendations], with a data range equal to or lesser than the selected data range, then the data is immediately available and no one-time setup is required. In this case, or if an algorithm's settings are edited while not modifying the selected report suite or data range, the algorithm runs or re-runs within 12 hours.
   * **Ongoing algorithm runs**: Data flows from [!DNL Analytics] to [!DNL Target Recommendations] on a daily basis. For example, for the [!UICONTROL Viewed Affinity] recommendation, when a user views a product, a product-view tracking call is passed into [!DNL Analytics] close to real-time. The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in less than 12 hours.

   For more information, see [Use Adobe Analytics with Target Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Set the **[!UICONTROL Lookback Window]** to determine the time range of available historical user behavior data to use when determining which recommendations to show. This option is available for all algorithms with the exception of Items with Similar Attributes and Custom Algorithms.

   ![Lookback Window slider](assets/data-range.png)

   If your site has a lot of traffic and behaviors change frequently, choose a shorter data window. A shorter window enables [!DNL Recommendations] to be more responsive to changes in the market and in your business. For example, a shorter window means that [!DNL Recommendations] will detect changes in visitor behavior as your visitors begin seasonal shopping, such as back-to-school shopping or Christmas, and will recommend items appropriate to those shopping seasons.

   If you don't have a lot of data, or visitor behavior does not change frequently, you might select a longer window. However, for many sites, a shorter window results in higher-quality recommendations.

   The available data ranges are:

   |Lookback Window option|Updated frequency (displayed on hover)|Supported alogrithms|
   | --- | --- | --- |
   |Six hours|Algorithm runs every 3-6 hours|[!UICONTROL Popularity-Based] algorithms when the selected [!UICONTROL Behavioral Data Source] is [!DNL Adobe Target]|
   |One day|Algorithm runs every 12-24 hours|[!UICONTROL Popularity-Based] algorithms|
   |Two days|Algorithm runs every 12-24 hours|<ul><li>[!UICONTROL Popularity-Based] algorithms</li><li>[!UICONTROL Item-Based] algorithms</li><li>[!UICONTROL User-Based] algorithms</li><li>[!UICONTROL Cart-Based] algorithms</li></ul>|
   |One week|Algorithm runs every 24-48 hours|<ul><li>[!UICONTROL Popularity-Based] algorithms</li><li>[!UICONTROL Item-Based] algorithms</li><li>[!UICONTROL User-Based] algorithms</li><li>[!UICONTROL Cart-Based] algorithms</li></ul>|
   |Two weeks|Algorithm runs every 24-48 hours|<ul><li>[!UICONTROL Popularity-Based] algorithms</li><li>[!UICONTROL Item-Based] algorithms</li><li>All [!UICONTROL User-Based] algorithms</li><li>[!UICONTROL Cart-Based] algorithms</li></ul>|
   |One month (30 days)|Algorithm runs every 24-48 hours|<ul><li>[!UICONTROL Popularity-Based] algorithms</li><li>[!UICONTROL Item-Based] algorithms</li><li>[!UICONTROL User-Based] algorithms</li><li>[!UICONTROL Cart-Based] algorithms</li></ul>|
   |Two months (61 days)|Algorithm runs every 24-48 hours|<ul><li>[!UICONTROL Popularity-Based] algorithms</li><li>[!UICONTROL Item-Based] algorithms</li><li>[!UICONTROL User-Based] algorithms</li><li>[!UICONTROL Cart-Based] algorithms</li></ul>|

## [!UICONTROL Backup Content] {#content}

[!UICONTROL Backup Content] rules determine what happens if the number of recommended items does not fill your [recommendations design](/help/c-recommendations/c-design-overview/design-overview.md). It is possible for [!DNL Recommendations] criteria to return fewer recommendations than your design calls for. As an example, if your design has slots for four items, but your criteria causes only two items to be recommended, you can leave the remaining slots empty, you can use backup recommendations to fill the extra slots, or you can choose to display no recommendations.

![Content section](assets/content.png)

1. (Optional) Slide the **[!UICONTROL Partial Design Rendering]** toggle to the "on" position.

   As many slots as possible will be filled but the design template might include blank space for remaining slots. If this option is disabled and there is not enough content to fill all available slots, recommendations are not served and default content is displayed instead. 

   Enable this option if you want recommendations served with blank slots. Use backup recommendations if you want recommendation slots to be filled with content based on your criteria with empty slots filled with similar or popular content from your site, as explained in the next step.

1. (Optional) Slide the **[!UICONTROL Show Backup Content]** toggle to the "on" position.

   Fill any remaining empty slots in the design with a random selection of most-viewed products from across your site.

   Using backup recommendations ensures that your recommendation design fill all available slots. Suppose that you have a 4 x 1 design, as illustrated below:

   ![4 x 1 design](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Suppose your criteria causes only two items to be recommended. If you enable the [!UICONTROL Partial Design Rendering] option, the fist two slots are filled, but the remaining two slots remain empty. However, if you enable the [!UICONTROL Show Backup Recommendations] option, the first two slots are filled based on your specified criteria and the remaining two slots are filled based on your backup recommendations.

   The following matrix shows the result you'll observe when using the [!UICONTROL Partial Design Rendering] and [!UICONTROL Backup Content] options:

   | Partial Design Rendering | Backup Content | Result |
   |--- |--- |--- |
   |Disabled|Disabled|If fewer recommendations are returned than the design calls for, the recommendations design is replaced by default content and no recommendations are displayed.|
   |Enabled|Disabled|The design is rendered, but may include blank space if fewer recommendations are returned than the design calls for.|
   |Enabled|Enabled|Backup recommendations will fill available design "slots," fully rendering the design.<br>If applying inclusion rules to backup recommendations restricts the number of qualifying backup recommendations to the point that the design cannot be filled, the design is partially rendered.<br>If the criteria does not return any recommendations, and inclusion rules restrict backup recommendations to zero, the design is replaced with default content.|
   |Disabled|Enabled|Backup recommendations will fill available design "slots," fully rendering the design.<br>If applying inclusion rules to backup recommendations restricts the number of qualifying backup recommendations to the point that the design cannot be filled, the design is replaced by default content and no recommendations are displayed.|

   For more information, see [Use a backup recommendation](/help/c-recommendations/c-algorithms/backup-recs.md).

1. (Conditional) If you selected **[!UICONTROL Show Backup Content]** in the previous step, you can enable **[!UICONTROL Apply inclusion rules to backup recommendations]**.

   Inclusion rules determine which items are included in your recommendations. The options available depend on your industry vertical.

   For more details, see [Specify inclusion rules](#inclusion) below.

1. (Optional) Slide the **[!UICONTROL Recommend Previously Purchased Items]** toggle to the "on" position.

   This setting is based on the `productPurchasedId`. The default behavior is to not recommend previously purchased items. In most cases you do not want to promote items a customer has recently purchased. It is useful if you sell items that people typically purchase only once, such as kayaks. If you sell items that people come back to purchase again on a repeated basis, such as shampoo or other personal items, you should enable this option.

## Content Similarity {#similarity}

Use [!UICONTROL Content Similarity] rules to make recommendations based on item or media attributes.

>[!NOTE]
>
>If you selected **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]** as your Algorithm Type and Algorithm, you have the option to set content similarity rules.

Content similarity compares item attribute keywords and makes recommendations based on how many keywords different items have in common. Recommendations based on content similarity do not require past data to deliver strong results. 

Using content similarity to generate recommendations is especially effective for new items, which are not likely to show up in recommendations using *People Who Viewed This, Viewed That* and other logic based on past behavior. You can also use content similarity to generate useful recommendations for new visitors, who have no past purchases or other historical data. 

When you select **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]**, you have the option to create rules to increase or decrease the importance of specific item attributes in determining recommendations. For items such as books, you might want to boost the importance of attributes like *genre*, *author*, *series*, and so on, to recommend similar books.

![](assets/ContentSimilarity.png)

Because content similarity uses keywords to compare items, some attributes, such as *message* or *description*, can introduce "noise" into the comparison. You can create rules to ignore these attributes. 

By default, all attributes are set to *Baseline*. You do not need to create a rule unless you want to change this setting.

>[!NOTE]
>
>The content similarity algorithm might use random sampling in computing similarity between items. As a result, similarity ratings between items might vary between algorithm runs.

## Inclusion Rules {#inclusion}

Several options help you narrow the items that display in your recommendations. You can use inclusion rules while creating criteria or promotions. 

![Inclusion rules](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Inclusion rules are optional; however, setting these details gives you more control over the items that appear in your recommendations. Each detail you configure further narrows the display criteria. 

For example, you can choose to display only women's shoes that have an inventory of more than 50 and a price between $25 and $45. You can also weight each attribute so those items that are more important to your business are most likely to appear. 

As another example, you can choose to display job openings to visitors who visit your site only from certain cities and who have the required college degrees. 

Inclusion rule options vary by industry vertical. By default, inclusion rules are applied to backup recommendations.

>[!IMPORTANT]
>
>You should use inclusion rules cautiously. They are useful if, for example, your organization has rules that demand that one brand is not recommended while another brand is being shown. However, there is an opportunity cost to this feature. You could possibly lose a percentage of lift by restricting some items from not showing when they would normally be shown by the activity criteria. 

The inclusion rules are joined with an AND. All rules must be met to include an item in a recommendation. 

To create a simple inclusion rule, as mentioned previously, to display only women's shoes that have an inventory of more than 50 and a price between $25 and $45, perform the following steps: 

1. Set a price range for the products you want to recommend.
1. Set the minimum inventory amount for the products you want to recommend.
1. Configure the recommendation to display items only when they meet certain criteria.

   ![](assets/Recs_InclusionRules.png)

   You can specify that items are included only when one of the attributes in the list meets or does not match one or more specified conditions. 

   The available evaluators depend on the value you choose in the first drop-down. You can list multiple items. These items are evaluated with OR. 

   Multiple rules are combined with an AND.

   >[!NOTE]
   >
   >This option limits the items that are displayed in the recommendation. It does not affect which pages the recommendation is displayed on. To limit where the recommendation displays, select the pages in the experience composer. 

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Attribute Weighting {#weighting}

You can add multiple rules to "nudge" the algorithm based on important information or metadata about the content catalog so that certain items are more likely to be shown. 

For example, you can apply a higher weighting to on-sale items so they appear more often in the recommendation. Non-sale items are not completely excluded, but they appear less often. Multiple weighted attributes can be applied to the same algorithm, and the weighted attributes can be tested on split traffic in the recommendation. 

1. Choose a value.

   The value determines the type of item that is more likely to display, based on one of several available criteria. 

1. Choose an evaluator.

1. Type the keyword to complete the rule attributes.

   For example, the complete rule might be "Category contains substring shoes." 

   ![](assets/Recs_AttributeWeighting.png)

1. Select the weight to assign to the rule.

   Options range from 0 to 100 in increments of 25. 
   
1. Add additional rules if desired.

When finished, click **[!UICONTROL Save]**.

If you are creating a new [!UICONTROL Recommendations] activity or editing an existing one, the **[!UICONTROL Save criteria for later]** check box is selected by default. If you do not want to use the criteria in other activities, clear the check box before saving.

## Training video: Create criteria in Recommendations (12:33) ![Tutorial badge](/help/assets/tutorial.png)

This video contains the following information:

* Create criteria
* Create criteria sequences
* Upload custom criteria

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
