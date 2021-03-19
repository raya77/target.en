---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: Implement Adobe Target by referencing the Target libraries (at.js or mbox.js) on your web pages.
title: Understand the Target JavaScript libraries
feature: Implementation
---

# Understand the Target JavaScript libraries

Implement [!DNL Adobe Target] by referencing the [!DNL Adobe Target] libraries (Adobe Experience Platform Web SDK or at.js) on your web pages.

>[!NOTE]
>
>The mbox.js library is no longer being developed. All customers must migrate from mbox.js to at.js or to the [!UICONTROL Adobe Experience Platform Web SDK] before March 31, 2021. For more information, see [Migrate to at.js from mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA) or [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

## Differences between the Target JavaScript Libraries {#section_40117C78C2F84FECAC4F1BA40CC4F171}

The following table explains the differences between the [!DNL Target] JavaScript libraries:

| Library Reference | Description |
|--- |--- |
|Adobe Experience Platform Web SDK|The [!UICONTROL Adobe Experience Platform Web SDK] lets you interact with the various services in the [!DNL Experience Cloud] (including [!DNL Target]) through the Adobe Experience Edge Network. If you choose to migrate to the [!DNL Adobe Experience Platform Web SDK], see [What is Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) in the *Web SDK Guide*.|
|at.js|at.js replaces mbox.js for [!DNL [!DNL Target]] implementations.<br>Among other benefits, at.js improves page-load times for web implementations, improves security, prevents  document.write warnings in Google Chrome, and provides better implementation options for single-page applications.<br>For more information, see [at.js Implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md).|

## Impact of at.js on Page-Load Time {#section_16630CD0FF0A498EB596A51381366A5A}

Many customers and consultants want to know the impact of [!DNL at.js] on page-load time, especially in the context of new versus returning users. Unfortunately, it's hard to measure and give concrete numbers regarding how [!DNL at.js] influences page-load time due to each customer's implementation.

However, if the Visitor API is present on the page, [!DNL Target] can better understand how [!DNL at.js] influences page-load time.

>[!NOTE]
>
>The Visitor API and [!DNL at.js] have an impact on page-load time only when you are using the global mbox (because of the body-hiding technique). Regional mboxes are not impacted by Visitor API integration.

The following sections describe the sequence of actions for new and returning visitors:

### New visitors

1. The Visitor API is loaded, parsed, and executed.
1. at.js is loaded, parsed, and executed.
1. If global mbox auto-create is enabled, the [!DNL Target] JavaScript library:

   * Instantiates the Visitor object.
   * The [!DNL Target] library tries to retrieve [!UICONTROL Experience Cloud Visitor ID] data.
   * For a new visitor, the Visitor API fires a cross-domain request to `demdex.net`.
   * After [!UICONTROL Experience Cloud Visitor ID] data is retrieved, a request to Target is fired.

### Returning Visitors

1. The Visitor API is loaded, parsed, and executed.
1. at.js is loaded, parsed, and executed.
1. If global mbox auto-create is enabled, the [!DNL Target] JavaScript library:

   * Instantiates the Visitor object.
   * The [!DNL Target] library tries to retrieve [!UICONTROL Experience Cloud Visitor ID] data.
   * The Visitor API retrieves data from cookies.
   * After [!UICONTROL Experience Cloud Visitor ID] data is retrieved, a request to [!DNL Target] is fired.

>[!NOTE]
>
>For new visitors, when the Visitor API is present, [!DNL Target] goes over the wire multiple times to make sure that [!DNL Target] requests contain [!UICONTROL Experience Cloud Visitor ID] data. For returning visitors, [!DNL Target] goes over the wire only to [!DNL Target] to retrieve the personalized content. 
