---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: March 1, 2021**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages might be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: On March 31, 2021, [!DNL Adobe Target] will no longer support the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>Adobe recommends that all customers migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library before this date to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.2.1 (March 9, 2021)

This maintenance release contains the following enhancements, fixes, and changes.

The issue numbers in parentheses are for internal [!DNL Adobe] use.

* Increased the allowable offer size (TGT-38304):

  |Type|Previous Limit|New Limit|
  | --- | --- | --- |
  |HTML|256 KB|1024 KB|
  |Visual offers from the Target UI|64 KB|1024 KB for each experience|
  |Via API|512 KB|1024 KB|

* [!UICONTROL Personalization Insights] reports for [!UICONTROL Auto-Target] (AT) and [!UICONTROL Automated Personalization] (AP) activities are now produced on a daily basis. You can choose a report providing [!UICONTROL Automated Segments] or [!UICONTROL Important Attributes] for the last 15, 30, and 60 days. The 45 and 90 day options have been removed to enable the other lookback window settings to run on a daily basis. (TGT-39472)
* Fixed an issue that caused the current dependency to not display when customers click [!UICONTROL Edit Dependency] on an activity's [!UICONTROL Goals & Settings] page. (TGT-39340)
* Fixed an issue when refreshing a workspace's [!UICONTROL Audience Library]. Before the refresh, the audiences for the currently selected workspace displayed. After the refresh, the [!UICONTROL Default Workspace] and its audiences displayed. The current workspace and its audiences now persist after the refresh. (TGT-38871) 
* Fixed an issue when copying a [!UICONTROL Recommendations] activity and later editing the original activity by changing its criteria sequence. The change in the criteria sequence in the original activity was also incorrectly applied to the copied activity. (TGT-39155)
* Fixed an issue that caused the incorrect number of products to display for [!UICONTROL Recommendations] exclusions. (TGT-39599)

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
