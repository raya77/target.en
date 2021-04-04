---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Read tips from our panel of experts about using Adobe Target as part of your testing and personalization efforts.
title: Where Can I Find Tips and Tricks for Using Target?
feature: Overview
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
---
# Chapter 4: Tips for using Target

Based on our work with many [!DNL Target] users, we’ve observed ways that you can get more value from your [!DNL Target] solution. We’ve summarized those in the many tips we’ve included in this chapter. Although you might not be ready to use all of these ideas right away, hold on to this list. The more experience you get with the solution and the more your program matures, the more you’ll see how these tips can help you accomplish more with [!DNL Target].

## Tip 1: Deepen personalization by augmenting the visitor profile with additional data.

You can personalize experiences with [!DNL Target] data right out of the box. But personalize more deeply by adding your own data into the mix. You can augment your profile with historical data from [!DNL Adobe Analytics] and real-time data out of [!DNL Adobe Audience Manager]. You can also use Customer Attributes, a feature within the People core service in [!DNL Adobe Experience Cloud], to easily bring CRM data, second-party partner data, and third-party purchased data into [!DNL Target]. 

For example, you can associate purchase data from your point-of-sale system with a visitor profile. To do that, just create a CSV file with up to 200 offline variables, and either upload it directly into [!DNL Adobe Experience Cloud] via a file upload, or use FTP to host and schedule your file to be updated regularly. Once your Customer Attributes are in [!DNL Adobe Experience Cloud], you can map them to [!DNL Experience Cloud] solutions like [!DNL Adobe Analytics] and [!DNL Target] where they will be available for analysis, testing, and personalization.

See [Custom attributes](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) for step-by-step instructions.

**Good to know**: Because [!DNL Target] is an open and agnostic platform that works well with different technologies, you can add CRM or purchased data in many different ways. That means you can choose a method that works best for your organization.

See [Methods to get data into Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) for more information.

## Tip 2: Personalize more deeply by blending Target audiences with other Adobe Experience Cloud audiences.

Blending audiences that live in different [!DNL Adobe Experience Cloud] solutions can give you a much broader understanding of your customers, as well as the ability to personalize more deeply. For example, although [!DNL Target] provides real-time audience data, [!DNL Adobe Analytics] provides historical audience data. Combining the two can help you identify when a customer’s behavior is consistent, and when there might be an opportunity to act on a new behavior. Simply click the drop-down menu next to “All Visitors” when creating an activity. Next, check the boxes of up to twenty audiences, click “Combine Multiple Audiences,” and click “Save.”

See [Combining multiple audiences](/help/c-target/combining-multiple-audiences.md) for step-by-step instructions.

**Good to know**: [!DNL Adobe Audience Manager] audiences are available in [!DNL Target] automatically. But [!DNL Adobe Analytics] audience sharing requires a bit of manual set up. Simply check the box labeled “Make this an Experience Cloud audience” during the audience building process in [!DNL Analytics]. Then from [!DNL Target], click “Import Experience Cloud audiences.”

## Tip 3: Export data from Target to use with third-party tools.

With response tokens, administrators can easily get data out of [!DNL Target] and into third-party tools. This can be helpful when you want to add your data to data collected in a survey tool. For example, if a survey shows a sample of a population scored an experience a “9,” and another scored an experience a “4,” you can use your data to see who saw experience A and who saw experience B. You can also use response tokens to export [!DNL Target] data to your internal data warehouse. Simply click “Administration,” then toggle the switch next to the desired Response Token to the on position. Next, create an activity. The data is then ready to be transferred to the third-party vendor. You can verify that [!DNL Target] is exporting the data using debugging tools.

See [Response tokens](/help/administrating-target/response-tokens.md) for step-by-step instructions.

**Helpful hint**: Before an administrator can activate a response token associated with a third party, a developer to needs to set up a partnership with that third-party company.

See [Response tokens](/help/administrating-target/response-tokens.md) for step-by-step instructions.

**Do this first**: Make sure you are using at.js version 1.1 or later. If you are using a previous version, you’ll see the response tokens, but at.js won’t be able to use them.

## Tip 4: Build audiences from these key variables to increase the value of your activity.

When building audiences for targeting or testing promotions and offers, first consider these variables:

* Behavioral. Site visit patterns and purchase patterns
* Referrer. Referring sites and campaigns
* Temporal. Times of day, days of the week, and seasonal factors
* Offline. Visit and purchase patterns at physical stores
* Environment. Country of origin, operating system, browser type

## Tip 5: Give users the level of access they need to do their job.

Make it easy to work with your organization’s data while keeping it safe. [!DNL Target Premium] allows administrators to control the level of access given to different internal and external teams.

See [Enterprise user permissions](/help/administrating-target/c-user-management/property-channel/property-channel.md) for more information.

**Helpful hint**: When adding users, if the name of a team member has not been previously added to your organization, such as might be the case with a third-party agency employee, entering their email address and password will trigger an email invitation to join a team’s workspace.

Using Target Standard? You can still [assign three levels of access](/help/administrating-target/c-user-management/c-user-management/user-management.md) for your users with read-only, editor, and approver roles!

## Tip 6: Discover how an offer performs across a customer journey by testing it across each page in the journey.

See how an offer, such as free shipping, performs during a customer journey that takes place across multiple pages on your website.

See [Multipage activity](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) for step-by-step instructions.

**Helpful hint**: Changing the URL after you’ve specified a page range will reset the experience. That means the variations you specified will no longer appear. If you need to change the URL, remember to re-define the experience.

## Tip 7: Test an offer with different audiences to discover if audiences hae different preferences.

With Experience Versions, you can run one test with variations for as many audiences as you like. For example, you can create a banner ad offering free shipping—with imagery and currency variations for customers in the U.S., U.K., and the U.A.E.—without having to run tests for three different audiences.

See for [Multiple experience audiences in an A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) and [Experience versions in Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) for step-by-step instructions.

## Tip 8: Save time by replicating activity experiences on similar pages.

Create a variation on one web page, such as a new button color, and automatically apply it to all pages that share the same template. You can specify pages, or apply the variations to all similar pages across your website. 

See [Include the same experience on similar pages](/help/c-experiences/c-visual-experience-composer/temtest.md) for step-by-step instructions.

## Tip 9: Reduce clutter in your Audience Library by creating one-time audiences.

If you’re targeting a segment you know won’t target again--for example, customers affected by an unexpected weather event--creating a one-time-use audience can help you get the job done without adding clutter to your Audience Library. This makes it easier to find audiences you use over and over again. 

See [Create an activity-only audience](/help/c-target/creating-activity-only-audience.md) for step-by-step instructions.

**Highly requested capability**: Our customers asked us to make it possible to keep single-use audiences from being automatically saved to the Audience Library. Now, they no longer have to manually delete audiences to keep their libraries organized.

## Tip 10: Run simple tests faster by not putting them through the standard QA process.

There is nothing worse than having an activity ready to go and then waiting weeks for it to complete the standard QA process. You can QA most activities by simply passing around a few QA links to colleagues to try them on various browsers. You will most likely want to do more QA testing for efforts that dramatically change site function, but in reality, you should have fewer of those activities and far more of the more basic activities. Adding better rights controls so that fewer people can push things fully live also adds meaningful limits and lets you accomplish what you need to without sacrificing speed and efficiency. Another option is to have a designated IT resource to provide timely oversight of the QA process.

See [Activity QA](/help/c-activities/c-activity-qa/activity-qa.md) for step-by-step instructions.

## Tip 11: Run tests on high-traffic pages so they reach statistical significance quicker.

Many marketers launch optimization programs for audience segmentation and targeting without checking whether traffic levels and audiences represented will provide significant results within the testing time frame for their optimization and conversion goals. To avoid this common mistake, answer these questions in advance:

* How many daily unique visitors does the page have?
* What is the conversion rate for the page?
* How long do you anticipate needing to run the test before you can confidently call it complete?

**Helpful Tip**: Use the Target [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html) to help determine the sample size needed for a successful test.

## Tip 12: Design simpler tests to make sure you can create and implement them.

After considering all aspects of how to design a test, a plan can get very complex. Based on where your business is with testing, and your group’s ability to design, code,execute, and analyze the results, determine if the test seems too ambitious. If it is, be prepared to reduce its scope and complexity. Better to start small than not perform the test at all. You can’t deliver impactful lift if you never launch the test. It’s important to balance the aspirations of the team with the realities of your resources and abilities.

## Tip 13: Break complex tests into smaller test activities to make them achievable.

Instead of developing one large test with multiple variables and complex development, develop a less complex series of smaller tests with minimal variables. This allows for a deeper understanding of test performance based on specific variables. It also reduces possible technical issues that come with the development of larger projects.

![Break complex tests illustration](/help/c-intro/assets/break-complex-tasks.png)

## Tip 14: Maximize your test impact by testing closer to the end of the conversion funnel.

Testing as close to the page where visitors click Complete Purchase, Submit Application, or otherwise complete a conversion tends to deliver the most impactful results. Visitors who reach the end of the funnel are more qualified, have invested more time, and are ready to purchase, so testing insights about their preferences and actions can help you make profitable changes. Because pages on the purchase path are critical to conversion rates, tests being conducted on those pages should be socialized to key stakeholders before rolling them out.

![Conversion funnel illustration](/help/c-intro/assets/conversion-funnel.png)

## Tip 15: Constantly update your tests to make iterative improvements.

If your hypothesis did not prove to be true, think of ways to improve your test. Remember that even if none of the tested experiences performed better, your experiment wasn’t a waste of time. A successful test doesn’t always mean a boost in revenue or conversions. If the test actually supported your hypothesis, then you’re on your way to developing a general theory. But even when you do have a clear winning result, don’t stop there. Too often, marketers make the mistake of testing once and then banking on those results without really understanding what led to the success. Instead, plan to iterate on those results to figure out why the front-runner was ahead. This will lead you to deeper insights that you can use in future campaigns.

## Tip 16: Compare tests and personalization activities for ideas to improve targeting.

Comparing the conversion performance of different audiences within different tests at different locations can help focus and refine a company’s optimization strategy. Use test comparisons to identify which audiences are most valuable to test, which should receive targeted experiences, and what types of experiences are most likely to elicit a response. 

For example, a financial services customer ran a promotional campaign for a credit card that involved professional sporting event incentives. Through partial factorial multivariate testing of its landing pages, the customer was able to optimally balance messaging about credit card benefits with sporting incentives to target distinct audiences from its customer base. This approach allowed the company to capitalize on and maximize conversion during a time-sensitive window surrounding a major sporting event.

## Tip 17: Make tests useful by only launching them if you know you can act of the data.

A test is pointless if you aren’t clear about how you are going to act on the data. This includes knowing your key success metric, what needs to happen to push a winner, how you will follow up on test results, and what you will do with the audience information. For a speedy and successful test, it’s vital that every group involved in the test (developers, creatives, testing specialists, and others) is aware of its role before the test launch.

## Tip 18: Before launching a test, be sure the business supports pushing the winner.

Successful optimization organizations believe in the concept of testing and understand that their professional opinions about what experience will win the test don’t always prove true. They determine the winner based on a solid foundation of data, and are eager and willing to push the winning experience live after the results are in, even if it’s not in line with their expectations or seems counterintuitive. 

For example, an Adobe healthcare services customer recently demonstrated the value of testing by showing how a hero banner that the team had considered a slam dunk actually negatively impacted conversion. If your organization hasn’t yet fully embraced testing, it’s best to first conduct simpler, smaller scope tests so that changes from test results can be made incrementally.

## Tip 19: Let everyone know you've launched a test to avoid concern when the site changes.

One of the benefits of setting up your activities to use QA parameters is that you can share those links with everyone on your team. You make more people aware of the activity and ensure they don’t assume the site isn’t functioning properly when they hit a test variant. 

After you finish your tests, communicating campaign launches, test results, and especially lessons learned helps you build awareness of and interest in the test results. Sharing the results with everyone in the organization also avoids retesting a hypothesis, educates everyone about what works, and helps them fundamentally challenge their own ideas of what works based on what you’ve found. It’s a good idea to prepare a template that you use each time for sharing your findings and key learnings.
Then consider creating a sharable book or Microsoft PowerPoint deck that cumulatively captures these learnings.

## Tip 20: Tap into mobile functionality to create more innovative mobile activities.

The tablet and smartphone user experiences need to focus on touch-driven controls as the primary visitor interaction rather than mouse clicks and keyboard controls. Take advantage of mobile display controls, including finger swipe, touch, drag, pinch, and zoom. Use simple, large buttons to designate interactions and navigation,such as a large shopping cart or video play button. If designing for mobile retail, incorporate rich product visualization that is optimized for the device type. Always look for opportunities to shift the user experience focus to embedded, large viewers or full-screen interactive zoom and pan, 360-degree spin, and enhanced video functionality.

## Tip 21: Help mobile visitors find what they want by optimizing mobile search.

Mobile users have high intent. The majority of them use search before they do anything else on m-commerce sites, making mobile site search optimization crucial. To improve your search engine optimization (SEO) for mobile, use explicit navigational cues for easy browsing. Also, implement auto-suggest and autocorrect in search input boxes to address the difficulty of mobile typing. Provide compelling, relevant search results optimized for screen size and location.

## Tip 22: Reach mobile audiences better using time-of-day targeting for mobile SEM campaigns.

Understand how and when to reach your audience and how to better manage your daily advertising spend by “day parting” your mobile campaigns into different segments throughout the day.

Many marketers make the mistake of failing to allocate enough budget to capture that share of voice in the hours when the use of particular devices is heaviest, thus leaving a lot of revenue and leads on the table. 

For instance, tablet usage typically spikes in the evening hours, and many users browse while watching television. In contrast, smartphone users typically access content on the go. Peak conversion times also vary by industry, so it’s important to understand when your unique customers are most likely to act.

## Keep in mind

Consider the following ideas before we move on to the next chapter: "Inspiration for testing and personalization activities."

### When you create your tests, don't decorate, be intentional.

* Control the flow with intentional Eye Paths focused on conversion points.
* Ensure you use your Real Estate to your advantage.
* Leverage Image Focus to ensure images are not decoration, but are working for you.
* Reduce clutter, friction, and blur with Simplified Copy.
* Be sure you have Effective Calls To Actions when you need the user to take action.
* Add credibility through User Generated Content where possible.

### Simplify your website.

* Don’t “make” customers read. They won’t.
* Make it easy to scan.
* Use bulleted copy blocks.
* Ensure your copy follows a clear, sequential thought process.

### Use effective Call to Actions (CTAs)

* Put yourself in the customer’s shoes.
* Use action-oriented language.
* Consider the motivation for conversion.
* Address the result of conversion.
* Make sure CTAs are seen!
