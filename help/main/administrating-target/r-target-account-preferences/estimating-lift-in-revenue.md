---
keywords: revenue lift;revenue;estimating lift in revenue;calculate lift;estimated value
description: Estimate the lift you might achieve if every visitor sees the winning experience, if the trends continue as they have during the test.
title: What Do I Estimate Lift in Revenue?
feature: Administration & Configuration
role: Admin
exl-id: a3c5e20e-f5d5-4b6f-b169-59d5916584ab
---
# Estimate lift in revenue

Use [!DNL Adobe Target] to estimate the revenue lift you would attain if all users view the winning experience.

>[!NOTE]
>
>Estimated lift is not available for [!UICONTROL Experience Targeting] (XT) activities at this time.

The estimated lift feature is turned off by default. It can be enabled in your account preferences. Only Experience Cloud Admin users can enable or disable this feature. If estimated lift is disabled, the corresponding fields do not appear in the interface. Disabling the feature does not result in a loss of data, including the data used for your estimates. The estimates are based on data that is collected whether or not the feature is enabled.

>[!IMPORTANT]
>
>The estimated lift is only an estimate. Its accuracy depends on a number of factors, including projected figures if current trends continue. These values are estimates based on past performance and should not be used for financial guidance. Future results may vary.

This estimate calculates the amount of lift achieved by the winning experience and your total number of visitors over the life of the activity, and shows the lift you might achieve if every visitor sees the winning experience, if the trends continue as they have during the test.

The estimated lift in revenue is calculated based on the Revenue Per Visit (RPV) obtained from the Primary Goal metric.

The estimated lift is calculated using the following formula: (&lt;winning experience RPV&gt; - &lt;control experience RPV&lt;)&#42;&lt;total number of visitors in the activity&gt;

The resulting number is rounded to one decimal place, maximum, if the condensed form has only a single digit before the decimal. For example: $1.6M, $60K, $900, $8.5K, $205K

For example, if your winning experience shows a lift of $0.59, and your control experience shows a lift of $0.15, the estimate calculates a lift of $0.44 per visitor. If you had 75,000 visitors, the resulting lift in revenue would be $33,000 if all visitors see the winning experience and current trends continue.

Likewise, if your winning experience shows a lift of $0.17 over the control experience, and you have had 192,000 visitors during the life of the test, then if current trends continue you could expect a revenue lift of $32,640.

The estimated lift in revenue field is shown as "---" under the following circumstances:

* If there have not been enough visitors to calculate a reasonable estimate 
* If the estimated value of the metric has not been provided on the metric setup page 
* If the best performing experience is the control

When setting up an activity's goals, the Estimated Value field provides a value for your goal. This value enables Target to calculate the estimated lift in revenue. This field is optional; however, incremental revenue for any non-revenue metric cannot be calculated without it. The data type is currency. This field is progressively shown after the user indicates the action taken to satisfy the goal.

The estimated revenue if 100% of visitors view the winning experience appears at the top of your Target reports.
