---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
description: Learn how an Auto-Target activity in [!DNL Target] serves the most tailored experience to each visitor based on customer profiles and the behavior of similar visitors.
title: What Is an Auto-Target Activity?
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
---
# ![PREMIUM](/help/assets/premium.png) Auto-Target overview

[!UICONTROL Auto-Target] activities in [!DNL Adobe Target] use advanced machine learning to select from multiple high-performing marketer-defined experiences to personalize content and drive conversions. Auto-Target serves the most tailored experience to each visitor based on the individual customer profile and the behavior of previous visitors with similar profiles. 

>[!NOTE]
>
>[!UICONTROL Auto-Target] is available as part of the [!DNL Target Premium] solution. This feature is not available in [!DNL Target Standard] without a [!DNL Target Premium] license. For more information about the advanced features this license provides, see [Target Premium](/help/c-intro/intro.md).
>
>[!UICONTROL Analytics for Target] (A4T) supports [!UICONTROL Auto-Target] activities. For more information, see [A4T support for Auto-Allocate and Auto-Target activities](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## Real-world success story using Auto-Target {#success}

A major clothing retailer recently used an [!UICONTROL Auto-Target] activity with ten product category-based experiences (plus randomized control) to deliver the right content to each visitor. "[!UICONTROL Add to Cart]" was chosen as the primary optimization metric. The targeted experiences had an average lift of 29.09%. After building the [!UICONTROL Auto-Target] models, the activity was set to 90% personalized experiences. 

In just ten days, more than $1,700,000 in lift was achieved. 

Keep reading to learn how to use [!UICONTROL Auto-Target] to increase lift and revenue for your organization.

## Overview {#section_972257739A2648AFA7E7556B693079C9}

While [creating an A/B activity using the three-step guided workflow](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), you can choose to allocate traffic using the [!UICONTROL Auto-Target For Personalized Experiences] option:

![Auto target for personalized experiences option](/help/c-activities/assets/auto-target-ui-new.png)

The [!UICONTROL Auto-Target] option within the A/B activity flow lets you harness machine-learning to personalize based on a set of marketer-defined experiences in one click. [!UICONTROL Auto-Target] is designed to deliver maximum optimization, compared to traditional A/B testing or Auto Allocate, by determining which experience to display for each visitor. Unlike an A/B activity in which the objective is to find a single winner, [!UICONTROL Auto-Target] automatically determines the best experience for a given visitor (based on his or her profile and other contextual information) to deliver a highly personalized experience.

Similarly to Automated Personalization, [!UICONTROL Auto-Target] uses a Random Forest algorithm, a leading data science ensemble method, to determine the best experience to show to a visitor. Because [!UICONTROL Auto-Target] can adapt to changes in visitor behavior, it can be run perpetually to provide lift. This is sometimes referred to as "always-on" mode.

Unlike an A/B activity in which the experience allocation for a given visitor is sticky, [!UICONTROL Auto-Target] optimizes the specified business goal over each visit. Like in [!UICONTROL Auto Personalization], [!UICONTROL Auto-Target], by default, reserves part of the activity's traffic as a control group to measure lift. Visitors in the control group are served a random experience in the activity.

## Considerations

There are a few important considerations to keep in mind when using [!UICONTROL Auto-Target]:

* You cannot switch a specific activity from [!UICONTROL Auto-Target] to Automated Personalization, and vice versa. 
* You cannot switch from Manual traffic allocation (traditional A/B Test) to [!UICONTROL Auto-Target], and vice versa after an activity is live. 
* One model is built to identify the performance of the personalized strategy vs. randomly served traffic vs. sending all traffic to the overall winning experience. This model considers hits and conversions in the default environment only. 

  Traffic from a second set of models is built for each modeling group (AP) or experience (AT). For each of these models, hits and conversions across all environments are considered. 
  
  Requests are served with the same model, regardless of environment, but the plurality of traffic should come from the default environment to ensure that the identified overall winning experience is consistent with real-world behavior.

* Use a minimum of two experiences.

## Terminology {#section_A309B7E0B258467789A5CACDC1D923F3}

The following terms are useful when discussing [!UICONTROL Auto-Target]:

|  Term  | Definition  |
|---|---|
|  Multi-armed bandit  | A multi-armed bandit approach to optimization balances exploratory learning and exploitation of that learning.  |
|  Random Forest  |Random Forest is a leading machine learning approach. In data-science speak, it is an ensemble classification, or regression method, that works by constructing many decision trees based on visitor and visit attributes. Within Target, Random Forest is used to determine which experience is expected to have the highest likelihood of conversion (or highest revenue per visit) for each specific visitor. For more information about Random Forest in Target, see [Random Forest Algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md).  |
|  Thompson Sampling  |The goal of Thompson Sampling is to determine which experience is the best overall (non-personalized), while minimizing the “cost” of finding that experience. Thompson sampling always picks a winner, even if there is no statistical difference between two experiences. For more information, see [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling).  |

## How [!UICONTROL Auto-Target] Works {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Learn more about the data and algorithms underlying [!UICONTROL Auto-Target] and Automated Personalization at the links below:

| Term | Details |
|--- |--- |
|[Random Forest Algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md)|Target's main personalization algorithm used in both [!UICONTROL Auto-Target] and Automated Personalization is Random Forest. Ensemble methods like Random Forest use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms. The Random Forest algorithm in the Automated Personalization system is a classification, or regression method, that operates by constructing a multitude of decision trees at training time.|
|[Uploading Data For Target's Personalization Algorithms](/help/c-activities/t-automated-personalization/algo-random-forest.md)|There are several ways to input data for [!UICONTROL Auto-Target] and Automated Personalization models.|
|[Data Collection for Target's Personalization Algorithms](/help/c-activities/t-automated-personalization/ap-data.md)|Target's personalization algorithms automatically collect various data.|

## Determining Traffic Allocation {#section_AB3656F71D2D4C67A55A24B38092958F}

Depending on the goal of your activity, you might choose a different traffic allocation between control and personalized experiences. Best practice is to determine this goal before you make your activity live.

The [!UICONTROL Custom Allocation] drop-down list lets you choose from the following options:

* Evaluate Personalization Algorithm 
* Maximize Personalization Traffic 
* Custom Allocation

![Allocation Goal drop-down list](/help/c-activities/assets/split-new.png)

| Activity Goal | Suggested Traffic Allocation | Tradeoffs |
|--- |--- |--- |
|**Evaluate Personalization Algorithm (50/50)**: If your goal is to test the algorithm, use a 50/50 percent split of visitors between the control and the targeted algorithm. This split gives the most accurate estimate of the lift. Suggested for use with “random experiences” as your control.|50% Control / 50% Personalized Experience split|<ul><li>Maximizes accuracy of lift between control and personalized</li><li>Relatively fewer visitors have a personalized experience</li></ul>|
|**Maximize Personalization Traffic (90/10)**: If your goal is to create an “always on” activity, put 10% of the visitors into the control to ensure there is enough data for the algorithms to continue learning over time. Note the tradeoff here is that in exchange for personalizing a larger proportion of your traffic, you have less precision in what the exact lift is. No matter your goal, this is the recommended traffic split when using a specific experience as the control.|Best practice is to use a 10% - 30% Control / 70% - 90% Personalized Experience split|<ul><li>Maximizes number of visitors who have a personalized experience</li><li>Maximizes lift</li><li>Less accuracy as to what the lift is for the activity</li></ul>|
|**Custom Allocation**|Manually split the percentage as desired.|<ul><li>You might not achieve the desired results. If you are unsure, follow the suggestions for either of the preceding options</li></ul>|

To adjust the Control percentage, click the icons in the Allocation column. You cannot decrease the control group to less than 10%.

![Change Auto-Target traffic allocation](/help/c-activities/assets/auto-target-control.png)

You can [select a specific experience to use as control](/help/c-activities/t-automated-personalization/experience-as-control.md) or you can use the Random experience option.

## When should you choose [!UICONTROL Auto-Target] over Automated Personalization? {#section_BBC4871C87944DD7A8B925811A30C633}

There are several scenarios where you might prefer to use [!UICONTROL Auto-Target] over [!UICONTROL Automated Personalization]:

* If you want to define the entire experience rather than individual offers that will be automatically combined to form an experience. 
* If you want to use the full set of Visual Experience Composer (VEC) features not supported by [!UICONTROL Auto Personalization]: the custom code editor, multiple experience audiences, and more. 
* If you want to make structural changes to your page in different experiences. For example, if you wanted to rearrange elements on your home page, [!UICONTROL Auto-Target] would be more appropriate to use than Automated Personalization.

## What does [!UICONTROL Auto-Target] Have in Common with Automated Personalization? {#section_2A601F482F9A44E38D4B694668711319}

**The algorithm optimizes for a favorable outcome for each visit.**

* The algorithm predicts a visitor's propensity for conversion (or estimated revenue from conversion) in order to serve the best experience. 
* A visitor is eligible for a new experience upon the end of an existing session (unless the visitor is in the control group, in which case the experience that visitor is assigned on the first visit remains the same for subsequent visits). 
* Within a session, the prediction doesn’t change, to maintain visual consistency.

**The algorithm adapts to changes in visitor behavior.**

* The multi-arm bandit ensures that the model is always "spending" a small fraction traffic to continue to learn throughout the life of the activity learning and to prevent over-exploitation of previously learned trends. 
* The underlying models are rebuilt every 24 hours using the latest visitor behavior data to ensure that Target is always exploiting changing visitor preferences. 
* If the algorithm can't determine winning experiences for individuals, it automatically switches to showing the overall best-performing experience while still continuing to look for personalized winners. The best-performing experience is found using [Thompson sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

**The algorithm continually optimizes for a single goal metric.**

* This metric could be conversion-based or revenue-based (more specifically Revenue per Visit).

**Target automatically collects information about visitors to build the personalization models.**

* For more information about the parameters used in [!UICONTROL Auto-Target] and Automated Personalization, see [Automated Personalization Data Collection](/help/c-activities/t-automated-personalization/ap-data.md).

**Target automatically uses all Experience Cloud shared audiences to build the personalization models.**

* You don't have to do anything specific to add audiences to the model. For information about using Experience Cloud Audiences with Target, see [Experience Cloud Audiences](/help/c-integrating-target-with-mac/mmp.md)

**Marketers can upload offline data, propensity scores, or other custom data to build personalization models.**

* Learn more about [uploading data for Auto-Target and Automated Personalization](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## How Does [!UICONTROL Auto-Target] differ from Automated Personalization? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL Auto-Target] frequently requires less traffic than Automated Personalization for a personalized model to build.**

Although the amount of traffic *per experience* required for [!UICONTROL Auto-Target] or [!UICONTROL Auto Personalization] models to build are the same, there are usually more experiences in an Automated Personalization activity than an [!UICONTROL Auto-Target] activity. For example, if you had an [!UICONTROL Auto Personalization] activity where you've created two offers per location with two locations, there would be four (2 = 4) total experiences included in the activity (with no exclusions). Using [!UICONTROL Auto-Target], you could set experience 1 to include offer 1 in location 1 and offer 2 in location 2, and experience 2 to include offer 1 in location 1 and offer 2 in location 2. Because [!UICONTROL Auto-Target] allows you could choose to have multiple changes within one experience, you can reduce the number of total experiences in your activity.

For [!UICONTROL Auto-Target], simple rules of thumb can be used to understand traffic requirements:

* **When Conversion is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 7,000 visits and 350 conversions. 
* **When Revenue per Visit is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 1,000 conversions per experience. RPV usually requires more data to build models due to the higher data variance that typically exists in visit revenue compared to conversion rate.

**[!UICONTROL Auto-Target] has full-fledged setup functionality.**

* Because [!UICONTROL Auto-Target] is embedded in the A/B activity workflow, [!UICONTROL Auto-Target] benefits from the more mature and full-fledged Visual Experience Composer (VEC). You can also leverage [QA links](/help/c-activities/c-activity-qa/activity-qa.md) with [!UICONTROL Auto-Target].

**[!UICONTROL Auto-Target] provides an extensive online testing framework.**

* The multi-arm bandit is part of a larger online-testing framework that allows our data-scientists and researchers to understand the benefits of their continual improvements in real-world conditions. 
* In the future, this test bed will allow us to open our machine learning platform to our data-savvy clients so that they can bring in their own models to augment Target's models.

## Reporting and [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

For more information, see [Auto-Target Summary Report](/help/c-reports/auto-target-summary-report.md) in the [Reports](/help/c-reports/reports.md) section.

## Training video: Understanding Auto-Target Activities ![Overview badge](/help/assets/overview.png)

This video explains how to set up an [!UICONTROL Auto-Target] A/B activity.

After completing this training, you should be able to:

* Define [!UICONTROL Auto-Target] testing 
* Compare and contrast [!UICONTROL Auto-Target] to Automated Personalization 
* Create [!UICONTROL Auto-Target] activities

>[!VIDEO](https://video.tv.adobe.com/v/18558)
