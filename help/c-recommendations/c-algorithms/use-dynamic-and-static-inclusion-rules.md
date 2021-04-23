---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Learn how to create inclusion rules in Adobe [!DNL Target] Recommendations for criteria and promotions. To achieve better results, add more dynamic or static filtering rules.
title: How Do I Use Dynamic and Static Inclusion Rules in Recommendations?
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
---
# ![PREMIUM](/help/assets/premium.png) Use dynamic and static inclusion rules

Information about creating inclusion rules for criteria and promotions in [!DNL Adobe Target] and adding dynamic or static filtering rules to achieve better results for your recommendations.

The process for creating and using inclusion rules for criteria and promotions is similar, as are the use cases and examples. Both criteria and promotions and the use of inclusion rules are covered in this section.

## Adding Filtering Rules to Criteria {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

While you are [creating criteria](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), click **[!UICONTROL Add Filtering Rule]** under **[!UICONTROL Inclusion Rules]**.

![](assets/inclusion_options_new.png)

The available options vary depending on the selected industry vertical and recommendation key.

## Adding Filtering Rules to Promotions {#section_D59AFB62E2EE423086281CF5D18B1076}

While [creating a promotion](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), select **[!UICONTROL Promote by Attribute]**, then click **[!UICONTROL Add Filtering Rule]**.

![](assets/inclusion_options.png)

## Filter Types {#section_0125F1ED10A84C0EB45325122460EBCD}

The following sections list the types of filtering options for [!UICONTROL Dynamic Filtering] and [!UICONTROL Filter by Value] for both criteria and promotions:

### Dynamic Filtering

Dynamic inclusion rules are more powerful than static inclusion rules and they yield better results and engagement. Consider the following:

* Dynamic inclusion rules deliver recommendations by matching an attribute in a user’s profile parameter or in an mbox call.

  For example, you can create a "Most Popular Criteria" recommendation. From the set of returned recommendations, you can filter out any recommendations (in real time) against an attribute passed when the user accesses a page where the recommendations are displayed.

* Use static rules to limit which items are included in the recommendation (instead of using collections).

* You can create as many dynamic inclusion rules as necessary. The inclusion rules are joined with an AND operator. All rules must be met to include an item in a recommendation.

The following options are available for dynamic filtering:

|Dynamic filtering option|Details|
| --- | --- |
|[Entity Attribute Matching](/help/c-recommendations/c-algorithms/entity-attribute-matching.md)|Filter dynamically by comparing a pool of potential recommendations items to a specific item that the users have interacted with.<br>Use [!UICONTROL Entity Attribute Matching] when you want to show recommendations most likely to appeal to the visitor, such as the visitor's favorite brand.|
|[Profile Attribute Matching](/help/c-recommendations/c-algorithms/profile-attribute-matching.md)|Filter dynamically by comparing items (entities) against a value in the user's profile.<br>Use [!UICONTROL Profile Attribute Matching] when you want to show recommendations that match a value stored in the visitor’s profile, such as size or favorite brand.|
|[Parameter Matching](/help/c-recommendations/c-algorithms/parameter-matching.md)|Filter dynamically by comparing items (entities) against a value in the request (API or mbox).<br>Use [!UICONTROL Parameter Matching] to recommend content that matches the page parameters or the visitor's parameters, such as device dimensions or geo-location.|

### Filter by Value

The following option is available for filtering by value:

|Filtering by value option|Details|
| --- | --- |
|[Static Filter](/help/c-recommendations/c-algorithms/static-value.md)|Manually enter one or more static values to filter.|

## Available operators {#operators}

Dynamic criteria and promotions are much more powerful than static criteria and promotions and yield better results and engagement.

The following examples provide general ideas about how you can use dynamic promotions and exclusions in your marketing efforts:

|Operator|Examples|
| --- | --- |
|Equals<br>(Available with Entity Attribute Matching, Profile Attribute Matching, Parameter Matching, and Static Filter.)|Using the "equals" operator in dynamic promotions, when a visitor is viewing an item on your website (such as a product, article, or movie), you can promote other items from:<ul><li>The same brand</li><li>The same category</li><li>The same category AND from the house brand</li><li>The same store</li></ul>|
|Does Not Equal<br>(Available with Entity Attribute Matching, Profile Attribute Matching, Parameter Matching, and Static Filter.)|Using the "does not equal" operator in dynamic promotions, when a visitor is viewing an item on your website (such as a product, article, or movie), you can promote other items from:<ul><li>A different TV series</li><li>A different genre</li><li>A different product series</li><li>A different style ID</li></ul>|
|Does Not Contain Substring<br>(Available with Entity Attribute Matching, Profile Attribute Matching, Parameter Matching, and Static Filter.)|Using the "does not contain substring" operator, when a visitor is viewing an item on your website (such as a product), you can promote other items that:<ul><li>Title does not contain a swear word</li></ul>|
|Starts With<br>(Available with Entity Attribute Matching, Profile Attribute Matching, Parameter Matching, and Static Filter.)|Using the "starts with" operator, when a visitor is viewing an item on your website (such as a product), you can promote other items that:<ul><li>Product name starts with iPhone</li></ul>|
|Ends With<br>(Available with Entity Attribute Matching, Profile Attribute Matching, Parameter Matching, and Static Filter.)|Using the "ends with" operator, when a visitor is viewing an item on your website (such as a product), you can promote other items that:<ul><li>Content ends with EN, which indicates English language</li></ul>|
|Is Greater Than or Equal To<br>(Available with Entity Attribute Matching, Profile Attribute Matching, Parameter Matching, and Static Filter.)|Using the "is greater than or equal to" operator, when a visitor is viewing an item on your website (such as a product), you can promote other items that:<ul><li>Cost the same or are more expensive</li></ul>|
|Is Less Than or Equal To<br>(Available with Entity Attribute Matching, Profile Attribute Matching, Parameter Matching, and Static Filter.)|Using the "is less than or equal to" operator, when a visitor is viewing an item on your website (such as a product), you can promote other items that:<ul><li>Cost the same or are less expensive</li><li>Exclude items that are less expensive</li></ul>|
|Is Between<br>(Available with Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching.)|Using the "is between" operator in dynamic promotions, when a visitor is viewing an item on your website (such as a product, article, or movie), you can promote other items that are:<ul><li>More expensive</li><li>Less expensive</li><li>Cost plus or minus 30%</li><li>Later episodes in the same season</li><li>Prior books in a series</li></ul>|
|Is Contained In List<br>(Available with Profile Attribute Matching and Parameter Matching.)|Using the "is contained in list" operator in profile attribute matching, when a visitor is viewing an item on your website (such as a product, article, or movie), you can promote other items that are:<ul><li>Available in the visitor's geography</li></ul>**Example**: You want to recommend only items that are available in a visitor's geographic area.<br>Your filter rule might look like:<br>`availableGeographies list contains an item in user.currentGeography`<br>**Note**: When using this operator, a list is expected in the [right side](#caveats) of the rule.|
|Is Not Contained In List<br>(Available with Profile Attribute Matching and Parameter Matching.)|Using the "is not contained in list" operator in profile attribute matching, when a visitor is viewing an item on your website (such as a product, article, or movie), you can exclude other items that are:<ul><li>In the list of the last ten items that the visitor has viewed</li></ul></ul>**Example**: You do not want to promote items that the visitor has recently viewed and has shown no interest in.<br>Your filtering rule might look like:<br>`id is not contained in list user.lastViewedItems`<br>**Note**: When using this operator, a list is expected in the [right side](#caveats) of the rule.|
|List Contains An Item In<br>(Available with Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching.)|Using the "list contains an item in" operator in profile attribute matching, when a visitor is viewing an item on your website (such as a sporting event or concert), you can promote other items that are:<ul><li>Associated with one of the visitor's favorite teams</li></ul>**Example**: You want to recommend games that are associated with one of the visitor's favorite teams.<br>Your filtering rule might look like:<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**Note**: When using this operator, a list is expected in [both sides](#caveats) of the rule.|
|List Does Not Contain An Item In<br>(Available with Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching.)|Using the "list does not contain an item in" operator in parameter attribute matching, when a visitor is viewing an item on your website (such as a product, article, or movie), you can exclude other items that are:<ul><li>Contained in a list of prohibited types</li></ul>**Example**: You want to exclude items that are available to visitors that are adults, such as tobacco and alcohol.<br>Your filtering rule might look like:<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**Note**: When using this operator, a list is expected in [both sides](#caveats) of the rule.|
|List Contains All Items In<br>(Available with Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching.)|Using the "list contains all items in" operator in profile attribute matching, when a visitor is viewing an item on your website (such as a job posting or recipe), you can promote other items that:<ul><li>Include a set of skills</li><li>Include a set of required ingredients</li></ul>**Example 1**: Suppose that a visitor has a set of skills (Java, C++, and HTML). The items in the catalog are jobs with required skills (Java and HTML). You want to ensure that the visitor's profile contains all the required skills before recommending the job to the visitor.<br>Your filtering rule might look like:<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**Example 2**: Suppose that a user has a list of pantry ingredients. The recipe has a list of required ingredients. You want to ensure that the visitor's profile contains all the required ingredients before recommending the recipe to the visitor.<br>Your filtering rule might look like:<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**Note**: When using this operator, a list is expected in [both sides](#caveats) of the rule.|
|List Does Not Contain All Items In<br>(Available with Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching.)|Using the "list does not contain all items in" operator in entity attribute matching, when a visitor is viewing an item on your website (such as sporting event or concert), you can promote other items that:<ul><li>Do not include a set of teams</li></ul>**Example**: Suppose a sporting event includes two teams: the Houston Astros and the Milwaukee Brewers. The visitor's profile indicates that this visitor does not want to view games for these teams. You want to ensure that you do not recommend a game if these teams are playing.<br>Your filtering rule might look like:<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**Note**: When using this operator, a list is expected in [both sides](#caveats) of the rule.|

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

Previously, no results were returned if a value was empty. The "If *x* is Empty" drop-down list lets you choose the appropriate action to perform if the criteria has empty values, as shown in the following illustration:

![](assets/empty_value.png)

To select the desired action, hover over the gear icon (![](assets/icon_gear.png)), then choose the desired action:

| Action | Available For | Details |
|--- |--- |--- |
|[!UICONTROL Ignore this filtering rule]|[!UICONTROL Profile Attribute Matching] and [!UICONTROL Parameter Matching]|This action is the default for [!UICONTROL Profile Attribute Matching] and [!UICONTROL Parameter Matching].<br>This option specifies that the rule is ignored. For example, if there are three filtering rules and the third rule doesn't pass any values, instead of not returning any results, you can simply ignore the third rule with the empty values.|
|[!UICONTROL Do not show any results for this criteria]<br>(Criteria only)|[!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching]|This action is the default for [!UICONTROL Entity Attribute Matching].<br>This action is how [!DNL Target] handled empty values before the addition of this option: no results are shown for this criteria.|
|[!UICONTROL Do not promote any items<br>(Promotions only)]|[!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching]|This action is the default for [!UICONTROL Entity Attribute Matching].<br>This action is how [!DNL Target] handled empty values before the addition of this option: no results are shown for this criteria.|
|[!UICONTROL Use a static value]|[!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching]|If a value is empty, you can choose to use a static value.|

## Caveats {#caveats}

>[!IMPORTANT]
>
>Different data type attributes might not be compatible in dynamic criteria or promotions during runtime with the "equals" and "does not equal" operators. Use [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory], and [!UICONTROL Environment] values wisely on the right-hand side if the left hand side has predefined attributes or custom attributes.

![](assets/left_right.png)

The following table shows effective rules and rules that might not be compatible during runtime:

| Compatible Rules | Potentially Incompatible Rules |
|--- |--- |
|value - is between - 90% and 110% of current item's - salesValue|salesValue - is between - 90% and 110% of current item's - value|
|value - is between - 90% and 110% of current item's - value|clearancePrice - is between - 90% and 110% of current item's - margin|
|margin - is between - 90% and 110% of current item's - margin|storeInventory - equals - current item's - inventory|
|inventory - equals - current item's - inventory||
