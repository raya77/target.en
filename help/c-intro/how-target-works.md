---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;search engine optimization;search engine optimization;seo;edge clusters, central clusters;at.js;mbox.js;
description: Learn about how Adobe Target works, including information about the Target JavaScript libraries (at.js and AEP Web SDK), Adobe data centers, and SEO testing.
title: How Does Target Work?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
---
# How Adobe Target works

Learn how [!DNL Adobe Target] works, including information about the [!DNL Adobe Experience Platform Web SDK] and JavaScript libraries (at.js and mbox.js). This article also introduces the various activity types you can create using [!DNL Target]. You can also learn about the [!DNL Target] edge network, Search Engine Optimization (SEO), and how [!DNL Target] detects bots.

## Target Platform Web SDKs and JavaScript libraries {#libraries}

[!DNL Target] integrates with websites using the [!DNL AEP Web SDK] or JavaScript libraries:

* **Adobe Experience Platform Web SDK:** The [AEP Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) is a new client-side JavaScript library. The AEP Web SDK lets customers of [!DNL Adobe Experience Cloud] interact with the various services in the [!DNL Experience Cloud] (including [!DNL Target]) through the [!DNL AEP] Edge Network. Adobe recommends that all new [!DNL Target] customers implement the [!DNL AEP Web SDK].
* **at.js:** The [at.js library](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) is an implementation library for [!DNL Target]. The at.js library improves page-load times for web implementations and provides better implementation options for single-page applications. at.js is updated frequently with new capabilities. Adobe recommends that all customers using at.js update their implementations to the [latest version of at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).
* **mbox.js:** The [mbox.js library](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) is the legacy implementation library for [!DNL Target]. The mbox.js library is supported until March 31, 2021; however, there will be no feature updates.

>[!IMPORTANT]
>
>All customers should migrate to the [!DNL AEP Web SDK] or to the latest version of at.js. For more information, see [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) or [Migrate to at.js from mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

Reference the [!DNL AEP Web SDK] or at.js on every page on your site. For example, you can add one of these libraries to your global header. Alternatively, consider using [Adobe Platform Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html) to implement [!DNL Target].

The following resources contain detailed information to help you implement the AEP Web SDK or at.js:

* [Adobe Experience Platform Web SDK Extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Implement Target using Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

Each time a visitor requests a page that has been optimized for [!DNL Target], a request is sent to the targeting system. The request helps to determine what content to serve to that visitor. This process occurs in real time. Every time a page is loaded, a request for the content is made and fulfilled by the system. The content is governed by the rules of marketer-controlled activities and experiences and is targeted to the individual site visitor. Content is served that each site visitor is most likely to respond to, interact with, or ultimately purchase. Personalized content helps maximize response rates, acquisition rates, and revenue.

In [!DNL Target], each element on the page is part of a single experience for the entire page. Each experience can include multiple elements on the page.

The content that is displayed to visitors depends on the type of activity you create:

### A/B Test

The content that displays in a basic A/B test is randomly chosen from the experiences you assign to the activity. You can assign the traffic allocation  percentages for each experience. As a result of this random splitting of traffic, it can take a significant amount of initial traffic before the percentages even out. For example, if you create two experiences, the starting experience is chosen randomly. If there is little traffic, it's possible that the percentage of visitors can be skewed toward one experience. As traffic increases, the percentages equalize.

You can specify percentage targets for each experience. In this case, a random number is generated and that number is used to choose the experience to display. The resulting percentages might not exactly match the specified targets, but more traffic means that the experiences should be split closer to the target goals.

1. A customer requests a page from your server and it displays in the browser.
2. A first-party cookie is set in the customer's browser to store customer behavior.
3. The page calls the targeting system.
4. Content displays based on the rules of your activity.

See [Create an A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) for more information.

### Auto-Allocate

Auto-Allocate identifies a winner among two or more experiences. Auto-Allocate automatically reallocates more traffic to the winning experience, which helps to increase conversions while the test continues to run and learn.

See [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) for more information.

### Auto-Target (AT)

Auto-Target uses advanced machine learning to select from multiple high-performing marketer-defined experiences. Auto-Target serves the most tailored experience to each visitor. Experience delivery is based on individual customer profiles and the behavior of previous visitors with similar profiles. Use Auto-Target to personalize content and drive conversions.

See [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md) for more information.

### Automated Personalization (AP)

Automated Personalization (AP) combines offers or messages, and uses advanced machine learning to match different offer variations to each visitor. Experience delivery is based on individual customer profiles to personalize content and drive lift.

See [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) for more information.

### Experience Targeting (XT)

Experience Targeting (XT) delivers content to a specific audience based on a set of marketer-defined rules and criteria.

Experience Targeting, including geotargeting, is valuable for defining rules that target a specific experience or content to a particular audience. Several rules can be defined in an activity to deliver different content variations to different audiences. When visitors view your site, Experience Targeting (XT) evaluates them to determine whether they meet the criteria you set. If they meet the criteria, they enter the activity and the experience designed for qualifying audiences is displayed. You can create experiences for multiple audiences within a single activity.

See [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) for more information.

### Multivariate Test (MVT)

Multivariate Testing (MVT) compares combinations of offers in elements on a page to determine which combination performs the best for a specific audience. MVT helps identify which element most impacts the activity's success.

See [Multivariate Test](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) for more information.

### Recommendations

Recommendations activities automatically display products or content that might interest your customers based on previous user activity or other algorithms. Recommendations help direct customers to relevant items they might otherwise not know about.

See [Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) for more information.

## The edge network {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

An “Edge” is a geographically distributed serving architecture that ensures optimum response times for visitors requesting content, regardless of where they are located around the world.

To improve response times, [!DNL Target] Edges host only activity logic, cached profiles, and offer information. 

Activity and content databases, [!DNL Analytics] data, APIs, and marketer user interfaces are housed in Adobe’s Central Clusters. Updates are then sent to the [!DNL Target] Edges. The Central Clusters and Edge Clusters are automatically synced to continually update cached activity data. All 1:1 modeling is also stored on each edge, so those more complex requests can also be processed on the edge.

Each Edge Cluster has all the information required to respond to the visitor's content request and track analytics data on that request. Visitor requests are routed to the nearest Edge Cluster.

For more information, see the [Adobe Target Security Overview](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf) white paper.

The [!DNL Target] solution is hosted on Adobe-owned and Adobe-leased data centers around the world.

Central Cluster locations contain both a data collection center and a data processing center. Edge Cluster locations contain only a data collection center. Each report suite is assigned to a specific data processing center.

Customer site activity data is collected by the closest of seven Edge Clusters. This data is directed to a customer’s pre-determined Central Cluster destination (one of three locations: Oregon, Dublin, Singapore) for processing. Visitor profile data is stored on the Edge Cluster closest to the site visitor. Edge clusters locations include the Central Cluster locations and Virginia, Amsterdam, Sydney, Tokyo, and Hong Kong.

Instead of responding to all targeting requests from a single location, requests are processed by the Edge Cluster closest to the visitor. This process helps mitigate the impact of network/Internet travel time.

![Types of Target servers map](/help/c-intro/assets/target-servers.png)

[!DNL Target] Central Clusters, hosted on Amazon Web Services (AWS), include:

* Oregon, USA
* Dublin, Ireland
* Republic of Singapore

[!DNL Target] Edge Clusters, hosted on AWS, include:

* Mumbai, India
* Tokyo, Japan
* Virginia, USA
* Oregon, USA
* Sydney, Australia
* Dublin, Ireland
* Republic of Singapore

The [!DNL Target Recommendations] service is hosted in an [!DNL Adobe] data center in Oregon.

>[!IMPORTANT]
>
>[!DNL Adobe Target] currently doesn’t have an Edge Cluster in China and the visitor performance remains limited for [!DNL Target] customers in China. Because of the firewall and the lack of Edge Clusters within the country, the experiences of sites with [!DNL Target] deployed can be affected. Experiences can be slow to render and page loads can be affected. Also, marketers might experience latency when using the [!DNL Target] authoring UI.

You can allowlist [!DNL Target] Edge Clusters, if desired. For more information, see [allowlist Target edge nodes](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Protected user experience {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe ensures that the availability and performance of the targeting infrastructure is as reliable as possible. However, a communication breakdown between a visitor’s browser and Adobe’s servers can cause an interruption in content delivery.

To safeguard against service interruptions and connectivity issues, all locations are set up to include default content (defined by the client). This default content is displayed if the user’s browser cannot connect to [!DNL Target].

No changes are made to the page if the user’s browser cannot connect within a defined timeout period (by default: 15 seconds). If this timeout threshold is reached, default location content is displayed.

Adobe protects the user experience by optimizing and safeguarding performance.

* Adobe ensures performance benchmarks based on industry standards, which are guaranteed by the Adobe Service Level Agreement. 
* The Edge Network ensures timely data delivery. 
* Adobe employs a multi-tiered approach to securing its applications to provide the highest level of availability and reliability for customers. 
* [!DNL Target] Consulting offers implementation assistance and ongoing product support.

## Search Engine Optimization (SEO) friendly testing {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] aligns with search engine guidelines for testing.

Google encourages user testing. Google states in its documentation that A/B and Multivariate Testing does not harm organic search engine rankings if you follow certain guidelines.

For more information, see the following Google resources:

* [Website testing and Google Search](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html) 
* [Experiments and Cloaking](https://support.google.com/analytics/answer/2576845?hl=en&ref_topic=1745207)

Guidelines were presented in a [Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html) post. Although the post dates back to 2012, it remains Google's most recent statement on the matter and the guidelines remain relevant.

* **No cloaking**: Cloaking is showing one set of content to your users and a different set of content to search engine bots. Cloaking is accomplished by specifically identifying bots and purposely feeding them different content.

  [!DNL Target], as a platform, has been configured to treat search engine bots the same as any user. As a result, bots can be included in activities if the bots are randomly selected and "see" the test variations. 

* **Use rel="canonical"**: Sometimes an A/B test must be set up using different URLs for the variations. In these instances, all variations should contain a `rel="canonical"` tag that references the original (control) URL. As an example, suppose that Adobe is testing its home page using different URLs for each variation. The following canonical tag for the home page would go in the `<head>` tag for each of the variations:

  `<link rel="canonical" href="https://www.adobe.com" />` 

* **Use 302 (temporary) redirects**: In the instances where separate URLs are used for the variation pages in a test, Google recommends using a 302 redirect to direct traffic into the test variations. The 302 redirect tells the search engines that the redirect is temporary and are active only as long as the test is running.

  A 302 redirect is a server-side redirect, and [!DNL Target], along with most optimization providers, uses client-side capabilities. Therefore, redirecting is an area where [!DNL Target] is not fully compliant with Google's recommendations. This practice, however, impacts only a small fraction of tests. The standard approach for running tests through [!DNL Target] calls for changing content within a single URL, so no redirects are necessary. There are instances when clients must use multiple URLs to represent their test variations. In these instances, [!DNL Target] uses the JavaScript `window.location` command. This command directs users to test variations, which does not explicitly signify whether the redirect is a 301 or 302.

  Adobe continues to look for viable solutions to completely align with search engine guidelines. For those clients that must use separate URLs for testing, Adobe is confident that proper implementation of the canonical tags mitigates the risk associated with this approach. 

* **Run experiments only as long as necessary**: Adobe believes "as long as necessary" to be as long as it takes to reach statistical significance. [!DNL Target] [provides best practices](https://docs.adobe.com/content/target-microsite/testcalculator.html) to determine when your test has reached this point. Adobe recommends that you incorporate the hardcoded implementation of winning tests into your testing workflow and allot the appropriate resources.

  Using the [!DNL Target] platform to "publish" winning tests is not recommended as a permanent solution. If the winning test is published for 100% of users 100% of the time, this approach can be used while the process of hardcoding the winning test is completed.

  It's important to consider what your test has changed as well. Simply updating the color of buttons or other minor non-text-based items on the page does not influence your organic rankings. Changes to text should be hardcoded, however.

  It's also important to consider the accessibility of the page you're testing. If the page is not accessible to search engines and was never designed to rank in organic search in the first place, then none of the considerations above apply. An example is a dedicated landing page for an email campaign.

Google states that following these guidelines "should result in your tests having little or no impact on your site in search results."

In addition to these guidelines, Google also provides one more guideline in the documentation to their Content Experiments tool:

* "Your variation pages should maintain the spirit of the content on your original pages. Those variations shouldn't change the meaning of or your user's general perception of that original content."

Google states as an example that "if a site's original page is loaded with keywords that don't relate to the combinations being shown to users, we may remove that site from our index."

Adobe feels that it would be difficult to unintentionally change the meaning of the original content within test variations. However, Adobe recommends being aware of the keyword themes on a page and maintaining those themes. Changes to page content, especially adding or deleting relevant keywords, can result in ranking changes for the URL in organic search. Adobe recommends that you engage with your SEO partner as part of your testing protocol.

## Bots {#bots}

Adobe [!DNL Target] uses the [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) metric "isRobot" to detect known bots based on the User Agent String passed in the Request Header. 

>[!NOTE]
>
> For [!DNL Server-Side] requests, the value passed in the [Request's "Context" node](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) is given precedence over the User Agent String for bot detection. 

Traffic that is identified as being generated by a bot is still served content. Bots are treated like a regular user to ensure that [!DNL Target] is in line with SEO guidelines. Using bot traffic can skew A/B tests or personalization algorithms if they are treated like normal users. Therefore, if a known bot is detected in your [!DNL Target] activity, the traffic is treated slightly differently. Removing bot traffic provide a more accurate measurement of user activity.

Specifically, for known bot traffic [!DNL Target] does not:

* Create or retrieve a visitor profile
* Log any profile attributes or execute profile scripts
* Look up Adobe Audience Manager (AAM) segments (if applicable)
* Use bot traffic in modeling and serving personalized content for Recommendations, Auto-Target, Automated Personalization, or Auto-Allocate activities
* Log an activity visit for reporting
* Log data to be sent to the [!DNL Adobe Experience Cloud] platform
