---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target], including SDKs, APIs, and JavaScript libraries.
landing-page-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: What New Features Are Included in the Current Release?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
---
# Target release notes (current)

These release notes provide information about features, enhancements, and fixes for each [!DNL Adobe Target Standard] and [!DNL Target Premium] release. In addition, release notes for Target APIs, SDKs, the [!DNL Adobe Experience Platform Web SDK], at.js, and other platform changes are also included, when applicable.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>Migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

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

## [!DNL Target Standard/Premium] 21.10.2 (October 13, 2021)

The following enhancements have been added when using [!DNL Target] [!UICONTROL Audiences] with the [!DNL Adobe Experience Platform Web SDK]:

* Added warning icons, popovers, and messages in various places in the [!DNL Target] UI to indicate that the audience was deleted at the source and is no longer available for use in [!DNL Target] activities.

  The following illustrations show some of the places the icons, popovers, and messages display:

  * [!UICONTROL Activity] list page

    ![Audience deleted at source message on Activities list page](assets/deleted-at-source-audiences-list.png)

  * Activity [!UICONTROL Overview] pages:

    ![Audience deleted at source message on overview page](assets/deleted-at-source-overview.png)

  * [!UICONTROL Experiences] step of the activity-creation workflow:

    ![Audience deleted at source message on [!UICONTROL Experiences] page](assets/deleted-at-source-experiences.png)

  * [!UICONTROL Targeting] step of the activity-creation workflow:

    ![Audience deleted at source message on [!UICONTROL Targeting] page](assets/deleted-at-source-targeting.png)

  * [!UICONTROL Goals & Settings] step of the activity-creation workflow:

    ![Audience deleted at source message on the [!UICONTROL Goals & Settings] page](assets/deleted-at-source-goals-settings.png)

  * Audience refinements ([!UICONTROL Replace Audience] on the [!UICONTROL Targeting] step of the activity-creation workflow):

* If you attempt to use the Combine Audiences feature and one of audiences was deleted at the source, [!UICONTROL Save] is disabled. 

## [!DNL Target Standard/Premium] 21.10.1 (October 6, 2021)

This release contains the following new features:

|Feature|Details|
| --- | --- |
|[!UICONTROL Audiences] UI refresh|As part of the [!DNL Adobe Target] team's ongoing effort to improve the user-experience for [!DNL Target] users, this release refreshes the [!UICONTROL Audiences] and [!UICONTROL Profile Scripts] pages in the [!DNL Target] UI. This update unifies and standardizes design patterns that were previously inconsistent, while adding new enhancements, such as:<ul><li>The ability to select and delete multiple audiences simultaneously</li><li>A refreshed [audience builder design](/help/c-target/c-audiences/create-audience.md)</li><li>Exclusion rule support in the [!UICONTROL Audience] library rule builder</li><li>A new “Audience Source” filter, to allow for faster audience discovery</li><li>Session persistent search and filter options</li></ul>For more information, see [Audiences](/help/c-target/target.md).<br>**NOTE**: The new [!UICONTROL Audiences] UI is available to select customers only. The update will be gradually rolled out to all customers starting in January 2022.|
|[!UICONTROL Profile Scripts] UI refresh|The [!UICONTROL Profile Scripts] library was also updated, and includes a refreshed interface along and several productivity updates:<ul><li>The ability to select and delete multiple profile scripts simultaneously</li><li>A new code editor for profile scripts</li><li>Syntax highlighting and error checking inside the code editor</li><li>Auto-complete tokens (mbox or profile) parameters through keyboard shortcuts</li></ul>For more information, see [Visitor Profiles](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**NOTE**: The new [!UICONTROL Profile Scripts] UI is available to select customers only. The update will be gradually rolled out to all customers starting in January 2022.|
|![Premium badge](/help/assets/premium.png) Recommendations Criteria create and edit|The [!UICONTROL Recommendations Criteria] creation and editing workflow has been streamlined to simplify choosing the right recommendations algorithm and settings to achieve your goals.<br>For more information, see [Create criteria](/help/c-recommendations/c-algorithms/create-new-algorithm.md).|
|![Premium badge](/help/assets/premium.png) Recommendations lookback window and algorithm refresh rate improvements|You can now run "Most Viewed" and "Top Sellers" algorithms with a six-hour lookback window to capture the content that's trending most recently. When the six-hour lookback window is selected, your recommendations results are updated every 3-6 hours throughout the day.<br>For more information, see [Data Source](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) in *Create criteria*.|

## Additional release notes and version details

|Resource|Details|
|--- |--- |
|[Release notes: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en)|Details about changes in each version of the Platform Web SDK.|
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
