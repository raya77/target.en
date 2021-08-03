---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: August 3, 2021**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>To avoid any potential issues with your sites, migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.8.1 (August 4, 2021)

This maintenance release contains many backend enhancements, including the following customer-facing change:

* Fixed an issue that caused reports for [!UICONTROL Auto Personalization] activities created in the [!UICONTROL Form-Based Experience Composer] to reference deleted offers in reports. This issued caused the following error message to display, "We are having trouble retrieving data for this report. Please contact Adobe Client Care if the problem persists." (TGT-41028)

## Target Delivery API (August 3, 2021)

This release contains the following enhancements:

* The limit for mbox parameters has been increased to 100 parameters. The previous limit was 50 parameters. (TNT-41717)
* The limit for `categoryId` has been increased to 256 characters. The previous limit was 128 characters.
* The following [!DNL Adobe Audience Manager] (AAM) details have been added to the Delivery API:    

  * AAM UUID (Adobe Audience Manager Unique User ID)
  * dataPartnerId
  * dataPartnerUserId
  
  Previously, the Delivery API included `dcsLocationHint` and `blob` only. (TNT-41644)

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
