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

## Target Delivery API (August 3, 2021)

This release contains the following enhancements:

* The limit for mbox parameters has been increased to 100 parameters. The previous limit was 50 parameters. (TNT-41717)
* The limit for `categoryId` has been increased to 256 characters. The previous limit was 128 characters.
* The following [!DNL Adobe Audience Manager] (AAM) details have been added to the Delivery API:    

  * AAM UUID: The internal AAM ID used to uniquely identify a user. 
  * dataPartnerId: The ID for a data partner.
  * dataPartnerUserId: The user ID provided by a data partner.
  
  Previously, the Delivery API included `dcsLocationHint` and `blob` only. (TNT-41644)

## at.js 2.6.0 (July 16, 2021)

* Added secure attribute to cookies whenever at.js settings `secureOnly` is set to `true`.
* Response tokens are now available when using `triggerView()`.
* Fixed an issue related to the `CONTENT_RENDERING_NO_OFFERS` event. Now this event is triggered correctly whenever there is no content returned from [!DNL Target].
* [!DNL Anlytics for Target] (A4T) click metrics details are correctly returned when using `prefetch` requests.
* UUID generation no longer uses `Math.random()`, but relies on `window.crypto`.
* The `sessionId` cookie expiry is correctly extended on every network call.
* The [!UICONTROL Single Page Application] (SPA) view cache initialization is now correctly handled and honors `viewsEnable` settings.

## [!DNL Target Standard/Premium] 21.6.1 (June 30, 2021)

This release contains the following new features and enhancements. The issue numbers in parentheses are for internal [!DNL Adobe] use.

|Feature|Details|
| --- | --- |
|[!UICONTROL Analytics for Target] (A4T)|Clicking the "[!UICONTROL View in Analytics]" link on the [!UICONTROL Reports] page from an activity that uses [!DNL Analytics] as the reporting source (A4T), [!DNL Analysis Workspace] now opens. Previously, the link opened [!DNL Analytics] reporting. (TGT-36959)|

## Python SDK 1.0.0 (June 16, 2021)

The new [!DNL Adobe Target] Python SDK with on-device decisioning capabilities is now available. This newest addition bolsters the [!DNL Target] suite of server-side SDKs. These SDKS help you integrate with [!DNL Target] and expedite your time to value, in the language of your choice. Server-side integrations are becoming a popular choice given that the market is shifting to a cookie-less world in which first-party data is valuable. Target SDKs are available in the most popular programming languages in the market (Python, Java, JavaScript, C# / .Net).

For more information, see the [Python SDK documentation](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk) in the [Adobe Target SDKs guide](https://adobetarget-sdks.gitbook.io/docs/).

## ![Adobe Experience Platform Web SDK badge](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] version 2.5.0 (June 1, 2021)

This release of the [!DNL Platform Web SDK] includes support for the following:

|Feature|Details|
| --- | --- |
|Redirect support with [!UICONTROL Analytics for Target] (A4T)|The Platform Web SDK now supports [!DNL Target] redirects when using [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>For more information, see see [Analytics for [!DNL Target] implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).|

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
