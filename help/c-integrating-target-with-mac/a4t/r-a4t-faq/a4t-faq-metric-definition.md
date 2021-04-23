---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: Find answers to questions about metric definitions and using Analytics for [!DNL Target] (A4T). A4T lets you use Analytics reporting with Adobe [!DNL Target] activities.
title: Where Can I Find Information About Metric Definitions with A4T?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
---
# Metric definitions - A4T FAQ

This topic contains answers to questions that are frequently asked about metric definitions and using [!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T).

## What's the expiration for activity membership? How long after visitors enter the activity are their actions counted in the activity if they don't see it again? {#section_41B4958F33534E4B96DEE0C981227A79}

The default expiration for the activity is 90 days after a visitor's last interaction with the activity. This setting can be adjusted by ClientCare if needed. This setting is global for all activities, however, so it should not be adjusted for one case.

## While configuring my goal metrics, why can't I access the Advanced Settings options? {#adv-settings}

The [!UICONTROL Advanced Settings] options are not available for activities that use [!DNL Analytics] as the reporting source (A4T).

For activities using A4T, the goal metric always uses the "[!UICONTROL Increment Count & Keep User in Activity]" and "[!UICONTROL On Every Impression]" settings. These settings are *not* configurable.

For non-A4T activities, you can use the [Advanced Settings options](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) to manage how you measure success. Options include adding dependencies, choosing whether to keep the user in the activity or remove them, and whether to count the metric once per entrant or on every impression. You access the [!UICONTROL Advanced Settings] options in a non-A4T activity by clicking the vertical ellipses > [!UICONTROL Advanced Settings], as shown below:

![Advanced Settings](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## What are calculated metrics and how do they replace the SiteCatalyst:Event mbox I used to use? {#section_D59F4719E6B94758A2187427C17F8EF3}

Calculated metrics let you create custom metrics that are derived from segments or mathematical calculations. In the past, when you might have used the `SiteCatlayst:Event` mbox where `evar27=shoes` and the event is `purchase`, you would now create a segment where `evar27=shoes` and then create a calculated metric where the event is `purchase` with the segment applied. These metrics can be created at any time, even after the activity is underway. They can then be used on any report in Analytics.

## Does A4T attribute conversions to multiple campaigns? {#section_7F15C727206440CD86B3A8CE77087DF9}

Yes, using the "Full Allocation" setting.
