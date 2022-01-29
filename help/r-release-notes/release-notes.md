---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target], including SDKs, APIs, and JavaScript libraries.
landing-page-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: What Is Included in the Current Release?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
---
# Target release notes (current)

These release notes provide information about features, enhancements, and fixes for each [!DNL Adobe Target Standard] and [!DNL Target Premium] release. In addition, release notes for Target APIs, SDKs, the [!DNL Adobe Experience Platform Web SDK], at.js, and other platform changes are also included, when applicable.

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

## at.js version 2.8.1 (January 28, 2022)

* Fixed `pageLoad` not being mapped to target-global-mbox in [!UICONTROL On Device Decisioning] (ODD) hybrid execution mode.
* Fixed an issue with analytics details for mbox request.
* Upgraded dev dependencies to fix security vulnerabilities.

## [!DNL Target Standard/Premium] 22.1.2 (January 26, 2022)

|Feature|Details|
| --- | --- |
|[!DNL Adobe Experience Platform] audiences in [!DNL Target]|You can now consume and use [!DNL Adobe Experience Platform] audiences in [!DNL Target]. The [!DNL Target] team, [!DNL Experience Platform] [!DNL Destinations] team and the [!DNL Unified Profile Service] team is pleased to announce the general availability of the “Same Page/Next Page Personalization” use cases.<br>Using audiences created in [!DNL Adobe Experience Platform] provide richer customer data that leads to more impactful personalization. The [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCP), built on [!DNL Adobe Experience Platform] helps companies bring together known and anonymous data from multiple enterprise sources to create customer profiles that can be used to provide personalized customer experiences across all channels and devices in real time.<br>For more information, see [Use audiences from Adobe Experience Platform](/help/c-target/c-audiences/audiences.md#aep) in *Create audiences*.<br>Be sure to read the Adobe blog and watch the video: [[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] and [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}.|
|[!UICONTROL Audiences] UI refresh|As part of the [!DNL Adobe Target] team's ongoing effort to improve the user-experience for [!DNL Target] users, this release refreshes the [!UICONTROL Audiences] and [!UICONTROL Profile Scripts] pages in the [!DNL Target] UI. This update unifies and standardizes design patterns that were previously inconsistent, while adding new enhancements, such as:<ul><li>The ability to select and delete multiple audiences simultaneously</li><li>A refreshed [audience builder design](/help/c-target/c-audiences/create-audience.md)</li><li>Exclusion rule support in the [!UICONTROL Audience] library rule builder</li><li>A new “Audience Source” filter, to allow for faster audience discovery</li><li>Session persistent search and filter options</li><li>The ability to move audiences between workspaces for [!DNL Target Premium] customers.</li></ul>For more information, see [Audiences](/help/c-target/target.md).<br>**NOTE**: This feature will be rolled out to customers in different regions in the next eight weeks.|
|[!UICONTROL Profile Scripts] UI refresh|The [!UICONTROL Profile Scripts] library was also updated, and includes a refreshed interface along and several productivity updates:<ul><li>The ability to select and delete multiple profile scripts simultaneously</li><li>A new code editor for profile scripts</li><li>Syntax highlighting and error checking inside the code editor</li><li>Auto-complete tokens (mbox or profile) parameters through keyboard shortcuts</li></ul>For more information, see [Visitor Profiles](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**NOTE**: This feature will be rolled out to customers in different regions in the next eight weeks.|

## [!DNL Target Standard/Premium] 22.1.1 (January 12, 2022)

This release includes bug fixes and pre-requisite capabilities for future integrations.

## at.js version 2.8.0 (January 7, 2022)

The [!DNL Target] at.js JavaScript library now collects feature usage and performance telemetry data. Personal data is not collected. Opt-out for this feature is available by setting `telemetryEnabled` to false in `targetGlobalSettings`. For more information, see [telemetryEnabled in targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry).

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
