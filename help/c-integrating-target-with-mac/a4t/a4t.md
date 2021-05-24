---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target;atjs;at.js;adobe experience platform web sdk;platform web sdk;platform sdk
description: Use [!DNL Analytics] for [!DNL Target] (A4T) to create activities based on [!DNL Analytics] conversion metrics and audience segments and use [!DNL Analytics] reports to examine results.
title: What is [!DNL Analytics] for [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
---
# [!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) is a cross-solution integration that lets you create activities based on [!DNL Analytics] conversion metrics and audience segments. The A4T integration lets you use [!DNL Analytics] reports to examine your results. If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics] data collection.

>[!NOTE]
>
>A4T support in an [!DNL Adobe Experience Platform Web SDK] implementation discussed in this article is scheduled to be available with the [!DNL Platform Web SDK] version 2.5.0 release (June 1, 2021).

## Overview {#section_92B66069210C40DBA937790E8CC596CF}

The [!DNL Analytics for Target] integration between [!DNL Analytics] and [!DNL Target] provides powerful analysis and timesaving tools for your optimization program.

The three primary benefits of using [!DNL Analytics] data in [!DNL Target] are:

* Marketers can dynamically apply [!DNL Analytics] success metrics or reporting segments to [!DNL Target] activity reports at any time. It is not required to specify everything before running the activity. 
* A single source of data eliminates the variance that occurs when collecting data in two separate systems. 
* Your existing [!DNL Analytics] implementation collects all required data. There is no need to implement mboxes on pages for the sole purpose of collecting data for reports.

If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics].

All [!DNL Analytics] metrics, including calculated metrics, are available in [!DNL Target] and the [!UICONTROL Target Activities] report in [!DNL Analytics], with one exception. The calculated metrics for [!UICONTROL Lift & Confidence] are not supported. Likewise, any segment available in [!DNL Analytics] can be applied to both solutions. You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the activity has completed.

Every metric is included, including any custom or calculated metrics that are built-in in [!DNL Analytics].

After the classification period, data appears in these reports approximately an hour after it is collected from the website. All metrics, segments, and values in the reports come from the report suite you selected when you set up the activity.

Keep the following points in mind when considering using A4T:

* To use [!DNL Analytics] as the reporting source for [!DNL Target], both you and your company must have access to [!DNL Analytics] and to [!DNL Target]. [Contact your account representative](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) if you need either solution. 
* The reporting source is set for each activity. [!DNL Target] continues to collect data to use in reporting and [!DNL Target] data is still available if you prefer to base an activity on data collected by [!DNL Target]. 
* Use one reporting source or the other. You cannot collect data for a single activity from both sources. 
* When using A4T, all success metrics available to your activities are [!DNL Analytics] metrics. However, your goal metric can be based on an mbox call if using at.js. For example, you can use Target's out-of-the-box click-tracking capabilities with A4T instead of having to implement [!DNL Analytics] click-tracking code. 
* When viewing reporting of an A4T activity in the [!DNL Target] UI, you are viewing [!DNL Analytics] data. For example, if you use the [!UICONTROL Visitor] metric in [!DNL Target], you are using the [!DNL Analytics] [!UICONTROL Visitor] metric, not the [!DNL Target] [!UICONTROL Visitors] metric, which is now called [!UICONTROL Entrants]. This difference is especially important for basic traffic metrics ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) and conversion metrics. 
* Any existing [!DNL Target] activities continue to use [!DNL Target] data collection and are not affected by enabling A4T. 
* Only one mbox-based metric is allowed when using A4T. 
* A server-to-server call from [!DNL Target] to [!DNL Analytics] sends activity and experience information to [!DNL Analytics]. This integration does not result in extra server calls for either [!DNL Target] or [!DNL Analytics]. 

  In some situations, the classifications from [!DNL Target] to [!DNL Analytics] fail and activities do not show data in [!DNL Analytics]. See [Troubleshoot the Analytics and Target integration (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). You can also [contact Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) for further assistance.

## Implement A4T

For information about implementing A4T with at.js and the [!DNL Adobe Experience Platform Web SDK], see [Analytics for [!DNL Target] implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Supported activity types {#section_F487896214BF4803AF78C552EF1669AA}

The following sections contain information about supported activity types when using the [!DNL Adobe Experience Platform Web SDK] or at.js:

| Activity Types | A4T Compatible? | Notes, if applicable |
|--- |--- |--- |
|[A/B activity with manual traffic split](/help/c-activities/t-test-ab/test-ab.md)|Yes||
|[A/B activity with Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)|Yes|See [A4T support for Auto-Allocate and Auto-Target activities](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)|
|[A/B activity with Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md)|Yes|See [A4T support for Auto-Allocate and Auto-Target activities](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).|
|[Experience Targeting (XT)](/help/c-activities/t-experience-target/experience-target.md)|Yes||
|[Multivariate test (MVT)](/help/c-activities/c-multivariate-testing/multivariate-testing.md)|Yes|Requires mbox-based goal metric goal to get the [!UICONTROL Element Contribution] report. The [!UICONTROL Element Contribution] report does not currently support [!DNL Analytics] metrics.|
|[Automated Personalization (AP) activity](/help/c-activities/t-automated-personalization/automated-personalization.md)|No||
|[Recommendations activity](/help/c-recommendations/recommendations.md)|Yes||

Because all activity types do not yet support A4T, it is recommended that you keep or implement important conversion mboxes, such as the `orderConfirmPage` mbox.

## Examples of A4T reports {#section_F0A43A1CB2F04E8282B909E4D7034361}

To view A4T reports in [!DNL Target], click **[!UICONTROL Activities]**, click the desired activity from the list that uses [!DNL Analytics] as its reporting source, then click the **[!UICONTROL Reports]** tab.

>[!NOTE]
>
>You can use the [!UICONTROL Reporting Source] drop-down list at the top of the [!UICONTROL Activities] page to display only activities that use A4T.

You can toggle between the [!UICONTROL Table View] and [!UICONTROL Graph View] of the report by clicking the appropriate icon at the top-right side of the report.

The following illustration shows the [!UICONTROL Graph View] of an A4T report with the [!UICONTROL Report Metric] drop-down list displaying the available [!DNL Analytics] goal metrics:

![](assets/a4t_report_graph1.png)

The following illustration shows the [!UICONTROL Graph View] of an A4T report with the [!UICONTROL Audience] drop-down list displaying the available [!DNL Analytics] audiences:

![](assets/a4t_report_graph2.png)

The following illustration shows the [!UICONTROL Table View] of an A4T report:

![](assets/a4t_report_table.png)

To view the report in [!DNL Analytics] rather than in [!DNL Target], click **[!UICONTROL View in Analytics]** along the top of the report. 

## Analytics & Target: Best Practices for Analysis Tutorial {#section_3438E6E77A464424B717A4FD333B84B2}

Open the [Analytics & Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by [!DNL Adobe Experience League].

## Training videos:

The following videos contain more information about the concepts discussed in this topic.

### Analytics for Adobe Target (A4T) (4:32) ![Overview badge](/help/assets/overview.png)

This video explains how to use [!DNL Analytics] as a reporting source in [!DNL Target] to drive the analysis of your optimization program.

* Explain what A4T is and why you would use it 
* Explain how A4T works 
* Understand the prerequisites needed before using A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics / Adobe Target Integration (A4T) (40:33) ![Tutorial badge](/help/assets/tutorial.png)

This video is a recording of " [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)," an initiative led by the Adobe Customer Care team.

* How to set up and validate that the integration is working 
* How the integration works 
* Learn about the ideal reports to use in Analytics 
* Answers to common questions about A4T

[Analytics/Target Integration (A4T) Office Hours](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [Analytics for [!DNL Target] implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md): Contains implementation information for at.js and the Platform Web SDK.
>* [Redirect offers - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [What is Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html): Contains overview information about the Platform Web SDK.
>* [Target overview](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html): Contains information specific to [!DNL Target] and the [!DNL Platform Web SDK].
