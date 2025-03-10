---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features and Enhancements Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: October 19, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

## [!DNL Target] Standard/Premium 22.10.3 (staggered release October 25-27, 2022)

This release will be available according to the following staggered schedule:

* **October 25**: Europe, Middle East, and Africa (EMEA) region
* **October 26**: Asia-Pacific (APAC) region
* **October 27**: Americas region

This release contains the following new features, enhancements, and fixes:

|Feature|Details|
| --- | --- |
|[!DNL Recommendations]|Added friendly names in [!UICONTROL Analytics for Target] A4T reporting. Previously, [!DNL Target] listed experience IDs only. This enhancement aligns reporting between [!DNL Adobe Analytics] and [!DNL Target] and helps customers streamline building reports in A4T. (TGT-41853)|
|Optimized A4T metrics for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target]<br>(Available to select customers for testing. Will be available to all customers in a future release.)|Be aware of the following changes:<ul><li>Added support for binary and maximization metrics in [!UICONTROL Analytics for Target] A4T reporting for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities</li><li>Preserved behavior for existing activities until February 2023. After this date, activities will be discontinued to force existing activity migration to new behavior</li><li>Starting February 20, 2023, support for `averagetimespentonsite`, `bouncerate`, and `entries` metrics in [!DNL Target] activities will be deprecated.</li></ul>|

* Added tooltips in the [!DNL Target] UI to help customers navigate the audience builder more efficiently and to learn how to use features that might be unfamiliar. (TGT-44139)
* Added functionality to prevent customers from editing an activity that was disabled by [!DNL Target] because it uses unsupported metrics. A message in the UI directs customers to duplicate the activity and then update the conversion metric.

  With this release `averagetimespentonsite`, `bouncerate`, and `entries` metrics in [!DNL Target] activities will be deprecated for new activities. Existing activities can continue using these metrics until February 2023. (TGT-43860, TGT-43861, & TGT-43650)

* Added a tooltip in the [!DNL Target] UI to help customers select an optimization criteria while creating or editing an [!UICONTROL Auto-Target] activity that uses A4T. (TGT-43713) 

## Additional release notes and version details

|Resource|Details|
|--- |--- |
|[Release notes: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en)|Details about changes in each version of the Platform Web SDK.|
|[at.js version details](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}|Details about changes in each version of the [!DNL Adobe Target] at.js JavaScript library.|


## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to [!DNL Target] and other [!DNL Adobe Experience Cloud] solutions, sign up for the [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
