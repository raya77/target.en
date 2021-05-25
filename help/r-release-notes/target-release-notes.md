---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: May 25, 2021**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>To avoid any potential issues with your sites, migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## ![Adobe Experience Platform Web SDK badge](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] version 2.5.0 (June 1, 2021)

This release of the [!DNL Platform Web SDK] includes support for the following:

|Feature|Details|
| --- | --- |
|Redirect support with [!UICONTROL Analytics for Target] (A4T)|The Platform Web SDK now supports [!DNL Target] redirects when using A4T. Redirect offers in [!DNL Adobe Target] cause a browser to redirect to a new page.|
|Response tokens|The Platform Web SDK now supports [!DNL Target] response tokens. Response tokens let you automatically output information specific to [!DNL Adobe Target] to your brand's web page. This information can include details about the activity, offer, experience, user profile, geo information, and more. These details provide extra response data to share with internal or 3rd-party systems or to use for debugging.|

## [!DNL Target Standard/Premium] 21.5.1 (June 8, 2021)

|Feature|Details|
| --- | --- |
|![Premium badge](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL Catalog Search] API|Search your [!DNL Recommendations] product and content catalog programmatically via API to identify items that match a search criteria and simplify administration of your catalog.<br>**Limitations and notes**:<ul><li>Catalog search via API is not supported for environments with more than 2,000,000 items.</li><li>Catalog search results via API are updated more rapidly than catalog search results via the [!DNL Target] UI. The catalog search in the [!DNL Target] UI can take additional time to reflect the latest results.</li></ul>For more information, see [Searching Entities](/http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) in the *[!DNL Adobe Target] [!DNL Recommendations] API* guide.|

## [!DNL Target Standard/Premium] 21.5.2 (Date to be determined)

This release contains the following new features and enhancements. The issue numbers in parentheses are for internal [!DNL Adobe] use.

|Feature|Details|
| --- | --- |
|![Premium](/help/assets/premium.png) [!DNL Recommendations]|The following enhancements apply to [!DNL Recommendations] popularity algorithms:<ul><li>A new six-hour "lookback window" (data range) option will be available for all popularity (Most Viewed/Top Sellers) algorithms when [!DNL Target] is the behavioral data source. (This lookback window is *not* available when [!DNL Adobe Analytics] is the behavioral data source.)</li><li>When selected, the following algorithms will run approximately every three hours (instead of every 12 hours).<ul><li>Most viewed</li><li>Most purchased</li><li>Most viewed by category</li><li>Most purchased by category</li><li>Most viewed by custom attribute (using groupBy feature)</li><li>Most purchased by custom attribute (using groupBy feature)</li></ul></ul>(TOP-1086)|

This release contains the following fixes.

* Content will be added as the release date approaches.

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
