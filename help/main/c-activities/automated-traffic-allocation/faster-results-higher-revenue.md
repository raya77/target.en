---
keywords: automated traffic allocation;targeting;auto-allocate;auto allocate
description: Learn how an Auto Allocate activity in Adobe [!DNL Target] identifies a winner among two or more experiences and automatically reallocates more traffic to the winner.
title: Can Auto-Allocate Activities Get Faster Results and Higher Revenue?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
---
# Auto-Allocate can give you faster test results and higher revenue than a manual test

With a manual A/B activity, you might be losing conversions because you can’t deliver the winning experience to your entire audience until the activity completes. Your traffic distribution remains fixed even after you recognize that some experiences are outperforming others, and the activity must run its entire course before you can act on a winner.

## Auto-allocating traffic

If you want an option to serve the winning experience more often and earlier in the activity while simultaneously removing or reducing the set-up and calculation cost of picking sample sizes, confidence levels, and other statistical concepts, [!UICONTROL Auto-Allocate] is your best option.

## How does Auto-Allocate work?

[!UICONTROL Auto-Allocate] uses the principle of the multi-armed bandit. If the term is unfamiliar, a one-armed bandit is a colloquial term for a slot machine (think: Las Vegas). Visualize auto-allocation of traffic as having multiple slot machines, in this case, test variations, and at first pulling all handles equally. Over time, one or more machines, or test variations, might pay out more than others. When this happens, a gambler would naturally start pulling the handles of the ones that win more often. In traffic allocation terms, [!DNL Adobe Target] will serve more visitors the experience or experiences that are winning more.

Consider the following illustration of a two-week A/B activity. With [!UICONTROL Auto-Allocate], as a winning experience emerges, [!UICONTROL Target] diverts more of the traffic to that winner early on in the test.

![Auto-Allocate illustration](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## How does Auto-Allocate give me faster results?

The upside is pretty clear: more visitors see the variations that perform best. And as a single variation pulls ahead, even more visitors get diverted to that winning experience, while the test was still running. This is especially helpful if the A/B activity being run is happening during a core business moment such as a holiday, product launch, or world news event.

## How could Auto-Allocate give me higher revenue?

[!UICONTROL Auto-Allocate] finds the winner faster than a manual A/B split, and also allows you to exploit that winner immediately–capturing upside revenue that would have been lost in a traditional or manual approach. Because [!UICONTROL Auto-Allocate] directs more traffic to the experience with the highest conversion rate, it can increase your revenue while the activity runs and learns.

In the following example, [!UICONTROL Auto-Allocate] gained more revenue during the test by pushing more traffic (40%) to Experience D, which had the highest conversion rate.

![Auto-allocate provides higher revenue illustration](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## In what cases should I stick with manual traffic allocation?

When you need to rank-order how every experience performed relative to the others, a manual A/B test is most applicable. [!UICONTROL Auto-Allocate] finds and exploits top performers but does not guarantee differentiation among the lower performing experiences. You should use manual traffic allocation for complete control of how much of your visitor traffic sees each test variant and for customization of the statistical thresholds that are relevant for your business.

## Get started

Ready to launch your first [!UICONTROL Auto-Allocate] activity? [Learn how here](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
