---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report;faq
description: Learn how to interpret the Automated Personalization Summary report in Adobe Target. You can switch to the Automated Segments and Important Attributes reports from this report.
title: How Do I Use the Automated Personalization Summary Reports?
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
---
# ![PREMIUM](/help/main/assets/premium.png) Automated Personalization Summary reports

Specialized summary reports are available to users of [!UICONTROL Automated Personalization] activities in [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] is available as part of the [!DNL Target Premium] solution. It is not included with [!DNL Target Standard] without a [Target Premium license](/help/main/c-intro/intro.md#premium).

1. Click **[!UICONTROL Activities]**, click the desired [!UICONTROL Automated Personalization] activity from the list, then click the **[!UICONTROL Reports]** tab.

   If you have many activities, you can filter the list by selecting [!UICONTROL Automated Personalization] from the [!UICONTROL Type] drop-down list. 

1. (Optional) Click the **[!UICONTROL Download]** icon to download the summary view (for example, comparing Control and Targeted traffic) as broken down by all available success metrics.

[!UICONTROL Automated Personalization] provides the following reports: 

* Activity Level
* Offer Level
* Automated Segments
* Important Attributes

## Activity Level report {#section_6F72FC5C790B4492B3DCECBFFA971337}

The [!UICONTROL Activity Level] report compares the aggregate performance of using an [!UICONTROL Automated Personalization] algorithm to randomly served content (control).

![Activity Level Report](/help/main/c-reports/assets/box_plot_ap.png)

The standard rules of results interpretation for A/B testing still apply, including lift, confidence, trending, duration, and so on. For more information about interpreting results, see [Statistical calculations in A/Bn tests](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Offer Level report {#section_CAA6409879E349C6906E2BE8156D87A1}

The [!UICONTROL Offer Level] report for the Random Forest experience compares the performance of each algorithm-applied offer to the same randomly served offer (Control). Thus, offers should not be compared against each other in this view.

Click the experience algorithm (Random Forest or control) to view the [!UICONTROL Offer Level] report.

![Offer Level report in Adobe Target](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>A clock icon indicates that the algorithm model is still building. A check mark icon indicates that the base algorithm has been established.

Offers can be shown within [reporting groups](/help/main/c-reports/personalization-reports/offer-reporting-groups-in-automated-personalization.md), and these reporting groups can be collapsed and expanded. Click **[!UICONTROL Control]** or **[!UICONTROL Targeted]** in the table to view rolled-up information by reporting groups, rather than by offers.

## Automated Segments

Click the [!UICONTROL Automated Segments] icon. This report shows how different visitors respond differently to the offers/experiences in your AP/AT activity. This report shows how different automated segments defined by Target's personalization models responded to the offers/experiences in the activity.

![Automated segments icon](/help/main/c-reports/assets/icon-automated-sements-ap.png)

For more information, see [Automated Segments report](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Important Attributes

Click the [!UICONTROL Important Attributes] icon. This report shows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. This report shows the top attributes that influenced the model and their relative importance.

![Important attributes icon](/help/main/c-reports/assets/icon-important-attributes-ap.png)

For more information, see [Important Attributes report](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Frequently Asked Questions

### Why are there differences in data between the Activity Level and Offer Level reports?

**[!UICONTROL Activity Level] report**: Visits recorded on the [!UICONTROL Activity Level] report capture the number of visits to the control experience(s) vs. "targeted" traffic. Targeted traffic includes a mix of exploration traffic and personalized traffic.

**Offer Level report**: Impressions recorded on the [!UICONTROL Offer Level] report capture the number of impressions for each offer. Therefore, in an activity with more than one location, the total number of visits recorded in the [!UICONTROL Offer Level] report across all Reporting Groups is equal to the multiple of the number of visits recorded for Control or Targeted traffic in the [!UICONTROL Activity Level] report times the total number of locations in the activity. Impressions of default content occurring in locations where default content was an available option are recorded in the "Default Content" offer group. Impressions of offers that were unassigned to a reporting group are recorded in the "Ungrouped" offer group.

>[!NOTE]
>
>The number of impressions recorded on the [!UICONTROL Offer Level] report might not be an exact integer multiple of the number of visits recorded in the [!UICONTROL Activity Level] report. This is due to minor discrepancies that occur in the capture of reporting data traffic over the internet (typical discrepancy rate is below 5%). Thus, the number of impression will not be an exact multiple when the number of locations available in the activity changed after the activity was activated.
