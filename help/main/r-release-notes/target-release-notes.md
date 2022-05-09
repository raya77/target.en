---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features and Enhancements Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: May 9, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

## [!DNL Target Standard/Premium] 22.5.1 (staggered release; May 10-12, 2022)

This release will be available according to the following staggered schedule:

* **May 11**: Asia-Pacific (APAC) region
* **May 12**: North America (NA) region
* **May 13**: Europe, Middle East, and Africa (EMEA) region

This release contains the following enhancements and fixes:

* Fixed an issue that caused a JavaScript error and prevented some customers from accessing the activity details for certain [!UICONTROL Automated Personalization] (AP) activities. (TGT-43526)
* Fixed an issue that prevented some customers from adding (or editing) a specific offer to an AP activity. (TGT-43503)
* Fixed an issue in the [!DNL Target] UI that displayed the following error message: "Your global mbox may not be in sync. Please try resaving it." This issue was a UI issue and did not impact customers' implementations. (TGT-43475)
* Fixed an issue that prevented one customer from editing experience-level refinements and audiences for an activity if the refinements and audiences were created before the new [!UICONTROL Audiences] UI was deployed. (TGT-43433)
* Fixed an issue that allowed customers to select duplicate [!DNL Adobe Audience Manager] (AAM) audiences while editing reporting audiences for an activity. (TGT-43430)
* Fixed an issue that prevented customers from creating duplicate audiences, but in different workspaces. (TGT-43423)
* Fixed an issue that prevented customers from deleting locations that have ad-hoc offers in activities created in the [!UICONTROL Form-Based Experience Composer]. (TGT-43315)
* Fixed an issue that prevented customers from accessing code offers after clicking image offers and then refreshing the UI. (TGT-43566)
* Ensured that the list of metrics available in the [!DNL Target] UI when creating activities that use [!DNL Analytics for Target] (A4T) displays only those metrics that were collected by [!DNL Adobe Analytics]. (TGT-43294)
* Fixed an issue that caused edits to profile scripts to revert to the original, unedited script after the script is edited, activated, and then deactivated. The profile script now remains in its edited state. (TGT-43249)
* Fixed an issue that caused the following error when attempting to move an audience to another workspace: "We cannot complete your request. Please contact Adobe Client Care if the problem persists". (TGT-43212)
* Fixed an error that caused an error when cloning custom code modifications for Single Page App (SPA) pages. (TGT-43137)
* Fixed an issue that caused the original promotion to be affected after duplicating an experience and then editing the promotion. (TGT-41775)

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to [!DNL Target] and other [!DNL Adobe Experience Cloud] solutions, sign up for the [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
