---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the current Release?
feature: Release Notes
---

# Target release notes (current)

These release notes provide information about features, enhancements, and fixes for each [!DNL Adobe Target Standard] and [!DNL Target Premium] release. In addition, release notes for Target APIs, SDKs, the JavaScript library (at.js), and other platform changes are also included, when applicable.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: On March 31, 2021, [!DNL Adobe Target] will no longer support the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>Migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library before this date to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

## at.js 2.4.1 (March 23, 2021)

This release of at.js is a maintenance release and includes the following enhancements and fixes:

* Fixed an issue with targetPageParams being included in mbox requests. targetPageParams should be included in pageLoad requests only. (TNT-40247)
* Optimized window and document globals referencing in the [!DNL Adobe Experience Platform Launch] extension. (TNT-37124)

## IP address changes for Recommendations feed-processing servers (March 16, 2021)

The [!DNL Target Recommendations] feed-processing server IP addresses were updated on March 16, 2021. For more information, see [IP addresses used by Recommendations feed-processing servers](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md).

## Target Standard/Premium 21.2.1 (March 9, 2021)

This maintenance release contains the following enhancements, fixes, and changes.

The issue numbers in parentheses are for internal [!DNL Adobe] use.

* Increased the allowable offer size (TGT-38304):

  |Type|Previous Limit|New Limit|
  | --- | --- | --- |
  |HTML|256 KB|1024 KB|
  |Visual offers from the Target UI|64 KB|1024 KB for each experience|
  |Via API|512 KB|1024 KB|

* [!UICONTROL Personalization Insights] reports for [!UICONTROL Auto-Target] (AT) and [!UICONTROL Automated Personalization] (AP) activities are now produced daily. You can choose a report providing [!UICONTROL Automated Segments] or [!UICONTROL Important Attributes] for the last 15, 30, and 60 days. The 45-day and 90-day options have been removed to enable the other lookback window settings to run daily. (TGT-39472)
* Fixed an issue that caused the current dependency to not display when customers click [!UICONTROL Edit Dependency] on an activity's [!UICONTROL Goals & Settings] page. (TGT-39340)
* Fixed an issue when refreshing a workspace's [!UICONTROL Audience Library]. Before the refresh, the audiences for the currently selected workspace displayed. After the refresh, the [!UICONTROL Default Workspace] and its audiences displayed. The current workspace and its audiences now persist after the refresh. (TGT-38871) 
* Fixed an issue when copying a [!UICONTROL Recommendations] activity and later editing the original activity by changing its criteria sequence. The change in the criteria sequence in the original activity was also incorrectly applied to the copied activity. (TGT-39155)
* Fixed an issue that caused the incorrect number of products to display for [!UICONTROL Recommendations] exclusions. (TGT-39599)

## Additional release notes and version details

|Resource|Details|
|--- |--- |
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
