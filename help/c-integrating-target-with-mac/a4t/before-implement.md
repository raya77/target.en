---
keywords: Recommendations
description: Learn the implementation requirements for Analytics for [!DNL Target] (A4T) and what to consider before you implement this integration.
title: What Should I Know Before Implementing A4T?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
---
# Before you implement Analytics for Target (A4T) with at.js

Several changes occur in your data collection process when enabling [!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T).

Before you decide to use this integration, review the following sections and consider the impact to your reporting processes.

>[!NOTE]
>
>This article applies to at.js implementations only.

## Implementation requirements {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Before you can begin using A4T, you must request that your account is provisioned for the integration. Use the [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences) to request to be provisioned.

This A4T integration requires that you implement the following library versions (or newer), depending on whether you want to use redirect offers with A4T or not:

### Requirements needed if *not* using redirect offers with A4T

This integration requires that you implement the following library versions (or newer) if you do not plan on using redirect offers with A4T. The order listed is the order of operations.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 1.8.0
* [!DNL Adobe Target] (depending on your implementation): at.js version 0.9.1 or mbox.js version 61
* Adobe Analytics: appMeasurement.js version 1.7.0

### Requirements needed if using redirect offers with A4T

To use redirect offers with A4T, you must implement the following library versions (or newer). The order listed is the order of operations.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 2.3.0

  **Note:**  at.js 1.8.0 or newer no longer works with Visitor API versions older than 2.5.0 for passing [!DNL Adobe Audience Manager] (AAM) parameters.
  
* [!DNL Adobe Target]: at.js version 1.6.2

  **Note**: The  mbox.js library does not support redirect offers with A4T. Your implementation must use at.js.

* Adobe Analytics: appMeasurement.js version 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Things to know before you implement {#section_50D49CC52E11414089C89FB67F9B88F5}

* This integration is enabled on new activities when you select to use [!DNL Analytics] as the reporting source. After you make the implementation changes described in this document, your existing activities are not impacted. 
* The process of setting up [!DNL Analytics] as the reporting source for [!DNL Target] includes several implementation steps, followed by a provisioning step. It is a good idea to read through the process as described below before implementing. After you complete these steps, you are ready to use [!DNL Analytics] as your reporting source when it is enabled for you. The provisioning process can take up to five business days. 
* The [!DNL Visitor ID service] creates a shared [!DNL Visitor ID] across the [!DNL Adobe Experience Cloud]. Although it does not replace the [!DNL Target] mboxPC id or [!DNL Audience Manager] UUID, it does replace the way [!DNL Analytics] identifies new visitors. If set up properly, returning [!DNL Analytics] visitors should also be identified via their old [!DNL Analytics] ID. Similarly, because the [!DNL Target] mboxPCid remains intact, no [!DNL Target] visitor profile data is lost when you upgrade to the [!DNL Visitor ID service]. 
* The [!DNL Visitor ID service] must execute before your [!DNL Analytics] and [!DNL Target] page code. Make sure that `VisitorAPI.js` appears above the tags for all other [!DNL Experience Cloud] solutions.

## Latency {#section_9489BE6FD21641A4844E591711E3F813}

After this integration is enabled, you will experience an extra 5-10 minutes of latency in [!DNL Analytics]. This latency increase allows data from [!DNL Analytics] and [!DNL Target] to be stored on the same hit, allowing you to break down activities by page and site section.

This increase is reflected in all [!DNL Analytics] services and tools, including the live-stream and real-time reporting, and applies in the following scenarios:

* For live stream, real-time reports & API requests, and current data for traffic variables, only hits with a supplemental data ID are delayed. 
* For current data on conversion metrics, finalized data, and data feeds, all hits are delayed an extra 5-7 minutes.

The latency increase starts after you implement the [!DNL Experience Cloud] visitor ID service, even if you have not fully implemented this integration.

## Supplemental ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

All [!DNL Target] calls used by an A4T activity to deliver content or record the goal metric must have a corresponding [!DNL Analytics] hit that shares the supplemental ID for A4T to work properly.

Hits that contain data from [!DNL Analytics] and [!DNL Target] contain a supplemental data ID. You can see this ID in the [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. For example: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. This ID is generated anytime the following criteria are in place:

* The visitor ID service is in implemented 
* A version of [!DNL mbox.js] that supports this integration is implemented.

When [troubleshooting](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), be sure to confirm that the supplemental ID is present on [!DNL Analytics] hits.

## Client-side Analytics logging {#client-side}

If at.js, the [!DNL Experience Cloud Visitor ID Service], and appMeasurement.js are on the page, [!DNL Analytics], and [!DNL Target] correctly stitches events for reporting and analytics purposes in the backend as long as the correct supplemental ID is included from the page. You do not need to manage and perform any additional operations for A4T to function correctly.

There are cases when you might want to have more control on when and how to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes. You might have an in-house analytics tool that you use for internal purposes. However, you also want to send the analytics data to [!DNL Analytics] via your in-house analytics product so that other members of your organization can continue to use [!DNL Analytics] as a visual reporting source. See [Step 7: Reference at.js or mbox.js on all site pages](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Analytics for Target Implementation* for more information.

## Shared audiences

While filling in the [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences), be aware of the following important information concerning the [!UICONTROL Shared Audiences] option listed under "[!UICONTROL For which capabilities are you requesting provisioning]?" 

![Request form](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

When you request [!UICONTROL Shared Audiences], you enable [!UICONTROL Target] and [!UICONTROL Adobe Audience Manager] (AAM) to share information, in this case audiences.

>[!IMPORTANT]
>
>This integration between [!UICONTROL Target] and AAM comes with extra costs. You are billed for each [!UICONTROL Target] call in AAM.
