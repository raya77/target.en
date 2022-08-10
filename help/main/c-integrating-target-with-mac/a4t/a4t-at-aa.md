---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Learn how to create Auto-Allocate and Auto-Target activities in Adobe [!DNL Target] that use Analytics as the reporting source (A4T).
title: Does A4T Support Auto-Allocate and Auto-Target Activities?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
---
# A4T support for Auto-Allocate and Auto-Target activities

The [!DNL Adobe Target]-to-[!DNL Adobe Analytics] integration, known as [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) supports [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities.

The A4T integration lets you:

* Use [Auto-Allocate](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)’s multi-armed bandit capability to drive traffic to winning experiences.
* Use [Auto-Target](/help/main/c-activities/auto-target/auto-target-to-optimize.md)’s ensemble machine learning algorithm to choose a best experience for each visitor. Auto-Target chooses the best experience based on users' profiles, behaviors, and context all while using an [!DNL Adobe Analytics] goal metric and [!DNL Adobe Analytics]’ rich reporting and analysis capabilities.

Make sure you have [implemented A4T for use with A/B Test and Experience Targeting activities](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). If you are using `analyticsLogging = client_side`, you must also pass the `sessionId` value to [!DNL Analytics]. For more information, see [Analytics for Target (A4T) reporting](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} in the *Adobe Target SDKs* guide.

To get started:

1. While creating an A/B Test activity, on the **[!UICONTROL Targeting]** page, select one of the following options as the **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Traffic Allocation Methods options: Manual, Auto-Allocate, and Auto-Target](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   For more information and step-by-step instructions, see [Create an Auto-Allocate activity](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) and [Create an Auto-Target activity](/help/main/c-activities/auto-target/create-auto-target.md).

1. Select **[!UICONTROL Adobe Analytics]** for your **[!UICONTROL Reporting Source]** on the **[!UICONTROL Goals & Settings]** page and select the report suite corresponding to your desired optimization goal.

   ![Reporting Source section on Goals & Settings page](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Choose a Primary Goal metric. The first dropdown allows you to either specify a goal in [!DNL Adobe Target] (which will then be tracked by [!DNL Adobe Analytics] as the metric "Activity Conversions"), or, to use an [!DNL Analytics] metric as your goal. 

   * To use [!DNL Adobe Target] to specify the optimization goal, choose **[!UICONTROL Conversion]**, and then specify the action that must be taken by your audience to indicate that the conversion goal has been reached. 
   * If you instead select **[!UICONTROL Use an Analytics metric]**, you will then be given a choice of what type of optimization criterion should be used.  See [Supported goal metrics and optimization criteria](#supported) below for more information. After specifying the optimization criterion, you can then select a compatible metric from [!DNL Analytics] for use as the optimization goal. You can use an out-of-box [!DNL Analytics] conversion metric or an [!DNL Analytics] custom event.
  

1. Save and activate your activity.

   [!UICONTROL Auto-Allocate] uses your selected metric to optimize the activity, driving visitors to the experience that maximizes your goal metric.

   Or

   [!UICONTROL Auto-Target] uses your selected metric to optimize the activity, driving visitors to a personalized best experience.

1. Use the **[!UICONTROL Reports]** tab to view your activity’s reporting and click **[!UICONTROL View in Analytics]** to dive deep and further segment your reporting data in an Adobe Analytics  Workspace. You can follow the tutorials below to see how to set up your reports in Worskpace:
* Auto-Allocate: see [How to set up A4T reports in Analysis Workspace for Auto-Allocate activities](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*
* Auto-Target: see [How to set up A4T reports in Analysis Workspace for Auto-Target activities](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.

## Supported goal metrics and optimization criteria {#supported}

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] let you choose any of the following metric types as your primary goal metric for optimization:

* [!DNL Adobe Target] conversion metrics
* [!DNL Adobe Analytics] conversion metrics
* [!DNL Adobe Analytics] custom events

However, [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] models will optimize for **normalized** versions of these metrics, with the exact normalization depending on the type of activity. The options for optimization criteria for each type of activity are explained by the table below:

| Activity Type | Metric Source | Optimization Criterion                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------------|---------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Auto-Allocate | Analytics     | Maximize Unique Visitor Conversion Rate | Models attempt to find the Experience with the highest  unique visitor conversion rate, which is defined as the number of visitors for whom the analytics metric is non-zero, divided by  the total number of visitors (who received that Experience). This  means that the metric is treated as binary - either 0, or 1  for each unique visitor in the activity.   Use this option if you only care about the fraction of users doing a particular  action, or when multiple conversion events for a single user are not meaningful.                                                                                                         |
| Auto-Allocate | Analytics     | Maximize Metric Value per Visitor       | Models attempt to find the Experience with the highest  metric value per visitor, which is defined as the total value of the  metric for all users exposed to that Experience, divided by  the total number of visitors who received that Experience. This means that  the metric can take any value for each unique visitor in the activity. For  example, if a visitor converts multiple times, each conversion will be counted.  Use this option if you are interested in maximizing a continuous metric like total revenue,  or if multiple conversion events for a single user are more meaningful than one (e.g.  multiple orders are worth more valuable than one)  |
| Auto-Allocate | Target        | (not configurable)                      | The metric is treated as binary, and the unique visitor conversion rate is maximized.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Auto-Target   | Analytics     | Maximize Unique Visit Conversion Rate   | Unlike Auto-Allocate or manual A/B tests, the personalized nature of Auto-target  means that the Experience a visitor sees can change  for every new visit. The appropriate rate is then a visit-normalized  conversion rate, which is defined as the fraction of visits in which a non-zero metric is  recorded. This is the conversion rate that is optimized by Auto-target.   Similar to Auto-Allocate, this option should be chosen when you care about the fraction of visits  where a conversion happens, i.e., when multiple conversion events occurring for a single visit  is not important.                                         |
| Auto-Target   | Analytics     | Maximize Metric Value per Visit         | When the metric being optimized for is continuous (e.g. revenue), or when the presence of multiple conversion  events in a single visit is meaningful (e.g. multiple orders), then you can choose to maximize the metric value  per visit. The "rate" being optimized is the total value of the metric, divided by the number of visits.                                                                                                                                                                                                                                                                                                       |
| Auto-Target   | Target        | (not configurable)                      | The metric is treated as binary, and the unique visit conversion rate is maximized.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |



Note that depending on optimization criterion, certain [!DNL Adobe Analytics] metrics will not be supported. 

* [!DNL Adobe Analytics] calculated metrics are not supported. 
* [!DNL Adobe Analytics] metrics must always be segmentable, and if the value per visitor/visit is being optimized, the metric must have positive polarity (i.e., positive values are better than negative ones)
* [!DNL Adobe Analytics] metric used in [!DNL Auto-Target] activities must be available in DataWarehouse exports. 

## Limitations and notes

Some limitations and notes apply to both [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities. Other limitations and notes apply to one activity type or the other.

### Auto-Allocate and Auto-Target {#both}

* When using [!DNL Adobe Analytics] as the reporting source for [!UICONTROL Auto-Allocate] or [!UICONTROL Auto-Target], you should always view reports in [!DNL Analytics].
* The reporting source cannot be changed from [!DNL Analytics] to [!DNL Target] or conversely after an activity has been activated.
* Although calculated metrics are not supported as primary goal metrics, it is often possible to achieve the intended result by instead selecting a custom event as the primary goal metric. For example, if you want to optimize for a metric such as "form completions per visitor," select a custom event corresponding to "form completions" as your primary goal metric. As explained in [Supported goal metrics and optimization criteria](#supported), depending on the activity type and your optimization criterion, [!DNL Target] will automatically normalizes conversion metrics, so it is not necessary to use a calculated metric to perform normalization.


### Auto-Allocate {#aa}

* **Training Frequency**: [!UICONTROL Auto-Allocate] models continue to train every hour, as usual.
* **Attribution Models**: [!DNL Target] uses the [!DNL Adobe Analytics] default attribution model for[!UICONTROL  Auto-Allocate] activities that use A4T.
* **Confidence**: The confidence formula used by [!UICONTROL Auto-Allocate] activities is different than the formula shown by default in the [!DNL Adobe Analytics] [!UICONTROL A4T] panel. [As described here](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Auto-Allocate] uses more conservative confidence intervals than regular [!UICONTROL A/B Test] activities. These conservative confidence levels compensate for repeated evaluations (peeks) at data. As a result, the default report in [!DNL Adobe Analytics] shows narrower confidence intervals compared to those being used by the [!UICONTROL Auto-Allocate] algorithm. Nevertheless, you can determine which experience is favored by the algorithms based on which experience has more unique visitors being sent to it. 
* **Winner Status**: Currently, the ["No Winner Yet" and "Winner" badges](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) are not available in the [!UICONTROL A4T] panel in [!DNL Analysis Workspace]. These badges are also not available if the same report is viewed in [!DNL Target]. A winner "star" badge shown in a [!DNL Target] report for an [!UICONTROL Auto-Allocate] activity using A4T should be ignored. This badge reflects regular confidence calculations, and not those used by [!UICONTROL Auto-Allocate].

### Auto-Target {#at}

* **Training Frequency**: [!UICONTROL Auto-Target] models continue to train every 24 hours, as usual. However, conversion event data coming from [!DNL Analytics] is delayed by an extra six to 24 hours. This delay means the distribution of traffic by [!DNL Target] trails the latest events recorded in [!DNL Analytics]. This delay has the largest effect in the first 48 hours after an activity is initially activated. The activity’s performance will more closely mirror [!DNL Analytics] conversion behavior after five days have elapsed. Consider using [!UICONTROL Auto-Allocate] instead of [!UICONTROL Auto-Target] for short-duration activities in which most traffic occurs within the first five days of the activity’s life.
* When using [!DNL Analytics] as the data source for an [!UICONTROL Auto-Target] activity, sessions end after six hours have elapsed. Conversions occurring after six hours are not counted.

For more information, see [Attribution models and lookback windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) in the *Analytics Tools Guide*.

## How to set up A4T reports in Analysis Workspace for Auto-Target and Auto-Allocate activities {#tutorial}

Although rich analysis capabilities are available in [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], a few modifications to the default [!UICONTROL Analytics for Target] panel are required to correctly interpret Auto-Allocate and Auto-Target activities. 

These modifications are required due to the nuanced definitions of conversion rates described in [Supported goal metrics and optimization criteria](#supported), as well as the differences between experimentation activities (manual A/B and [!UICONTROL Auto-Allocate]) and personalization activities ([!UICONTROL Auto-Target]).

These tutorials walk you through the recommended modifications for analyzing [!UICONTROL A4T] [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities in [!UICONTROL Workspace].

For more information, see 
* [How to set up A4T reports in Analysis Workspace for Auto-Allocate activities](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.
* [How to set up A4T reports in Analysis Workspace for Auto-Target activities](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.
