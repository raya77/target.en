---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Learn how to create Auto-Allocate and Auto-Target activities in Adobe Target that use Analytics as the reporting source (A4T).
title: Does A4T Support Auto-Allocate and Auto-Target Activities?
feature: Analytics for Target (A4T)
---

# A4T support for Auto-Allocate and Auto-Target activities

The [!DNL Adobe Target]-to-[!DNL Adobe Analytics] integration, known as [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) supports [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities.

The A4T integration lets you:

* Use [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)’s multi-armed bandit capability to drive traffic to winning experiences.
* Use [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md)’s ensemble machine learning algorithm to choose a best experience for each visitor. Auto-Target chooses the best experience based on users' profiles, behaviors, and context all while using an [!DNL Adobe Analytics] goal metric and [!DNL Adobe Analytics]’ rich reporting and analysis capabilities.

Make sure you have [implemented A4T for use with A/B Test and Experience Targeting activities](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). If you are using `analyticsLogging = client_side`, you must also pass the `sessionId` value to [!DNL Analytics]. For more information, see [Analytics for Target (A4T) reporting](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) in the *Adobe Target SDKs* guide.

To get started:

1. While creating an A/B Test activity, on the **[!UICONTROL Targeting]** page, select one of the following options as the **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Traffic Allocation Methods options: Manual, Auto-Allocate, and Auto-Target](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   For more information and step-by-step instructions, see [Create an Auto-Allocate activity](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) and [Create an Auto-Target activity](/help/c-activities/auto-target/create-auto-target.md).

1. Select **[!UICONTROL Adobe Analytics]** for your **[!UICONTROL Reporting Source]** on the **[!UICONTROL Goals & Settings]** page and select the report suite corresponding to your desired optimization goal.

   ![Reporting Source section on Goals & Settings page](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Choose a Primary Goal metric.

   * To use [!DNL Adobe Target] to specify the optimization goal, choose **[!UICONTROL Conversion]** .
   * Choose **[!UICONTROL Use an Analytics metric]** and then select a metric from [!DNL Analytics] for use as the optimization goal. You can use an out-of-box [!DNL Analytics] conversion metric or an [!DNL Analytics] custom event.

   See [Supported goal metrics](#supported) below for more information.

1. Save and activate your activity.

   [!UICONTROL Auto-Allocate] uses your selected metric to optimize the activity, driving visitors to the experience that maximizes your goal metric.

   Or

   [!UICONTROL Auto-Target] uses your selected metric to optimize the activity, driving visitors to a personalized best experience.

1. Use the **[!UICONTROL Reports]** tab to view your activity’s reporting by your choice of [!DNL Adobe Analytics] metrics. Click **[!UICONTROL View in Analytics]** to dive deep and further segment your reporting data.

## Supported goal metrics {#supported}

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] let you choose any of the following metric types as your primary goal metric for optimization:

* [!DNL Adobe Target] conversion metrics
* [!DNL Adobe Analytics] conversion metrics
* [!DNL Adobe Analytics] custom events

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] requires you to choose a metric that is based on a binomial event. A binomial event either does or does not happen. Binomial events include a click, a conversion, an order, and so forth. These types of events are also sometimes referred to as Bernoulli, binary, or discrete events.

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] does not support optimization for continuous metrics. Continuous metrics include  revenue, number of products ordered, session duration, number of page views in session, and so forth. These unsupported types of metrics are also sometimes referred to as non-binomial or non-Bernoulli metrics.

The following metric types are unsupported as primary goal metrics:

* [!DNL Adobe Target] engagement and revenue metrics
* [!DNL Adobe Analytics] engagement and revenue metrics

  It is possible to select an [!DNL Analytics] engagement or revenue metric as your primary goal metric because [!DNL Target] cannot identify and exclude all engagement and revenue metrics from [!DNL Analytics]. Select only binomial conversion metrics or custom events from [!DNL Analytics].

* [!DNL Adobe Analytics] calculated metrics

## Limitations and notes

Some limitations and notes apply to both [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities. Other limitations and notes apply to one activity type or the other.

### Auto-Allocate and Auto-Target

* The reporting source cannot be changed from [!DNL Analytics] to [!DNL Target] or conversely after an activity has been activated.
* Although calculated metrics are not supported as primary goal metrics, it is often possible to achieve the intended result by instead selecting a custom event as the primary goal metric. For example, if you want to optimize for a metric such as "form completions per visitor," select a custom event corresponding to "form completions" as your primary goal metric. [!DNL Target] automatically normalizes conversion metrics on a per-visit basis to account for uneven traffic distribution, so it is not necessary to use a calculated metric to perform normalization.
* [!DNL Target] uses the "Same Touch" attribution model in the [!UICONTROL Auto-Allocate] feature: Analytics for Target (A4T).

### Auto-Allocate

* [!UICONTROL Auto-Allocate] models continue to train every two hours, as usual.

### Auto-Target

* [!UICONTROL Auto-Target] models continue to train every 24 hours, as usual. However, conversion event data coming from [!DNL Analytics] is delayed by an extra six to 24 hours. This delay means the distribution of traffic by [!DNL Target] trails the latest events recorded in [!DNL Analytics]. This delay has the largest effect in the first 48 hours after an activity is initially activated. The activity’s performance will more closely mirror [!DNL Analytics] conversion behavior after five days have elapsed. Consider using [!UICONTROL Auto-Allocate] instead of [!UICONTROL Auto-Target] for short-duration activities in which most traffic occurs within the first five days of the activity’s life.
* When using [!DNL Analytics] as the data source for an [!UICONTROL Auto-Target] activity, sessions end after six hours have elapsed. Conversions occurring after six hours are not counted.

For more information, see [Attribution models and lookback windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) in the *Analytics Tools Guide*.
