---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features and Enhancements Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: October 5, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

## [!DNL Target] Standard/Premium 22.10.1 (staggered release October 6-10, 2022)

This release will be available according to the following staggered schedule:

* **October 6**: Americas region
* **October 7**: Europe, Middle East, and Africa (EMEA) region
* **October 10**: Asia-Pacific (APAC) region

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


## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to [!DNL Target] and other [!DNL Adobe Experience Cloud] solutions, sign up for the [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
