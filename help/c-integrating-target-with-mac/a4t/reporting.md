---
keywords: analytics for target;a4t;analytics as the reporting source;analytics
description: Learn how to use Analytics for Target (A4T). A4T provides access to Analytics reports for Target activities that use Analytics metrics and audience segments.
title: How Do I Use Reporting in A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
---
# A4T reporting{#a-t-reporting}

Using [!DNL Adobe Analytics] as your reporting source for [!DNL Adobe Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

 You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Overview {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] also calls [!DNL Analytics] whenever the conversion is made. [!DNL Analytics] adds the conversion as a specific new [!DNL Analytics] event named "Activity Conversion," which is tracked along with other data collected by [!DNL Analytics].

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. The data collected in that first 24 hours is still accurate and is assigned to the right experience.

## Reports in Analytics {#analytics}

In [!DNL Analytics], there are several dimensions and metrics made available after the A4T integration is enabled.

### Dimensions

* [!UICONTROL Analytics for Target] - The parent ID that is passed in through the integration. The format of this dimension is `Activity ID:Experience ID:3rd ID`. The dimensions below are classifications of this dimension.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - can be ignored

### Metrics

* [!UICONTROL Activity Impressions] - Matches the [!UICONTROL Entrants] number in the [!DNL Target] report.
* [!UICONTROL Activity Conversions] - Matches the [!UICONTROL Custom Conversions] number in the [!DNL Target] report.

In [!DNL Analysis Workspace], use the [!UICONTROL Analytics for Target] panel to analyze your [!DNL Target] activities and experiences with lift & confidence. For more information, see [Analytics for Target (A4T) Panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) in the *Analytics Tools Guide*.

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists "unspecified" instead of listing your activities, an update is required to your provisioned account. Please contact Customer Care to resolve this issue.

For detailed information and examples, open the [Analytics & Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Reports in Target {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite. 
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

  Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

  Any numbers that increase are shown as positives in the report, even when an increase is undesired. For example, even though you want a lower bounce rate, the higher bounce rate is shown as the winner with highest lift. Be aware of these and similar metrics, and whether you'd prefer to decrease or increase the numbers, when making decisions based on your reports.

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. You don't have to know exactly what you want to measure beforehand.

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Activity creation {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

During activity creation, you must specify a goal for the activity on the [!UICONTROL Settings] page. This goal becomes the default metric for the report and is always listed as the first option in the metrics selector. You cannot select segments for reporting like you would for a regular Target activity. A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

You can perform offline calculations for A4T, but it requires a step with data exports in [!DNL Analytics].

For more information, see [Performing Offline Calculations for Analytics for Target (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
