---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target], including SDKs, APIs, and JavaScript libraries.
landing-page-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: What Is Included in the Current Release?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
---
# Target release notes (current)

These release notes provide information about features, enhancements, and fixes for each [!DNL Adobe Target Standard] and [!DNL Target Premium] release. In addition, release notes for [!DNL Target] APIs, SDKs, the [!DNL Adobe Experience Platform Web SDK], at.js, and other platform changes are also included, when applicable.

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

## Target platform release (May 25, 2022)

This release contains the following enhancements and fixes:

* Added [User Agent Client Hints](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) support.
* Fixed an issue that intermittently caused timeouts when rendering [!UICONTROL Offer Decisions] in [!UICONTROL Experience Targeting] (XT) activities. (TNT-44611)

## at.js version 2.9.0 (May 27, 2022) 

* Added [User Agent Client Hints](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) support.
* Fixed a bug where multiple mbox requests on the same page have different impression IDs.

## [!DNL Target Standard/Premium] 22.5.1 (staggered release; May 11-13, 2022)

This release will be available according to the following staggered schedule:

* **May 11**: Asia-Pacific (APAC) region
* **May 12**: Americas region
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
* Fixed an issue that caused edits to profile scripts to revert to the original, unedited script after the script is edited, activated, and then deactivated. The profile script now remains in its edited state. (TGT-43249)
* Fixed an issue that caused the following error when attempting to move an audience to another workspace: "We cannot complete your request. Please contact Adobe Client Care if the problem persists". (TGT-43212)
* Fixed an error that caused an error when cloning custom code modifications for Single Page App (SPA) pages. (TGT-43137)
* Fixed an issue that caused the original promotion to be affected after duplicating an experience and then editing the promotion. (TGT-41775)

## Additional release notes and version details

|Resource|Details|
|--- |--- |
|[Release notes: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en)|Details about changes in each version of the Platform Web SDK.|
|[at.js version details](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)|Details about changes in each version of the [!DNL Adobe Target] at.js JavaScript library.|

## Documentation Changes, Past Release Notes, and Experience Cloud Release Notes

In addition to the notes for each release, the following resources provide additional information:

|Resource|Details|
|--- |--- |
|Documentation changes|View detailed information about updates to this guide that are not included in these release notes.<br>For more information, see [Documentation Changes](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C).|
|Release notes for previous releases|View information about new features and enhancements in previous releases of Target Standard and Target Premium.<br>For more information, see [Release notes for previous releases](/help/main/r-release-notes/release-notes-for-previous-releases.md).|
|Adobe Experience Cloud release notes|View the latest release notes for the Adobe Experience Cloud solutions.<br>For more information, see [Experience Cloud Release Notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html).|

## Prerelease Information {#section_5D588F0415A2435B851A4D0113ACA3A0}

The following resources let you see what's coming in the next Target release.

|Resource|Details|
|--- |--- |
|Adobe Priority Product Update|To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)|
|Upcoming release notes|For information about the current month's Target releases, including prerelease information, see the [Target Release Notes - Prerelease](/help/main/r-release-notes/target-release-notes.md) page.|
