---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features and Enhancements Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: September 29, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

## [!DNL Target] Standard/Premium 22.10.1 (staggered release October 4-6, 2022)

This release will be available according to the following staggered schedule:

* **October 4**: Europe, Middle East, and Africa (EMEA) region
* **October 5**: Asia-Pacific (APAC) region
* **October 6**: Americas region

This release contains the following new features, enhancements, and fixes:

|Feature|Details|
| --- | --- |
|[!DNL Adobe Experience Manager] (AEM) experience fragments|Updates to the AEM experience fragments functionality include the following:<ul><li>Added the ability to filter AEM experience fragments by type (HTML or JSON) in the [!UICONTROL Offers] list. (TGT-43121)</li><li>Fixed an issue that allowed customers to insert JSON [!UICONTROL Experience Fragment] offers when using the VEC, which is not supported. JSON offers can be inserted only when using the [!UICONTROL Form-Based Experience] composer. (TGT-43846)</li></ul>For more information, see AEM [experience fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).|
|New [!UICONTROL Visual Experience Composer] extension for Google Chrome|A new [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) extension for Chrome is available in the Chrome Web Store.<br>Starting in January 2023, the current [!DNL Target] VEC Helper extension will stop working in Google Chrome because Google won't allow extensions using Manifest V2. Download the new extension to continue to visually author your websites in [!DNL Target] starting with the new year.<br>The following links show the two extensions in the Chrome Web Store:<ul><li>[New extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Old Extension](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>|
|Optimized A4T metrics for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target]<br>(Exact release date to be determined.)|Be aware of the following changes:<ul><li>Added support for binary and maximization metrics in [!UICONTROL Analytics for Target] A4T reporting for [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities</li><li>Removed the binary metrics warning message for [!UICONTROL Auto-Target] activities</li><li>Preserved behavior for existing activities until February 20, 2023. After this date, activities will be discontinued to force existing activity migration to new behavior</li><li>Starting February 20, 2023, support for `averagetimespentonsite`, `bouncerate`, and `entries` metrics in [!DNL Target] activities will be deprecated.</li></ul>|
 
* Fixed an issue that prevented audience rule information from displaying properly in the [!UICONTROL Audiences Refinements] information window. (TGT-43917)
* Improved the performance of the [!DNL Target] UI when loading audiences that approach the [recommended limit of targeting rules](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Fixed an issue that caused some components to not display properly in the [!UICONTROL Modifications] panel on the [!UICONTROL Experiences] page when creating or editing activities in the VEC after switching from [!UICONTROL Compose] to [!UICONTROL Browse] mode. (TGT-43300)
* Fixed an issue that prevented some customers from archiving [!UICONTROL A/B Test] activities that use [!UICONTROL Auto-Target]. (TGT-40978)
* Added the ability to automatically use a single offer in multiple locations within a single reporting group. (TGT-40689)

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to [!DNL Target] and other [!DNL Adobe Experience Cloud] solutions, sign up for the [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
