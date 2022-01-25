---
keywords: audience;audience rules;combine audiences;exclusion;add exclusion;exclude;combining audiences;adhoc audience;ad hoc audience
description: Learn how to combine multiple audiences (including Adobe Experience Cloud audiences and [!DNL Target] audiences) on the fly to create ad hoc audiences.
title: Can I Combine Multiple Audiences to Create a New Audience?
feature: Audiences
exl-id: 1d9bff9c-f63b-4e15-9809-71b046158b71
---
# Combine multiple audiences

Combine multiple audiences (including [!DNL Adobe Experience Cloud], [!DNL Adobe Experience Platform], and [!DNL Target] audiences) on the fly to create ad hoc audiences. You can also create exclusion rules and exclude audiences from a rule.

>[!NOTE]
>
>The [!DNL Adobe Experience Platform] source is available to all [!DNL Target] customers using the [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). Audiences available from the [!DNL Adobe Experience Platform] can be used as is or combined with existing audiences, as explained in this topic).

Suppose that you have a "New Visitors" audience and a "Chrome Users" audience. For a specific activity, you might want to combine these existing audiences to target new visitors using Chrome browsers. Instead of creating a third audience and storing it in the [!UICONTROL Audiences] library, you can combine these two audiences during activity creation or while editing an existing activity.

As another example, you can target all loyalty customers. For example, you can include a specific [!DNL Audience Manager] audience for loyalty status and combine it with a [!DNL Target] audience made up of people who signed up for your loyalty program during the current session. Combining these two audiences is easier than creating a third, permanent audience.

You can combine up to ten audiences using AND and OR operators.

You can create and use combined audiences in various places throughout the [!DNL Target] UI.

## Create a combined audience while creating an activity {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

You can create an ad hoc combined audience on the activity's [!UICONTROL Target] page during the three-step guided workflow.

1. While creating an [activity](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Targeting]** page, click the three vertical ellipses, then click **[!UICONTROL Replace Audience]**.

   ![Step Result](assets/edit_audience.png)

1. On the [!UICONTROL Choose Audience] page, select the check boxes next to the desired audiences that you want to use as building blocks for your combined audience.

   Click the [!UICONTROL Filters] button to narrow your search for the desired audience. You can filter audiences by their source: [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud], [!DNL Adobe Experience Platform]. 

   ![Step Result](assets/combine_multiple_audiences1.png)

1. Click **[!UICONTROL Combine Audiences]** in the top-right corner.

   ![Step Result](assets/combine_multiple_audiences2.png)

1. (Conditional) Edit the new combined audience as desired.

   The [!UICONTROL Edit Audience] dialog box lets you drag and drop additional audience building blocks from the left side into the new combined audience. You can also add exclusion rules and exclude audiences.

    1. Use drag-and-drop functionality to add audiences within an existing section as a level 2 building block.

       For example, suppose in the previous example, you now want to include Safari users in the combined audience. Search for and drag the "Safari Browser" audience into the "Firefox Browser" box on the right side, as in the following example:

       ![](assets/combine_multiple_audiences3.png)

       Notice that the operator between the two browser-type audiences is "AND." Select the And drop-down list and change it to "OR" to create a new combined audience for new visitors using either Firefox or Safari. Be careful to avoid creating rules that exclude all potential audience members. For example, it is not possible for someone to visit a page using Firefox and Safari simultaneously.

       >[!NOTE]
       >
       >The operator (AND or OR) must remain the same as you combine audiences. You cannot mix & match operators.

    1. To add an exclusion to a rule, click **[!UICONTROL Exclude]**.

       ![](assets/combine_multiple_audiences3a.png)

       Drag and drop an audience.

       For example, to exclude United States visitors from new visitors, you could drag the Market: United States audience into the box.

       This combined audience includes all new visitors to your site (excluding those from San Francisco) using Safari or Firefox. 
    
    1. To exclude an audience from a rule, click **[!UICONTROL Exclusion]** > **[!UICONTROL Exclude this Audience.]**.

       For example, you could create a combined audience that includes all new visitors to your site, excluding those using Firefox. Excluding visitors using Firefox is easier and quicker than creating a combined audience that explicitly includes multiple browsers (Safari, Chrome, and Internet Explorer), but does not include Firefox.

1. Provide a descriptive name for the combined audience, then click **[!UICONTROL Done]**.

## Create a combined audience for use in metric targeting {#section_A42E795AFCBD4575809C5942039910F0}

You can create an ad hoc combined audience on the activity's [!UICONTROL Goals & Settings] page to use in metric targeting. For example to create targeting based on conversion using a combined audience:

1. While editing or creating an [activity](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Goals & Settings]** page, select **[!UICONTROL Conversion]** for the success metric, then select **[!UICONTROL Viewed an Mbox]** as the action. 
1. Select the desired mbox in the **[!UICONTROL Search mbox]** field.

   ![](assets/combine_multiple_audiences4.png)

1. Click the gear icon, then click **[!UICONTROL Add Audience Targeting]**. 
1. Click the **[!UICONTROL Add Audience/Targeting Condition]** link to display the [!UICONTROL Choose Audience] dialog box.

   ![](assets/combine_multiple_audiences5.png)

1. Proceed with [Step 2](/help/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under "Create a Combined Audience While Creating an Activity" to create the combined audience.

## Create a combined audience for use in reporting {#section_4682D342EFBB43C38E54B99B3A1E14CD}

You can create an ad hoc combined audience on the activity's [!UICONTROL Goals & Settings] page to use in reporting.

1. While editing or creating an [activity](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Goals & Settings]** page, click the **[!UICONTROL Add Audience]** icon under [!UICONTROL Audiences for Reporting] to display the [!UICONTROL Choose Audience] page.

   ![](assets/combine_multiple_audiences6.png)

1. Proceed with [Step 2](/help/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under "Create a Combined Audience While Creating an Activity" to create the combined audience.

## Create a combined audience while editing an activity {#section_364A12CE96E04B61B7C18113AA586C2C}

You can create an ad hoc combined audience while editing an existing activity.

1. From the [!UICONTROL Activities] page, hover over the desired activity, then click the **[!UICONTROL Edit]** icon.

   Or

   Click the desired activity to open it, then click **[!UICONTROL Edit Activity]**. 

1. Click the **[!UICONTROL Configure]** > **[!UICONTROL Audiences]** > **[!UICONTROL Multiple Audiences]**.

   ![Configure > Audiences > Multiple Audiences](assets/combine_multiple_audiences7.png)

1. Click the more options icon (three vertical ellipses) next to the activity's current audience, then click **[!UICONTROL Change Audience]**.

   ![Change Audience](assets/combine_multiple_audiences8.png)

1. Proceed with [Step 2](/help/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) under "Create a Combined Audience While Creating an Activity" to create the combined audience.
