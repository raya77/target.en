---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: April 16, 2021**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>To avoid any potential issues with your sites, migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.4.1 (April 19, 2021)

This release contains the following new features and enhancements. The issue numbers in parentheses are for internal [!DNL Adobe] use.

|Feature|Details|
| --- | --- |
|On-device decisioning support for at.js|On-device decisioning lets marketers and developers deliver experimentation and personalization on a user's browser at near-zero latency.<br>For more information, see [On-device decisioning for at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)<br>(Date to be announced)|
|![Premium](/help/assets/premium.png) List-based operators for entity filtering rules|[!DNL Target Recommendations] supports new list-based operators for entity filtering rules. (TGT-39234)<br>Newly added operators include:<br><ul><li>Is Contained In List</li><li>Is Not Contained In List</li><li>List Contains An Item In</li><li>List Does Not Contain An Item In</li><li>List Contains All Items In</li><li>List Does Not Contain All Items In</li></ul>For more information, see "Available operators" in [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators).|

This release contains the following fixes.

* Fixed an issue that prevented an activity from syncing after changing the audience to [!UICONTROL All Visitors]. (TGT-40259)
* Fixed an issue that prevented offers from being duplicated when used in different locations in [!UICONTROL Automated Personalization] activities even though the [!UICONTROL Disallow Duplicates] option is enabled. (TGT-39567)
* Fixed an issue that prevented the [!UICONTROL Administration] > [!UICONTROL Scene7 configuration] page from loading properly. (TGT-39918)
* Fixed an issue that caused properties to be mapped to the incorrect workspace. (TGT-39869)
* Fixed an issue that caused infinite loading if the request fails after changing the environment while creating a recommendations exclusion. (TGT-39948)

## at.js version 2.5.0 (Date to be announced)

This release of at.js includes the following enhancements and changes:

* [On-device decisioning](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) support for at.js.
* [Preview links](/help/c-activities/c-activity-qa/activity-qa.md) support for Automated Personalization activities

This release also removes support for Microsoft Internet Explorer 10 and above versions.

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
