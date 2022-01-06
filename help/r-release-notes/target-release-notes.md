---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: January 6, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>To avoid any potential issues with your sites, migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## !DNL Target Standard/Premium] 22.1.1 (January 6, 2022)

This release contains the following new feature:

|Feature|Details|
| --- | --- |
|Use Offer decisions in Target activities|You can now use [!DNL Adobe Journey Optimizer] offer decisions in [!DNL Adobe Target] A/B Test and Experience Targeting (XT) activities to determine and deliver the next best offer for your visitors on web and mobile.<br>For more information, see Use offer decisions.<br>**Note**: This capability is available for [!DNL Target] customers who also have access to Offer Decisioning and have a [!DNL Target] implementation based on Adobe Experiene Platform Web SDK.|

## at.js version 2.7.0 (October 28, 2021)

This release contains the following enhancement:

* Added support for [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components). This version of at.js is required to create and test personalized experiences and offers on custom elements and on elements inside custom elements. This functionality is included in the [!DNL Target Standard/Premium] 21.10.5 release.

## [!DNL Target Standard/Premium] 21.10.5 (October 28, 2021)

This maintenance release contains the following enhancement:

|Feature|Details|
| --- | --- |
|[!UICONTROL Visual Experience Composer] (VEC)|Added support for [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components). Personalized experiences and offers can be created and tested on custom elements and on elements inside custom elements.<br>For more information, see [Visual Experience Composer options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom).|

## [!DNL Target Standard/Premium] 21.10.4 (October 21, 2021)

This maintenance release contains the following enhancement:

|Feature|Details|
| --- | --- |
|Cart-based Recommendations|Added a new family of algorithms to deliver recommendations based on the contents of the visitor's cart.<br>For more information, see "Cart-Based" in [Create criteria](/help/c-recommendations/c-algorithms/create-new-algorithm.md) and "Cart adds/cart views/checkout pages" and "Exclude items already in the visitor's cart" in [Plan and implement Recommendations](/help/c-recommendations/plan-implement.md).|

## [!DNL Target Standard/Premium] 21.10.3 (October 19, 2021)

This maintenance release contains the following enhancements, fixes, and changes:

* Fixed issues that prevented customers from opening the [!UICONTROL A4T] panel in [!DNL Analysis Workspace] by clicking the [!UICONTROL View in Analytics] button in [!DNL Target] activity reporting. (TGT-42099, TGT-42100)
* Fixed an issue that caused the [!UICONTROL Edit Design] button to not display while editing [!UICONTROL A/B Test] and [!UICONTROL Experience Targeting] (XT) activities using the [!UICONTROL Form-Based Experience Composer]. (TGT-41980)
* Fixed an issue that prevented the [!UICONTROL Compatible] checkbox from displaying in criteria selection while creating a new [!UICONTROL Recommendations] activity. (TGT-42053)
* Fixed an incorrect error message that displayed when not being able to select [!DNL Analytics] as the reporting source (A4T) because of lack of [!DNL Analytics] permissions. (TGT-41954)
* Implemented multiple accessibility fixes to improve keyboard navigation across the [!DNL Target] UI.

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
