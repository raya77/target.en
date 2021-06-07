---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target], including SDKs, APIs, and JavaScript libraries.
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

## Target Standard/Premium 21.6.1 (June 7, 2021)

This release includes the following enhancements:

|Feature|Details|
| --- | --- |
|![Premium badge](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL Catalog Search] API|Search your [!DNL Recommendations] product and content catalog programmatically via API to identify items that match a search criteria and simplify administration of your catalog.<br>**Limitations and notes**:<ul><li>Catalog search via API is not supported for environments with more than 2,000,000 items.</li><li>Catalog search results via API are updated more rapidly than catalog search results via the [!DNL Target] UI. The catalog search in the [!DNL Target] UI can take additional time to reflect the latest results.</li></ul>For more information, see [Searching Entities](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) in the *[!DNL Adobe Target] [!DNL Recommendations] API* guide.|

This release maintenance release contains the following fixes.

* Fixed an issue that caused the default workspace to change to another workspace when refreshing the [!UICONTROL Audiences] page. (TGT-38871)
* Fixed an issue in [!UICONTROL Administration] > [!UICONTROL Implementation] that sometimes caused an error message stating, "Your global mbox may not be in sync. Please try resaving it."

## ![Adobe Experience Platform Web SDK badge](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] version 2.5.0 (June 1, 2021)

This release of the [!DNL Platform Web SDK] includes support for the following:

|Feature|Details|
| --- | --- |
|Redirect support with [!UICONTROL Analytics for Target] (A4T)|The Platform Web SDK now supports [!DNL Target] redirects when using [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>For more information, see see [Analytics for [!DNL Target] implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).|

## at.js version 2.5.0 (May 13, 2021)

This release of at.js includes the following enhancements and changes:

* [On-device decisioning](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) support for at.js.
* [Preview links](/help/c-activities/c-activity-qa/activity-qa.md) support for Automated Personalization activities

This release also removes support for Microsoft Internet Explorer 10, Internet Explorer 11, and all older versions. Microsoft Edge continues to be supported in at.js 2.5.0 and later.

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
