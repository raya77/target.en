---
keywords: audience;propensity;profile attribute;compare;comparison;create audience;creating audience
description: Learn how to define an audience to compare two profile attributes.
title: Can I Compare Two Profile Attributes for Use in Audiences?
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
---
# Create a profile attribute comparison audience

Define an audience in [!DNL Adobe Target] to compare two profile attributes for your [Audience library](/help/c-target/c-audiences/audiences.md) or in an [activity-only audience](/help/c-target/creating-activity-only-audience.md). Using operators, such as greater than, less than, or equal to, define an audience to dynamically compare the values of two different profile attributes.

>[!NOTE]
>
>This functionality is available for the [[!UICONTROL Visitor Profile]](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E) category only.

## Overview {#section_303CBC78194D49A2A004945D425441E1}

Audiences are defined by rules that determine who is included or excluded from a [!DNL Target] activity. An audience definition can include multiple rules, and each rule can include multiple parameters. If one of the rules you include uses the [!UICONTROL Visitor Profile] category, you can define a rule based on a visitor profile attribute’s specific value or compare the value of that attribute to another visitor profile attribute.

For example, let’s assume you work for a furniture company and uploaded two customer propensity scores into [!DNL Target]:

* Likelihood to buy dining room furniture in the next 90 days 
* Likelihood to buy living room furniture in the next 90 days

You could create an audience defined as the propensity to buy dining room furniture is greater than the propensity to buy living room furniture. [!DNL Target] would then dynamically compare the dining room and living room propensity scores for a specific visitor to determine if that visitor qualifies for this audience.

For more information, see [Methods to get Data into Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17).

## Create a profile attribute comparison audience {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Name the audience and add an optional description. 
1. Drag and drop **[!UICONTROL Visitor Profile]** into the audience builder pane.
1. From the **[!UICONTROL Visitor Profile]** drop-down list, choose an attribute:

   ![Propensity Score 1](assets/propensity_score_1.png)

1. Choose your Evaluator:

   ![Propensity Score 2](assets/propensity_score_2.png)

1. From the **[!UICONTROL Choose Comparison Type]** drop-down list, choose **[!UICONTROL Attribute]**.

   The "static value" comparison type lets you compare your visitor profile attribute to specific values.

   ![Propensity Score 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >If you are using one of the default visitor profile categories (for example, New Visitor or Returning Visitor), you can choose only the static value option. The dynamic comparison options are not available for default categories. Other examples where the dynamic comparison options are not available include "First page of session," "Not in other tests," "Not first page of session," and "Category Affinity."

1. Choose the additional attribute you want to compare to your initial attribute.

   ![](assets/propensity_score_4.png)

1. Click **[!UICONTROL Done]**.

## Training video ![Overview badge](/help/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Watch the following video for more information and a scenario in which you could use this feature:

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
