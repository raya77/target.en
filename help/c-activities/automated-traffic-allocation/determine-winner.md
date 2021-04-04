---
keywords: automated traffic allocation;targeting;winner;statistical guarantee;confidence;determine winner;lift;confidence;default;default experience;auto-allocate;auto allocate
description: Learn how to interpret the results of an Auto-Allocate A/B activity in Adobe Target by examining important indicators, including lift and confidence.
title: How Do I Interpret Auto-Allocate Reports?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
---
# Interpret Auto-Allocate reports {#determine-a-winner}

Interpret the results of an [!UICONTROL Auto-Allocate] A/B activity in [!UICONTROL Adobe Target] by examining important indicators, including lift and confidence.

Many marketers make the mistake of prematurely declaring a winning experience before the results indicate the clear winner. We've now made it easier for you to determine the winner. 

>[!NOTE]
>
>For general information about declaring a winner, see [Ten common A/B testing pitfalls and how to avoid them](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identify the winning experience {#section_24007470CF5B4D30A06610CE8DD23CE3}

When using the [!UICONTROL Auto-Allocate] feature, [!DNL Target] displays a badge at the top of the activity's page indicating "No Winner Yet" until the activity reaches the minimum number of conversions with sufficient confidence.

![No Winner badge](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

When a clear winner is declared, [!DNL Target] displays "Winner: Experience X."

![](assets/winner.png)

>[!NOTE]
>
>Auto-Allocate activities are designed to find the best experience among all options and not just to do pairwise comparisons with control.

## Statistical guarantees of Auto-Allocate {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

At the end of an A/B activity, Auto-Allocate guarantees that the determined winner has an effective false-positive rate of 5%. This means that only 5% of the time, the determined winner is not actually the best experience among all the experiences in the activity. For an A/A test (with identical experiences), we conclude a test less than 5% of the time. The expected behavior for an A/A test (with identical experiences) is for it to run indefinitely and so the winner badge should never appear.

We do not use p-value based confidence for Auto-Allocate.

The Confidence column in an Auto-Allocate activity (illustrated below) displays the probability of an experience being the winner within 1% margin of error (i.e. the algorithm uses a minimum detectable effect of 1% between the best and the second-best conversion rate). Note that the algorithm uses [Bernstein Inequality](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)) to compute this probability.

Normal A/B tests compute confidence based on p-values. Auto-Allocate does not use p-values. P-values "loosely" compute the probability that a given experience is different from the control. These p-values can be used only to determine whether an experience might be different from the control. These values cannot be used to determine if an experience is different from another experience (not control).

>[!IMPORTANT]
>
>Target shows a winner after a predefined minimum number of conversions; however, the final decision to pick the winner should always be on the results of the Adobe Target [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html). Target does not consider the base conversion rates of a site and other important aspects that are fed into the calculator to determine the duration of the activity. As a result, Target might display a winner earlier than warranted on the basis of a minimum number of conversions. For more information, see [Sample Size Calculator](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Understand Lift and Confidence reporting in Auto-Allocate activities {#lift-confidence}

In Auto-Allocate activities, the first experience (by default named Experience A) is always defined as a “Control” experience on the Reports tab. This experience is not treated as a true statistical control in the modeling used to determine the performance of experiences, but it is treated as a reference or baseline for some figures in the report.

The "Lift” numeric value and 95% bounds for each experience are always calculated with reference to the defined “Control” experience. The defined “Control” experience cannot have lift relative to itself, so a blank “---” value is reported for this experience. Unlike in A/B tests, in Auto-Allocate tests, if an experience performs worse than the defined control, a negative Lift value is not reported; instead “---” is displayed.

The displayed Confidence Interval bars represent the 95% confidence interval around the mean estimate of an experience’s conversion rate. These are also color-coded with respect to the defined “Control” experience. The “Control” experience’s bar is always colored gray. The portions of confidence intervals below the “Control” experience’s confidence interval are colored red and the portions of confidence intervals above the “Control” experience are colored green.

A winner is found when the leading experience’s 95% Confidence Interval is not overlapping with any other experiences. The winning experience is designated with a green star badge to the left of the experience name and in the “Winner” banner. When no star is visible, the banner reads “No Winner Yet” and a winner has not yet been found.

A “Confidence” number is also reported next to the currently leading or winning experience. This figure is reported only until the leading experience’s Confidence reaches at least 60%. If exactly two experiences are present in the Auto-Allocate experiment, this number represents the confidence level that the experience is performing better than the other experience. If more than two experiences are present in the Auto-Allocate experiment, this number represents the confidence level that the experience is performing better than the defined “Control” experience. If the “Control” experience is winning, no “Confidence” figure is reported.

## Frequently Asked Questions {#section_C8E068512A93458D8C006760B1C0B6A2}

**It has been a few days into the activity. Why are all confidence values still showing 0%?**

Any of the following reasons describe why 0% displays in the report's [!UICONTROL Confidence] column for all activities:

* Manual A/B tests and Auto-Allocate use different statistics to display Confidence values.

  Manual A/B tests use p-values based on [Student's t-test](https://en.wikipedia.org/wiki/Student%27s_t-test). A P-value is the probability of finding the observed (or a more extreme) difference between an experience and the control, given that in reality there is no such difference. These P-values can be used only to determine whether observed data is consistent with a given experience and the control being the same. These values cannot be used to determine if an experience is different from another experience (not control).

  Auto-allocate shows the probability of a given experience being a true winner across all experiences in the activity. This means only a winning experience (which is most likely to be the winner), will have a non-zero confidence value. All others are most likely to be losers and will display 0%. 

* Auto-Allocate starts showing confidence only after the winning experience gathers 60% confidence. These confidence levels typically appear in about half the time that a normal A/B test would take to complete (although this is not guaranteed). To determine how long a normal A/B test would run, please use a [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html): plug control's conversion-rate in "Baseline conversion rate," "5%" for "Lift," and 95% for "Confidence." Typically, confidence starts showing after each experience has amassed at least 50% of the required samples per-experience. This will give you an idea of when confidence will start appearing. 
* If the report is showing 0% across the board, it is likely too early into the activity.
