---
keywords: Targeting;audience;reporting;success metric
description: Learn how to choose a success metric in Adobe [!DNL Target] that qualifies the user for the reporting audience.
title: Can I Apply a Reporting Audience To A Success Metric?
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
---
# Apply a reporting audience to a success metric

Choose a success metric that qualifies the user for the reporting audience.

For all activities, the [!UICONTROL Applied At] drop-down list lets you apply an audience to a success metric so you can view reporting numbers after the metric has been reached and for subsequent actions.

![](assets/success_metric.png)

For example, suppose you have created an activity for all visitors entering from your home page and reaching the conversion page, but you also want to drill down more on visitors who have added more than $50 into the cart before converting.

The Applied At drop-down list potentially provides three categories: any visitors to the activity, only visitors who reach a certain step in the activity, or only visitors who reach conversion. Or, to phrase it another way, you can specify that a visitor must have reached an mbox on the entry page of the activity, an mbox that defines some point in the middle of the activity, or the conversion mbox at the end of the activity.

[Success metrics](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) are available only if you have configured them for your activity. If you have not defined success metrics, you'll see only two options from the drop-down list: Campaign Entry and Conversion.

Consider the following information when applying a reporting audience to a success metric:

* For actions before the action with the applied success metric, Target does not apply a segmented audience. 
* For actions after the applied success metric, Target applies a segmented audience.

To view the segmentation in reporting, select the desired audience from the Audience drop-down list in the activity's report.

![](assets/reporting_audience_dropdown.png)
