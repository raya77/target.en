---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: October 6, 2021**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>To avoid any potential issues with your sites, migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.1 (October 6, 2021)

This release contains the following new features:

|Feature|Details|
| --- | --- |
|[!UICONTROL Audiences] UI refresh|As part of the [!DNL Adobe Target] team's ongoing effort to improve the user-experience for [!DNL Target] users, this release refreshes the [!UICONTROL Audiences] and [!UICONTROL Profile Scripts] pages in the [!DNL Target] UI. This update unifies and standardizes design patterns that were previously inconsistent, while adding new enhancements, such as:<ul><li>The ability to select and delete multiple audiences simultaneously</li><li>A refreshed [audience builder design](/help/c-target/c-audiences/create-audience.md)</li><li>Exclusion rule support in the [!UICONTROL Audience] library rule builder</li><li>A new “Audience Source” filter, to allow for faster audience discovery</li><li>Session persistent search and filter options</li></ul>For more information, see [Audiences](/help/c-target/target.md).<br>**Note**: The new [!UICONTROL Audiences] and [!UICONTROL Profile Scrips] UI will be rolled out to all regions next week.|
|[!UICONTROL Profile Scripts] UI refresh|The [!UICONTROL Profile Scripts] library was also updated, and includes a refreshed interface along and several productivity updates:<ul><li>The ability to select and delete multiple profile scripts simultaneously</li><li>A new code editor for profile scripts</li><li>Syntax highlighting and error checking inside the code editor</li><li>Auto-complete tokens (mbox or profile) parameters through keyboard shortcuts</li></ul>For more information, see [Visitor Profiles](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**Note**: The new [!UICONTROL Audiences] and [!UICONTROL Profile Scrips] UI will be rolled out to all regions next week.|
|![Premium badge](/help/assets/premium.png) Recommendations Criteria create and edit|The [!UICONTROL Recommendations Criteria] creation and editing workflow has been streamlined to simplify choosing the right recommendations algorithm and settings to achieve your goals.<br>For more information, see [Create criteria](/help/c-recommendations/c-algorithms/create-new-algorithm.md).|
|![Premium badge](/help/assets/premium.png) Recommendations lookback window and algorithm refresh rate improvements|You can now run "Most Viewed" and "Top Sellers" algorithms with a six-hour lookback window to capture the content that's trending most recently. When the six-hour lookback window is selected, your recommendations results are updated every 3-6 hours throughout the day.<br>For more information, see [Data Source](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) in *Create criteria*.|

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
