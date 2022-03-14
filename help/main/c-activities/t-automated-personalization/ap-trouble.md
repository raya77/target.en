---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Explore potential challenges you might face while using Automated Personalization (AP) activities in Adobe Target, along with suggested solutions.
title: How Do I Troubleshoot Automated Personalization?
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
---
# ![PREMIUM](/help/main/assets/premium.png) Troubleshoot Automated Personalization

Sometimes activities don't go as expected. Here are some potential challenges you might face while using Automated Personalization, and some suggested solutions.

## My AP activity is taking too long to build models. {#section_20028B204DBB4D77A324BA193434AEE2}

There are several activity setup changes that can decrease the expected time to build models, including the number of experiences in your Automated Personalization test, the traffic to your site, and your selected success metric.

**Solution:** Review your activity setup and see if there are any changes you are willing to make to improve the speed at which models will build.

* If your success metric is set to RPV, can you change to conversion? Conversion activities tend to require less traffic to build models. You will not lose activity data is you change the success metric from RPV to conversion. 
* Is your success metric far down the sales funnel from your activity experiences? A lower activity conversion rate increases the traffic requirements needed for models to build, as a minimum number of conversions is required. 
* Are there some offers or experiences you can exclude from your activity? Decreasing the number of experiences in an activity speeds the amount of time to build models. 
* Is there a higher-traffic page there this activity would be more successful? The more traffic and conversions in your activity locations, the quicker models will build.

## My AP activity didn't generate any lift. {#section_8900BC8968474438B8092F7A94C0C6CF}

There are several factors required for an AP activity to generate lift:

* The offers need to be different enough to influence visitors. 
* The offers need to be located somewhere that makes a difference to the optimization goal. 
* There must be enough traffic and statistical "power" in the test to detect the lift. 
* The personalization algorithm must work well.

**Solution:** The best course of action is to first make sure the content and locations that make up the activity experiences truly make a difference to the overall response rates using a simple, non-personalized A/B test. Be sure to compute the sample sizes ahead of time to ensure there is enough power to see a reasonable lift and run the A/B test for a fixed duration without stopping it or making any changes. If an A/B test results show statistically significant lift on one or more of the experiences, then it is likely that a personalized activity will work. Of course, personalization can work even if there are no differences in the overall response rates of the experiences. Typically, the issue stems from the offers/locations not having a large enough impact on the optimization goal to be detected with statistical significance.

## My AP activity URL is showing offer content on incorrect pages. {#section_82A224406DBF4107B05204BEFBBE458C}

In AP, the URL and template testing rules are added to the [!DNL Target] request entry constraint (for example, target-global-mbox), where they are evaluated only once. Once a user qualifies for an activity, the Target-request-level targeting rules are not re-evaluated. However, the targeting audience is added to location targeting rules.

**Solution:** Add the necessary template rules as the input-audience of the campaign. Audience evaluation happens upon each request/call.

This will be fixed in an upcoming release.

## Any metric dependent on conversion metric never converts. {#section_076D1F44298C4E4A849AC52F5A33214D}

This is expected.

In an AP activity, once a conversion metric (whether optimization goal or post goal) is converted, the user is released from the experience and the activity is restarted.

For example, there is an activity with a conversion metric (C1) and an additional metric (A1). A1 is dependent on C1. When a visitor enters the activity for the first time, and the criteria for converting A1 and C1 are not converted, metric A1 is not converted due to the success metric dependency. If the visitor converts C1 and then converts A1, A1 is still not converted because as soon as C1 is converted, the visitor is released.

## My Experience URLs are not working as expected. {#section_7B08DA1F30AA483E9406336DAF361BA4}

* If you are not able to see the preview in the new tab (due to browser cache), try refreshing two or three times or copy the link and open it in new browser or new session. 
* Regenerate the Experience URL links if you changed any content and share the new links with your teammates.
