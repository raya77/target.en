---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Take a high-level look at Adobe Target. Learn about available activities, channels, implementation, integrations, and more.
title: Where Can I Find a High-level Introduction to Target?
feature: Overview
exl-id: 19238d4c-b7e1-418d-96e5-c46a3769f7bf
---
# Chapter 2: Adobe Target at a glance

Before you get started using [!DNL Adobe Target], it might be helpful to get a high-level overview of the solution. In this chapter, get to know the solution’s key capabilities, brand touchpoints on which you can use it, implementation options, important user interface features and workflows, governance features, and its role in the overall [!DNL Adobe Experience Cloud]. Unless noted as [!DNL Adobe Target Premium] features, the items described in this chapter are available with both [!DNL Adobe Target Premium] and [!DNL Adobe Target Standard]. For more information, see [Introduction to Target](/help/c-intro/intro.md).

## Capabilities and activities

Testing and personalization are the two broad types of capabilities that [!DNL Target] offers and that you can use when creating an “activity” in [!DNL Target]. You might see the term “testing” used interchangeably with “optimization,” and “personalization” used interchangeably with “targeting.”

In a testing activity, you compare one variation of a digital experience against one or more other variations to discover that one that causes the most visitors to take a desired action. [!DNL Target] offers the following testing capabilities: A/B testing, Multivariate testing (MVT), and Auto-Allocate.

With a personalization activity, you deliver a digital experience that is tailored to a specific group of visitors or to each individual visitor. [!DNL Target] offers these personalization capabilities: Experience Targeting, Auto-Target, Automated Personalization, and Recommendations.

For a more in-depth understanding of when and how to use each capability, see [Target activity types](/help/c-activities/target-activities-guide.md).

|Activity type|Details|
| --- | --- |
|A/B Testing|Compare two or more variations of your experiences or offers on your website, or other digital customer touchpoint to see which variation most improves key business measures during a pre-specified test period. A/B tests are well-suited for large changes, such as new web page layouts, different approaches to site navigation, or drastically different treatments of individual elements of a digital experience like copy, images, and call-to-action buttons. [Learn more](/help/c-activities/t-test-ab/test-ab.md).|
|Auto-Allocate|Identify the best-performing experience among two or more experiences, and automatically re-allocate more traffic to the winner to increase conversions while the test continues to run and learn. Uses Artificial Intelligence powered by [!DNL Adobe Sensei]. [Learn more](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).|
|Auto-Target<br>(Premium)|Leverage Adobe Sensei AI in [!DNL Target] to determine and deliver the best experience of several to each visitor based on his or her individual customer profile and the behavior of previous visitors with similar profiles. Auto-Target enables personalization at scale. [Learn more](/help/c-activities/auto-target/auto-target-to-optimize.md).|
|Automated Personalization<br>(Premium)| Use advanced machine learning algorithms and automation powered by [!DNL Adobe Sensei] to review different combinations of images, copy, and other elements in an offer and deliver the best combination to each visitor based on which best achieves business goals, such as increased conversions or revenue per visitor. [Learn more](/help/c-activities/t-automated-personalization/automated-personalization.md).|
|Experience Targeting (XT)|Deliver content to a specific audience based on a set of user-defined rules and criteria. **[!UICONTROL Experience Targeting]** is valuable for targeting a specific experience or content to a particular audience when you understand that an audience is valuable and have a good sense of what experience resonates with them. [Learn more](/help/c-activities/t-experience-target/experience-target.md).|
|Multivariate Testing (MVT)|Compare all possible combinations of variations of elements on your page or digital experience--for example of three different background images, two variations of copy, and two different button colors. MVT determines which combination performs the best for a specific audience and which elements most impact the results. [Learn more](/help/c-activities/c-multivariate-testing/multivariate-testing.md).|
|Recommendations<br>(Premium)|Use Adobe Sensei AI to automatically suggest products or content that might interest your customers based on their previous activity and that of other customers. [Learn more](/help/c-recommendations/recommendations.md).|

## Channels

You can use [!DNL Target] to test and personalize digital experiences just about anywhere--traditional digital touchpoints like your web site, mobile site, and mobile app, but also on touchpoints like kiosks, email, IoT devices, gaming consoles, and even voice assistants like Alexa and Cortana. Many companies start using [!DNL Target] on their web site. However, recent research indicates that more people visit brands from their mobile devices. Optimizing your mobile channels is now essential. Ideally, you’ll connect the visitor’s experiences across all your touchpoints to deliver a seamless, consistent experience.

|Channel|Details|
| --- | --- |
|Website|[!DNL Target] can be used to run A/B Testing, Multivariate Testing, Experience Targeting, Auto-Allocate, Auto-Target, Automated Personalization, and Recommendations activities on pages of your multi-page, single page application (SPA), and mobile websites to improve visitor and customer engagement, increase conversions, and increase revenue.|
|Mobile Web|[!DNL Target] can be used to run all the same activity types that you run on your website on your mobile website pages to similarly improve visitor and customer engagement, increase conversions, and increase revenue.|
|Mobile App|[!DNL Target] can be used to test and personalize mobile app experiences based on user behavior and mobile context. [!DNL Target] lets you deliver interactions that engage and convert through iterative testing as well as Experience Targeting and AI-powered personalization. To use [!DNL Target] on your mobile app, you must use the Adobe Mobile Services SDK.|
|IoT/Everywhere|[!DNL Target] offers a server-side implementation so that you can use the same testing and personalization capabilities in activities that you use on your traditional website, mobile site, and mobile apps in emails and on touchpoints that lack a browser or don’t use JavaScript code. For example, so you could test and personalize kiosks, set-top boxes, gaming consoles, voice assistants, and other non-traditional touchpoints.|

## Implementations

Many of you might want to use [!DNL Target] to test and personalize on your many different digital touchpoints, including traditional web and mobile touchpoints, but also touchpoints that lack a browser or don’t use JavaScript code. In some cases, internal or external policy requires you to have additional levels of control and security. You might also have processes that need to run on a backend server for performance reasons. To meet this wide variety of uses, we give you the ability to implement [!DNL Target] in different ways: client-side, server-side, or a combination of the two.

|Implementation type|Details|
| --- | --- |
|Client-side|With this implementation of [!DNL Target], [!DNL Target] delivers the experiences associated with an activity directly to the client browser. The browser decides which experience to display and displays it. With client-side, you can use a WYSIWYG editor, the **[!UICONTROL Visual Experience Composer]** (VEC), or a non-visual interface, the **[!UICONTROL Form-based Experience Composer]**, to create your test and personalization experiences. [Learn more](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).|
|Server-side| In this type of [!DNL Target] implementation, a client device makes a request for an experience through your server, your server sends that request to [!DNL Target], [!DNL Target] sends back the response to your server, and your server makes the decision on what experience to deliver to the client device for it to render. The experience does not need to display in a browser; it can display in an email or kiosk, via a voice assistant, or through some other non-visual experience or non-browser-based device. Because your server sits between the client and [!DNL Target], this type of implementation is also ideal if you need greater control and security or have complex backend processes that you want to run on your server. [Learn more](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).|
|Hybrid implementation| In this implementation, you choose the implementation approach that works best for a given use case. For example, you might use a client-side implementation to A/B test an offer in a hero banner on the home page, but also use a server-side implementation to determine the internal search results to display on a client browser, experience to display on a smart car dashboard, or voice response to deliver from a voice assistant.|

## Activity elements

In [!DNL Target], you can create a personalization activity, an optimization activity, or an activity that optimizes your personalization approach. Each activity has key elements--the experiences or offers you’re testing or personalizing, the audiences or individuals to whom you’re delivering an experience, the metrics by which you measure the impact of the activity, and the reports that visually display that impact.

|Element type|Details|
| --- | --- |
|Experiences|An offer, image, text, button, video, combination of these various elements on a page, an entire web page, or a set of pages that perhaps form a purchase funnel or some other logical sequence of pages. It can also be the response of a voice assistant, a customer service script, or even a personalized flavor from a drink machine. You test or personalize experiences in [!DNL Target] activities. [Learn more](/help/c-experiences/experiences.md).|
|Offers|A block of content that might contain images, text, HTML, links, video, a call to action button, a voice assistant response, or any other type of content. An offer might be for a discount, free shipping, and so on. An offer can be displayed on a web page, but might also be experienced on any customer touchpoint, such as a voice assistant or gaming console. When you test an offer, you measure its success in comparison to other offers or no offer. [Learn more](/help/c-experiences/c-manage-content/manage-content.md). |
|Audiences| A group of people with the same characteristics, such as a new visitor, a returning visitor, or returning visitors from the Midwest. The Audience feature allows you to target different content and experiences to specific audiences to optimize your digital marketing by displaying the right messages to the right people at the right time. If a visitor is identified as part of a target audience, [!DNL Target] determines which experience to display, based on criteria defined during activity creation. [Learn more](/help/c-target/target.md). |
|Success metrics|Key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity. For example, you can determine if a new offer increases your revenue per visitor or adding an item to a shopping cart. Success metrics can be useful for discovering issues with registration, ordering, or purchase funnels, but also simply with visitor or customer engagement. [Learn more](/help/c-activities/r-success-metrics/success-metrics.md).|
|Reports|Information about the progress and results of your activities that help you make decisions based on your data. Report data can help you decide when to end a test, show you which experience of offer is the winner, and provide insights or learnings you need to determine next actions. [Learn more](/help/c-reports/reports.md).|

## Activity-creation tools

[!DNL Target] provides you with three main ways to set up your testing and personalization activities, the [!UICONTROL Visual Experience Composer] (VEC), the [!UICONTROL Form-based Experience Composer], and the [!UICONTROL Single Page Application (SPA) Visual Experience Composer]. Both guide you through the activity setup process in three-steps—defining the experiences, selecting or defining the audiences, and selecting the primary and secondary success metrics by which you’ll measure the results of your activity.

|Tool|Details|
| --- | --- |
|[!UICONTROL Visual Experience Composer] (VEC)|A WYSIWYG user interface that lets you easily create and test personalized experiences and offers in the site context. You can create experiences and offers for [!DNL Target] activities by dragging and dropping, swapping, and modifying the layout and content of a web page (or offer) or mobile web page. [Learn more](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md).|
|[!UICONTROL Form-based Experience Composer]|A non-visual experience and offer creation interface that’s useful in creating experiences for use in A/B tests, Experience Targeting, Automated Personalization, and Recommendations activities when the Visual Experience Composer is not available or practical for use. For example, you might use the form-based composer to create experiences and offers for delivery in emails, kiosks, and voice assistants. [Learn more](/help/c-experiences/form-experience-composer.md).|
|[!UICONTROL Single Page Application (SPA) Visual Experience Composer]|The VEC for SPAs enables marketers to create tests and personalize content on SPAs in a do-it-yourself fashion without continuous development dependencies. The VEC can be used to create A/B Test and Experience Targeting (XT) activities on popular frameworks, such as React and Angular. [Learn more](/help/c-experiences/spa-visual-experience-composer.md).|

## Governance and control

To provide the right people the right roles and associated levels of access and permissions to [!DNL Target], we have an administrative console. For [!UICONTROL Target Premium] users, we offer more detailed governance and control
with [!UICONTROL Enterprise Permissions].

|Tool|Details|
| --- | --- |
|[!UICONTROL Adobe Admin Console for Enterprise]|Add users to Adobe Target and assign permissions from the Adobe Admin Console. [Learn more](/help/administrating-target/c-user-management/c-user-management/user-management.md).|
|[!UICONTROL Enterprise Permission]s<br>(Premium)| A means of formal administering enterprise-wide user access to [!DNL Target]. Add users to [!DNL Target], assign permissions based on their roles, and create workspaces for teams based on different departments, global locations, channel, and other logical groupings. You can assign users the roles of Observer, Editor, Publisher, or Approver. [Learn more](/help/administrating-target/c-user-management/property-channel/property-channel.md).|

## Integrations

[!DNL Target] can integrate with many first-, second-, and third-party systems. These
integrations can be valuable for giving you access to visitor and customer data available from those systems for use in creating audiences for testing and for personalization. As part of [!DNL Adobe Experience Cloud], [!DNL Target] integrates tightly with [!DNL Experience Cloud] solutions and its Core Services.

|Integration|Details|
| --- | --- |
|Adobe Experience Cloud|[!DNL Target] has embedded capabilities with other [!DNL Adobe Experience Cloud] solutions to personalize experiences at scale. Leverage the power of [!DNL Target] together with [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), [Experience Cloud Audiences](/help/c-integrating-target-with-mac/mmp.md), [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM), and [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM).|
|Target APIs (Premium)|[!UICONTROL Target] offers more than 40 APIs that you can use to integrate Adobe Target with first-, second-, and third-party systems. [Learn more](/help/api/api-overview.md).|

## Keep in mind

Consider the following ideas before we move on to the next chapter: "Develop your testing and personalization ideas."

### Best practices for optimization

* **Good strategy**: What is our objective and hypothesis? Are they aligned? For example, we want to increase loan application submissions, so we hypothesize that reducing the number of fields in application form will do that.
* **Disciplined methodology** Are we starting to test in the right places? For example,you need locations that have enough traffic and that impact the metrics that matter    to the business.
* **Proper setup** Is our activity set up to achieve our objective? For example, if we are trying to increase loan application submissions, we should target people interested in loans and measure clicks of the “Submit” button.
* **Thorough analysis**: Did the test activity run to completion? What do the results say? Run your activity until it achieves between 95% and 99% statistical confidence. Document why you think the winning experience won and apply the learning elsewhere.
* **Iterative testing**: Are we building on the learnings of previous activities? If you find a winning tactic, try to improve on it or make changes that work with it to further improve your success metric.

### Opinions can negatively affect your results

* Opinions that can negatively impact your effectiveness. Highest Paid Person’s Opinion (HIPPO), attitudes, biases. For example, the CEO wants to reduce the size of the search box to make more room on each page. We should test to make sure that it doesn’t reduce the number of searches.
* Are you acting on opinions? I don’t like the way that test looks. The customer won’t like this experience at all. While intuition is useful, A/B testing has proven time and again that it’s not always spot on.
* Or do you have an optimization mindset? I’m excited to see which experience wins. Do we have enough options to test?

### Assumptions can also negatively affect results

* Assumptions that can negatively impact your effectiveness. Herd mentality (this is how our competitors are doing it). For example, all our competitors use hero banners with rotating images, so we should, too.
* Assuming we know why something is or isn’t working. Assuming we don’t need to test something. For example, we always list hotel rooms in order of highest to lowest priced as the default.
* Are you acting on assumptions? We don’t need to test that, we’ve checked analytics. (Yes, but there may be more to the story than analytics reveals.)
* Or do you have an optimization mindset? We test everything.
