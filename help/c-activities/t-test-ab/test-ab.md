---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: Learn about the different types of A/B Test activities in Adobe [!DNL Target] - Manual, Auto-Allocate, and Auto-Target. Choose the one that's right for you.
title: Which Type of A/B Activities Are Available in Target?
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
---
# A/B Test overview

A manual [!UICONTROL A/B Test] activity compares two or more versions of your website content to see which version best improves your conversions during a pre-specified test period.

>[!NOTE]
>
>In addition to the Manual (Default) [!UICONTROL A/B Test] activity (discussed in this section), [!DNL Target] provides two additional types of [!UICONTROL A/B Test] activities: [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target].
>
>See [Types of A/B Testing activities](#types) below for more information.

A manual [!UICONTROL A/B Test] activity (sometimes referred to as an A/B...N test) compares two or more versions of your Web site content to see which best lifts your conversions, sales, or other metrics you identify. Use an A/B test to compare changes to your page against your default page design to determine which experience produces the best results.

Manual A/B tests are particularly useful when you have a clear hypothesis of ways to improve your page performance based on success metrics or alternative content delivery.

Manual A/B tests are well-suited for large changes that might involve new layouts or drastically different treatments of the elements. If your test design does not easily break down into individual page elements, you should run an A/B test before a [multivariate test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

When you set up your A/B test, you can determine the percentage of visitors that see each experience. For example, you might split traffic evenly between the control and a second experience, or you might test out a new, more risky experience by showing it to only 5% of your audience.

>[!NOTE]
>
>For detailed information about determining the optimum sample size for an A/B test, see [Plan Your A/B Test](/help/c-activities/t-test-ab/sample-size-determination.md).

When the number of different experiences exceeds five and span two or more locations, it's a good idea to consider an [MVT test](/help/c-activities/c-multivariate-testing/multivariate-testing.md) before running your A/B tests. The multivariate test shows which areas on the page are most likely to improve conversion. These are the locations that a marketer should focus on. For example, the MVT test might show that the call to action is the most important location for meeting your goals. Once you have determine which locations and content are most useful for helping you meet your goals, you can then run an A/B test to further refine the results, such as to test two specific images against each other, or to compare the wording or colors of a call to action. By following an MVT test with one or more A/B tests, you can determine the best possible content for the results you desire.

## Types of A/B Testing activities {#types}

In addition to the manual [!UICONTROL A/B Test] activity (discussed in this section), [!DNL Target] provides two additional types of A/B Testing activities: [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target].

|Activity Type|Description|
| --- | --- |
|[!UICONTROL Manual A/B Test]|Compares two or more experiences to see which best improves conversions throughout a pre-specified test period.<br>This section describes how to set up a manual [!UICONTROL A/B Test] activity, but the steps for the other types of [!UICONTROL A/B Test] activities are similar.|
|[!UICONTROL Auto-Allocate]|Identifies a winner among two or more experiences, and then re-directs traffic to the winner, increasing conversion as the test runs and learns.<br>To learn about the benefits of using an Auto-Allocate activity, see [Auto-Allocate](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) in *How long should you run an A/B Test* and [Auto-Allocate overview](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).|
|![Premium badge](/help/assets/premium.png) [!UICONTROL Auto-Target]|Uses advanced machine learning to personalize content and drive conversions by identifying multiple high-performing, marketer-defined experiences, and then serving the most tailored experience to visitors based on their individual customer profiles and past behaviors of similar visitors.<br>For more information,see [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md).|

For more information about which of these [!UICONTROL A/B Test] activities is right for you, see the interactive [Adobe Target Activities Guide PDF](/help/c-activities/target-activities-guide.md).

The steps for creating the three types of [!UICONTROL A/B Test] activities are similar. To create an [!UICONTROL Auto-Allocate] or [!UICONTROL Auto-Target] activity, start by [creating an A/B Test activity](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), but when you get to the [!UICONTROL Targeting] page, choose the desired traffic allocation method, as shown below:

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![Traffic Allocation Method settings](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Training video: Activity Types (9:03) ![Overview badge](/help/assets/overview.png) 

This video explains the activity types available in [!DNL Target Standard/Premium].

* Describe the types of activities included in [!DNL Adobe Target] 
* Select the appropriate activity type to achieve your goals 
* Describe the three-step guided workflow that applies to all activity types

>[!VIDEO](https://video.tv.adobe.com/v/17386)
