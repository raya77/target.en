---
keywords: promotions;front promotions;back promotions;promotions type;list of items;promote by attribute;promote a collection
description: Learn how to add promoted items and control their placement in your Adobe [!DNL Target] Recommendations designs. You can add static and dynamic promotions.
title: How Do I Add Promotions in Recommendations Designs?
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
---
# ![PREMIUM](/help/main/assets/premium.png) Add promotions

Add promoted items and control their placement in your [!DNL Adobe Target Recommendations] designs. You can add static and dynamic promotions.

>[!IMPORTANT]
>
>Static and dynamic exclusion rules are powerful features that can help you with your marketing efforts. For detailed information, examples, and use-case scenarios, see [Use dynamic and static inclusion rules](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

When you create a [!DNL Recommendations] activity, you have the option to include promoted items in your [!DNL Recommendations] design. Promotions use available slots in a design and take precedence over criteria results and backup recommendations. For example, if your design has six slots and you use two of them for promotions, four slots are available for items recommended based on criteria.

Promotions are de-duplicated against items recommended by the criteria for your activity, so a given item won't appear twice in a single recommendations tray.

You can promote specific items, dynamically promote items, promote items based on attributes, or promote collections.

![[!UICONTROL Front Promotion] and [!UICONTROL Back Promotion] options in [!DNL Target] UI](assets/add_promotion_toggles.png)

>[!NOTE]
>
>Using promotions changes CSV structure and output. These changes could have an impact on any external processes that involve CSV, such as email.

1. On the **[!UICONTROL Options]** page, click the **[!UICONTROL Front Promotion]** or **[!UICONTROL Back Promotion]** toggle.

   The following illustration shows the [!UICONTROL Front Promotion] toggle in the "On" position.

   ![Add Front Promotion options](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   You can insert promotions both before *and* after your criteria results.

1. Set the number of design slots to use for promoted items.

   You can use up to 20 slots, depending on your [!DNL Recommendations] design. Each slot you use becomes unavailable for recommendations returned based on your criteria.

1. Set a start date and end date for your promoted items.

   If you don't set a start date, the promotion begins immediately. If you don't set an end date the promotion runs indefinitely.

1. Select a **[!UICONTROL Promotion Type]**.

   * Select **[!UICONTROL List of items]** and enter the `entity.id` values, separated by commas, of the specific items you want to promote.

   * Select **[!UICONTROL Promote by attribute]** and add rules to define the attributes of the items you want to promote.

     If you select [!UICONTROL Promote by Attribute], you can create dynamic matches. For more information, see [Use dynamic and static inclusion rules](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Select **[!UICONTROL Promote a collection]** and choose the collection of items you want to promote. 

     You can create new collections to use for promotions. See [Create a collection](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) for more information.

   If you chose **[!UICONTROL List of Items]** as the **[!UICONTROL Promotion Type]**, you can select the **[!UICONTROL Randomize Item Order]** check box, if desired.

   The default sort order for [!UICONTROL List of Items] is based on the order you entered in the [!DNL Target] UI or API. If your list includes more items than the number of slots you set for promotions, the [!UICONTROL Randomize Item Order] option randomizes the promoted items that are displayed in your design. Choosing this option results in [!DNL Target] randomly selecting the items enabled for promotions in the template from the entire promotion set on each hit.

   If your entities do not have an `entity.value` attribute (for example, you do not sell products) you can pass a numeric value into the `entity.value` attribute, such as the publishing date. In this case, promoted items can be promoted based on the most-recent publishing date, in descending order. The `entity.value` attribute is of type double; it does not accept strings.

   If you selected the **[!UICONTROL Promote by Attribute]** or **[!UICONTROL Promote a Collection]** option, the option to randomize the order is not applicable.

   When promoting specific items using the [!UICONTROL Promote by Attribute] or [!UICONTROL Promote a Collection] options, the default order in which items are presented is based on the `entity.value` attribute, in descending numeric order.

   The following table illustrates the differences between these options:

   |Promotion type|Default sort|Backup sort|Dynamic filtering option|
   | --- | --- | --- | --- |
   |[!UICONTROL List of Items]|Order entered in the Target UI/API|Random (when selected via UI/API)|No|
   |[!UICONTROL Promote by Attribute]|`entity.value` (descending order)|No randomization|Yes|
   |[!UICONTROL Promote a Collection]|`entity.value` (descending order)|No randomization|No|

1. Click **[!UICONTROL Save]**.

Promotions are applied to all experiences in the activity.
