---
keywords: multivariate test;mvt;mvt plan;multivariate test plan
description: Learn how to plan a Multivariate Tests in Adobe [!DNL Target] so you can create a successful test.
title: How Do I Plan a Multivariate Test?
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
---
# Plan a Multivariate Test

[!UICONTROL Multivariate Tests] (MVT) in [!DNL Adobe Target] require some planning before you can create a successful test.

MVT require sufficient traffic to generate useful results. Before setting up your test, you should be aware of the amount of traffic you typically get, including the number of impressions and conversions. Having this information will reduce the likelihood of designing a test with requirements that exceed your site's traffic.

It is recommended that elements be independent of each other. (For example, do not test your layout and content in the same test.)

Examine the HTML code for the pages you want to test. Make sure the HTML elements on your site do not have duplicate DOM IDs. Duplicate IDs can result in the same piece of content being delivered to more than one location.

Plan to test the elements on your page that are likely to produce significant results. For example, a banner or a hero image is probably going to lead to more conversions than a change in the footer. Including less-influential elements in your test only increases the amount of traffic and time required to test the more prominent elements on the page.

Finally, before you create your test, you should create the content you want to test. Understand the content differences for each offer, and create any images, text, and HTML offers that you expect to use in the test. 

## Training video: Creating Multivariate Tests (9:25) ![Tutorial badge](/help/main/assets/tutorial.png)

This video demonstrates how to plan and create a multivariate test using the Target three-step guided workflow.

* Define and design a multivariate test 
* Create a multivariate test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
