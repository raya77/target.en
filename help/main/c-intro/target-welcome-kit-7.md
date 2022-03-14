---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Let's get started with your first activity in Adobe [!DNL Target] so you can obtain ROI on your investment.
title: I Need to Create My First Activity in Target. Where Do I Start?
feature: Overview
exl-id: 4d07b088-a577-4c82-b35f-18d0be8428d8
---
# Chapter 7: Create and run your first [!DNL Target] activity

So you’re ready to get started with your first activity in [!DNL Target]? Excellent. Let’s figure out an activity for your website, mobile site, or mobile app that’s not overly complex., but can provide quick ROI and get you excited about the potential of using [!DNL Target] to test and personalize. Depending on your organization and its focus, you might consider going one of three different routes with that first activity.

Key to your first activity though, is establishing a baseline of the business metric you’re trying to improve—revenue, click throughs, form submissions, completed registrations, and so on. In an A/B test, you can often use the current experience or offer as a “control,” and measure the impact of a variant of that experience or offer against it. With most personalization activities though, you’d ideally determine the performance of the current experience before launching a personalized version of it. This will let you measure the impact of personalization.

## Route 1: A/B testing to all visitor traffic

You could set up a basic [A/B Test activity](/help/main/c-activities/t-test-ab/test-ab.md) in which you test one variation of an offer or experience against one or more other variations to see which ones your visitors prefer. If you’re only looking for the winning variant, you can opt to leverage AI to get quicker results by selecting [Auto-Allocate](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) in the second step of the A/B test setup workflow.

Example: A media company tests its current copy for a gift subscription offer on its web or mobile site homepage to see which variation leads more visitors to purchase a gift subscription. If they select Auto-Allocate, the activity will shift more traffic to the winning variant as the test runs. If not, it will wait for you to manually push the winning experience live after the test concludes.

## Route 2: Personalize to a specific audience

You could set up an [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activity that targets a specific audience you know is valuable with an offer or experience you know would resonate with them.

Example: An airline targets its platinum level members with a special offer that doubles their points on their next flight purchase to reward them and further build customer loyalty.

## Route 3: Application of AI and automation to personalize at scale to individual visitors

You can set up an AI-driven activity to deliver the best experience out of several for each visitor by simply selecting [Auto-Target](/help/main/c-activities/auto-target/auto-target-to-optimize.md) in the second step of the A/B test setup workflow. Using Auto-Target with your first activity can be extremely useful when you don’t know which experience will resonate for different visitors. With Auto-Target, you let machine learning evaluate and score predictive attributes in real-time and determine which attributes of your visitors are most important in determining which experience to deliver.

Example: A telco that sells multiple phone brands and models turns on Auto-Target to use automation and machine learning to determine which of four different experiences or offers on its homepage or mobile app opening screen will best resonate with its wide variety of visitors.

## Generate an activity idea

You could do that basic button color or copy change test, but how about testing or personalizing something that has the potential to demonstrate how powerful [!DNL Target] can be for moving the needle of the business metrics that matter? Something that raises eyebrows with executives in the C-suite and leaders in the business units. 

Here are just a few ways to come up with those activity ideas that are easy to implement but can make a big business impact:

* **Use what you know.** Perhaps you already know your customers well, and have a good sense of what will resonate with them. Use that to develop personalized experiences.
* **Use your analytics solution.** Look for places on your site where customers dropped out of a purchase flow or bounced off a page. Review the pages and hypothesize what might be causing them to exit before taking the action you wanted.
* **Use your powers of observation.** Look at a few key pages on your website and use your gut feel to identify things that need improvement. Maybe a product details page that’s too crowded and wordy, so simplify it. Maybe a purchase button is hard to find, so move it to a more noticeable location.
* **Look at your competitors.** A quick review of your competitors’ websites might reveal designs, offers, copy, and other elements that you believe are highly effective in driving business results. Consider ways to try those approaches on your site.
* **Tap into customer feedback.** Your customers might have given you ideas for improving their experience through an online survey or on customer service calls. Identify a pain point that several have mentioned, and come up with an experience that might eliminate it.

As you come up with your testing idea, keep in mind that you should be able to explain,ideally with data, why you think your proposed test idea can improve the customer experience and metrics that matter to the business.

## Planning your activity with the Activity Planner

We’ve included the [Adobe Target Activity Planner](/help/main/assets/activity-planner.pdf) as a standalone PDF that you can save and use over and over again. Click the link to view the PDF file. Right-click to download the PDF file.

To run an effective activity, you need to fill out each area of the planner. Use this tool as you and others brainstorm ideas for testing and personalization activities.

![Adobe Target Activity Planner](/help/main/c-intro/assets/activity-planner.png)

Here's the type of thought that goes into each area of the planner:

### What can be improved?

Select the channel or touchpoint that you want to improve. Add the URL for the item or describe it. In this case, you’ll add the URL for the web page for which you plan to create a test variation or personalized experience.

### What is your hypothesis?

Clearly explain what the issue is with the current web page experience, including any data or source you used to identify the issue. Explain what you plan to change and why you believe it would improve the customer experience. Finally, explain the result you expect and describing the business value in business success metrics that you believe this new experience will deliver.

### What type of activity is needed?

Check the box of the activity type you intend to run. You can review [Target activity types](/help/main/c-activities/target-activities-guide.md) topic or the [Adobe Target at a Glance](/help/main/c-intro/target-welcome-kit-2.md) chapter to understand the different types of activity types available.

### Who is the target audience?

In an A/B test with a control experience and a variant, for example, you could include your entire visitor population. By default, [!DNL Target] delivers 50 percent to the control and 50 percent to the variant. But if you are personalizing, you could describe the audience or audiences to which you are personalizing. When using AI, you might just note that you are using AI to personalize to the individual. Note that your hypothesis should state why you are choosing a specific audiences for an activity if you are choosing any.

### What are the primary metrics for measuring the impact of the activity?

Describe the business metrics that you will use as an indicator of the success of your activity. For example, increased revenue per visitor (RPV), conversion rate, or average order value (AOV). The more you can tie the impact to the business bottom line,the better, so if you can tie the impact to revenue, that’s ideal.

### What are the secondary metrics for measuring the impact of the activity?

This is the same as the primary metric. Select a metric that helps you measure the impact of the activity on the business.

### What resources/teams need to be involved?

If your activity requires the assistant of a designer, a web developer, or a data analyst, document that here, explaining what they’ll need to do as part of the activity.

### If running a test, how long does this test need to run to reach significance?

You need a certain number of visitors to be put into the test population to draw a statistically significant conclusion from the test. Think about it, if only two people participate in your test, are you going to be confident in the results?

[!DNL Target] relies on statistical principles to determine the results of a test are statistically valid. The Adobe [sample size calculator](https://experienceleague.adobe.com/tools/calculator/testcalculator.html) helps you determine the length of time to run a test based on the confidence you need in your results. Click the [!UICONTROL Learn More] link in this box to open and use the calculator.

### How important is this activity?

No organization has unlimited resources to run all the testing and personalization activities it wants. Use this area to assign a number, for example, from 1 to 5 or label with low, medium, or high to reflect the relative importance of this activity to the business. In many cases, prioritizing an activity is done by considering the level of effort, time, and cost for setting up an activity versus the level of payoff it might deliver.

### What are the results?

After the activity has completed, document the results, being sure to tie those results into the original hypothesis, any important audiences you used in the activity, and the primary and secondary success metrics noted above by which you intended to evaluate the activity results. The next chapter talks about communicating those activity results.

### What needs to be refined in the activity/What are next steps?

Your activity results often provide insights into actions that you should take next. If an experience variation was wildly successful, you may want to hard-code that into your website. You might see opportunities to apply that success on other similar pages. The results might point to more work to be done to improve the customer experience on this page. Use this area to document key learnings from the activity and to document what you’ll do based on those learnings.

## Open [!DNL Target] and create and launch your activity

You’ve filled out your Activity Planner. Now it’s time to get into the solution and build your activity. [!DNL Target] makes it super easy to modify your web page in the [!UICONTROL Visual Experience Composer].
