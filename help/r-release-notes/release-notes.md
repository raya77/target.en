---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the current Release?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
---
# Target release notes (current)

These release notes provide information about features, enhancements, and fixes for each [!DNL Adobe Target Standard] and [!DNL Target Premium] release. In addition, release notes for Target APIs, SDKs, the JavaScript library (at.js), and other platform changes are also included, when applicable.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>Migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

## at.js version 2.5.0 (May 13, 2021)

This release of at.js includes the following enhancements and changes:

* [On-device decisioning](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) support for at.js.
* [Preview links](/help/c-activities/c-activity-qa/activity-qa.md) support for Automated Personalization activities

This release also removes support for Microsoft Internet Explorer 10, Internet Explorer 11, and all older versions. Microsoft Edge continues to be supported in at.js 2.5.0 and later.

## Target Standard/Premium 21.4.1 (April 19, 2021)

This release contains the following new features and enhancements. The issue numbers in parentheses are for internal [!DNL Adobe] use.

|Feature|Details|
| --- | --- |
|On-device decisioning support for at.js<br>(Date to be announced)|On-device decisioning lets marketers and developers deliver experimentation and personalization on a user's browser at near-zero latency.<br>For more information, see [On-device decisioning for at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)|
|![Premium](/help/assets/premium.png) List-based operators for entity filtering rules|[!DNL Target Recommendations] supports new list-based operators for entity filtering rules. (TGT-39234)<br>Newly added operators include:<br><ul><li>Is Contained In List</li><li>Is Not Contained In List</li><li>List Contains An Item In</li><li>List Does Not Contain An Item In</li><li>List Contains All Items In</li><li>List Does Not Contain All Items In</li></ul>For more information, see "Available operators" in [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators).|

This release contains the following fixes.

* Fixed an issue that prevented an activity from syncing after changing the audience to [!UICONTROL All Visitors]. (TGT-40259)
* Fixed an issue that prevented offers from being duplicated when used in different locations in [!UICONTROL Automated Personalization] activities even though the [!UICONTROL Disallow Duplicates] option is enabled. (TGT-39567)
* Fixed an issue that prevented the [!UICONTROL Administration] > [!UICONTROL Scene7 configuration] page from loading properly. (TGT-39918)
* Fixed an issue that caused properties to be mapped to the incorrect workspace. (TGT-39869)
* Fixed an issue that caused infinite loading if the request fails after changing the environment while creating a recommendations exclusion. (TGT-39948)

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
