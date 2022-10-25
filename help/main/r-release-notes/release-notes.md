---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target], including SDKs, APIs, and JavaScript libraries.
landing-page-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: What Is Included in the Current Release?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
---
# Target release notes (current)

These release notes provide information about features, enhancements, and fixes for each [!DNL Adobe Target Standard] and [!DNL Target Premium] release. In addition, release notes for [!DNL Target] APIs, SDKs, the [!DNL Adobe Experience Platform Web SDK], at.js, and other platform changes are also included, when applicable.

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

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

## [!DNL Target] Standard/Premium 22.10.1 (staggered release October 10-13, 2022)

This release will be available according to the following staggered schedule:

* **October 10**: Asia-Pacific (APAC) region
* **October 12**: Americas region
* **October 13**: Europe, Middle East, and Africa (EMEA) region

This release contains the following new features, enhancements, and fixes:

|Feature|Details|
| --- | --- |
|[!DNL Adobe Experience Manager] (AEM) experience fragments|Updates to the AEM experience fragments functionality include the following:<ul><li>Added the ability to filter AEM experience fragments by type (HTML or JSON) in the [!UICONTROL Offers] list. (TGT-43121)</li><li>Fixed an issue that allowed customers to insert JSON [!UICONTROL Experience Fragment] offers when using the VEC, which is not supported. JSON offers can be inserted only when using the [!UICONTROL Form-Based Experience] composer. (TGT-43846)</li></ul>For more information, see AEM [experience fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).|
|New [!UICONTROL Visual Experience Composer] extension for Google Chrome|A new [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) extension for Chrome is available in the Chrome Web Store.<br>Starting in January 2023, the current [!DNL Target] VEC Helper extension will stop working in Google Chrome because Google won't allow extensions using Manifest V2. Download the new extension to continue to visually author your websites in [!DNL Target] starting with the new year.<br>The following links show the two extensions in the Chrome Web Store:<ul><li>[New extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Old Extension](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>For more information, see [Visual Editing Helper extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).|
|Documentation updates|Major documentation updates include the following:<ul><li>New and updated [Adobe Target Admin and Reporting API documentation](https://developer.adobe.com/target/administer/admin-api/){target=_blank} includes comprehensive coverage of Admin and Reporting API endpoints, including properties, offers, hosts, environments, clients, audiences, activities, and more.<br>See this and additional developer content in the [[!DNL Adobe Target] [!UICONTROL Developer Guide]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Statistical calculations in A/Bn tests](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>This article documents the detailed statistical calculations used in manual A/Bn tests in [!DNL Adobe Target].<br>The information in this article replaces the *Adobe Target Calculations for A/B Testing* pdf file that was previously available for download on this site.</li></ul>|
 
* Fixed an issue that prevented audience rule information from displaying properly in the [!UICONTROL Audiences Refinements] information window. (TGT-43917)
* Improved the performance of the [!DNL Target] UI when loading audiences that approach the [recommended limit of targeting rules](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Fixed an issue that caused some components to not display properly in the [!UICONTROL Modifications] panel on the [!UICONTROL Experiences] page when creating or editing activities in the VEC after switching from [!UICONTROL Compose] to [!UICONTROL Browse] mode. (TGT-43300)
* Fixed an issue that prevented some customers from archiving [!UICONTROL A/B Test] activities that use [!UICONTROL Auto-Target]. (TGT-40978)
* Added the ability to automatically use a single offer in multiple locations within a single reporting group. (TGT-40689)

## Additional release notes and version details

|Resource|Details|
|--- |--- |
|[Release notes: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en)|Details about changes in each version of the Platform Web SDK.|
|[at.js version details](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}|Details about changes in each version of the [!DNL Adobe Target] at.js JavaScript library.|

## Documentation Changes, Past Release Notes, and Experience Cloud Release Notes

In addition to the notes for each release, the following resources provide additional information:

|Resource|Details|
|--- |--- |
|Documentation changes|View detailed information about updates to this guide that are not included in these release notes.<br>For more information, see [Documentation Changes](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C).|
|Release notes for previous releases|View information about new features and enhancements in previous releases of Target Standard and Target Premium.<br>For more information, see [Release notes for previous releases](/help/main/r-release-notes/release-notes-for-previous-releases.md).|
|Adobe Experience Cloud release notes|View the latest release notes for the Adobe Experience Cloud solutions.<br>For more information, see [Experience Cloud Release Notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html).|

## Prerelease Information {#section_5D588F0415A2435B851A4D0113ACA3A0}

The following resources let you see what's coming in the next Target release.

|Resource|Details|
|--- |--- |
|Adobe Priority Product Update|To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)|
|Upcoming release notes|For information about the current month's Target releases, including prerelease information, see the [Target Release Notes - Prerelease](/help/main/r-release-notes/target-release-notes.md) page.|
