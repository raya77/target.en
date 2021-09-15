---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target], including SDKs, APIs, and JavaScript libraries.
landing-page-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: What New Features Are Included in the Current Release?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
---
# Target release notes (current)

These release notes provide information about features, enhancements, and fixes for each [!DNL Adobe Target Standard] and [!DNL Target Premium] release. In addition, release notes for Target APIs, SDKs, the [!DNL Adobe Experience Platform Web SDK], at.js, and other platform changes are also included, when applicable.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>Migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

## [!DNL Target Standard/Premium] 21.9.1 (September 14, 2021)

This maintenance release contains the following enhancements, fixes, and changes.

* Fixed issues that prevented customers from logging in to the [!UICONTROL Visual Experience Composer] (VEC) due to new security policies for third-party cookies in some web browsers. This issue was discussed in "Pages not loading in the Visual Experience Composer (VEC) or Enhanced Experience Composer (EEC) when using Google Chrome version 80+" in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).
* Fixed an issue that caused offer names in the VEC to display the offer's path instead of the offer's friendly name. (TGT-41300)
* Experience names are now reflected in [!DNL Analysis Workspace] for A4T activities (TGT-38674) 
* Fixed an issue in [!DNL Recommendations] that erroneously applied entity ID changes in a promotion in a duplicated activity to the original activity. (TGT-41482)
* Fixed an issue that prevented the "Edit Criteria" button from displaying properly on the [!UICONTROL Experiences] page for [!DNL Recommendations] activities in the VEC. (TGT-39512)
* Fixed an issue that prevented synchronization of activities when duplicated and copied to a test workspace. (TGT-40686)
* Fixed an issue that prevented modifications to a selector with [experience fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) when using "[!UICONTROL Insert After]" in the VEC. (TGT-41802)
* Fixed an issue that prevented empty JSON content in an offer from being sent to the backend. [!DNL Target] now sends the JSON object even though it is empty. (TGT-41555)
* Fixed an issue that caused legacy [!DNL Analytics] reporting to open instead of [!DNL Analysis Workspace] when customers clicked "[!UICONTROL View in Analytics]" while viewing a report. (TGT-41867)
* Added additional clarification to the displayed UI message when a customer attempts to select [!DNL Analytics] as the reporting source (A4T) for an [!UICONTROL Automated Personalization] activity. The message states that, "[!DNL Target] is the only supported source for [!UICONTROL Automated Personalization] activities." (TGT-41954)
* Added additional clarification to the error message when customers attempt to separate hosts with "newline" instead of commas. (TGT-40671) 
* Fixed an issue that caused some activities' "[!UICONTROL Last Updated]" dates to differ from the English UI for Spanish and Japanese customers (when viewing the UI in Spanish and Japanese). (TGT-38980) 

## Additional release notes and version details

|Resource|Details|
|--- |--- |
|[Release notes: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en)|Details about changes in each version of the Platform Web SDK.|
|[at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)|Details about changes in each version of the [!DNL Adobe Target] at.js JavaScript library.|

## Documentation Changes, Past Release Notes, and Experience Cloud Release Notes

In addition to the notes for each release, the following resources provide additional information:

|Resource|Details|
|--- |--- |
|Documentation changes|View detailed information about updates to this guide that are not included in these release notes.<br>For more information, see [Documentation Changes](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C).|
|Release notes for previous releases|View information about new features and enhancements in previous releases of Target Standard and Target Premium.<br>For more information, see [Release notes for previous releases](/help/r-release-notes/release-notes-for-previous-releases.md).|
|Adobe Experience Cloud release notes|View the latest release notes for the Adobe Experience Cloud solutions.<br>For more information, see [Experience Cloud Release Notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html).|

## Prerelease Information {#section_5D588F0415A2435B851A4D0113ACA3A0}

The following resources let you see what's coming in the next Target release.

|Resource|Details|
|--- |--- |
|Adobe Priority Product Update|To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)|
|Upcoming release notes|For information about the current month's Target releases, including prerelease information, see the [Target Release Notes - Prerelease](/help/r-release-notes/target-release-notes.md) page.|
