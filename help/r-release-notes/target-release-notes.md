---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: September 14, 2021**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>To avoid any potential issues with your sites, migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.9.1 (September 14, 2021)

This maintenance release contains the following enhancements, fixes, and changes.

* Fixed issues that prevented customers from logging in to the [!UICONTROL Visual Experience Composer] (VEC) due to new security policies for third-party cookies in some web browsers. This issue was discussed in "Pages not loading in the Visual Experience Composer (VEC) or Enhanced Experience Composer (EEC) when using Google Chrome version 80+" in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).
* Fixed an issue that caused offer names in the VEC to display the offer's path instead of the offer's friendly name. (TGT-41300) 
* Fixed an issue in [!DNL Recommendations] that erroneously applied entity ID changes in a promotion in a duplicated activity to the original activity. (TGT-41482)
* Fixed an issue that prevented the "Edit Criteria" button from displaying properly on the [!UICONTROL Experiences] page for [!DNL Recommendations] activities in the VEC. (TGT-39512)
* Fixed an issue that prevented synchronization of activities when duplicated and copied to a test workspace. (TGT-40686)
* Fixed an issue that prevented modifications to a selector with [experience fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) when using "[!UICONTROL Insert After]" in the VEC. (TGT-41802)
* Fixed an issue that prevented empty JSON content in an offer from being sent to the backend. [!DNL Target] now sends the JSON object even though it is empty. (TGT-41555)
* Fixed an issue that caused legacy [!DNL Analytics] reporting to open instead of [!DNL Analysis Workspace] when customers clicked "[!UICONTROL View in Analytics]" while viewing a report. (TGT-41867)
* Added additional clarification to the displayed UI message when a customer attempts to select [!DNL Analytics] as the reporting source (A4T) for an [!UICONTROL Automated Personalization] activity. The message states that, "[!DNL Target] is the only supported source for [!UICONTROL Automated Personalization] activities." (TGT-41954)
* Added additional clarification to the error message when customers attempt to separate hosts with "newline" instead of commas. (TGT-40671)
* Updated the [!UICONTROL Type] field for segments to accurately include [!DNL Platform] and [!DNL AAM] ([!DNL Adobe Audience Manager]). (TGT-41328)
* Fixed an issue that caused traffic sources operands to change after clicking [!UICONTROL Save]. (TGT-41408)
* After saving an activity-only audience (either rule-based or combined), the UI now loads the [!UICONTROL Audience] picker with the Activity-only filter applied. (TGT-41747).
* Fixed an issue that caused audiences that were deleted from the source ([!DNL Adobe Experience Platform], [!UICONTROL AAM], and so forth) to continue to display in the [!DNL Target] UI.
* Added a filter option to the [!UICONTROL Audiences] page to display only audiences imported from the [!DNL Adobe Experience Platform]. (TGT-41298)
* Added enhanced keyboard accessibility options in the [!UICONTROL Audiences] UI. (TGT-39927) 
* Fixed an issue that caused some activities' "[!UICONTROL Last Updated]" dates to differ from the English UI for Spanish and Japanese customers (when viewing the UI in Spanish and Japanese). (TGT-38980) 

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
