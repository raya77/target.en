---
keywords: implement;implementing;implementation;adobe launch;launch;race;redirect;experience platform launch;platform launch
description: Learn how to implement the Adobe [!DNL Target] at.js library using Adobe Experience Platform Launch, the preferred method to implement Adobe [!DNL Target].
title: How Do I Implement [!DNL Target] using Adobe Launch?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
---
# Implement [!DNL Target] using [!DNL Adobe Platform Launch]

[!DNL Adobe Experience Platform Launch] is the next-generation tag management platform from [!DNL Adobe] and is the preferred method to implement [!DNL Adobe Target]. [!DNL Platform Launch] gives customers a simple way to deploy and manage the analytics, marketing, and advertising tags necessary to power relevant customer experiences.

## Implement [!DNL Target] using [!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25} 

The following table lists the various sources where you can get more information about [!DNL Platform Launch]:

| Resource | Details |
|--- |--- |
|[Implementing [!DNL Target] using the [!UICONTROL Adobe Target Extension Tutorial]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions)|This tutorial provides step-by-step instructions to implement [!DNL Target] in a website with [!DNL Platform Launch]. Topics include adding the at.js JavaScript library, firing the global mbox, adding parameters, and integrating with other solutions. This article is part of a larger tutorial that shows you how to implement [!DNL Platform Launch], and other [!DNL Adobe Experience Cloud] solutions.|
|[Quickstart guide for tags in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html)|Information about deploying and managing the analytics, marketing, and advertising tags necessary to power relevant customer experiences.|
|[Adobe [!DNL Target] Extension Documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html)|Information about implementing [!DNL Target] using [!DNL Platform Launch].|

## Advantages of implementing at.js using the [!DNL Target] [!DNL Platform Launch] extension {#section_48B3F938B6F8491DAF798E0DB54EF304}

The following advantages apply only if you use [!DNL Platform Launch] to implement at.js. For this reason, [!DNL Adobe] strongly suggests that you use [!DNL Platform Launch] rather than a manual implementation of at.js.

* **Solves [!DNL Adobe Analytics] and [!DNL Target] race condition:** Because the [!DNL Analytics] call could be fired before the [!DNL Target] call, the [!DNL Target] call is not stitched to the [!DNL Analytics] call. This sequencing can lead to incorrect data. Starting with 0.6.0, the [!DNL Platform Launch] extension ensures that the [!DNL Analytics] beacon call waits until the [!DNL Target] call completes, successfully or not. Using [!DNL Platform Launch] solves the data inconsistency customers can experience when implementing manually. 
* **Prevents incorrect redirect offer handling:** If you have [!DNL Target] and [!DNL Analytics] on the page, and there is a redirect offer executed by [!DNL Target], you can experience a situation in which the [!DNL Analytics] tracker fires a request when it shouldn’t (because the user is being redirected to a different URL). If you implement [!DNL Target] and [!DNL Analytics] via [!DNL Platform Launch], you’ll not experience this issue. Using [!DNL Platform Launch], [!DNL Target] instructs [!DNL Analytics] to abort the [!DNL Analytics] beacon request.
