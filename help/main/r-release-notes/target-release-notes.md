---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features and Enhancements Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: April 13, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Platform release (April 13, 2022)

This release contains the following update:

* Fixed issue to ensure that the last octet of IP addresses are properly obfuscated when captured using profile scripts. (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1 (staggered release, date to be determined)

This release contains the following changes and enhancements:

* Fixed an issue that caused edits to profile scripts to revert to the original, unedited script after the script is edited, activated, and then deactivated. The profile script now remains in its edited state. (TGT-43249)
* Fixed an issue that caused the following error message in the [!DNL Target] UI when moving an audience used in an activity with the "draft" status: "We cannot complete your request. Please contact Adobe client-care if the problem persists." (TGT-43212)
* Fixed an issue that caused the [!UICONTROL Include] and [!UICONTROL Exclude] options to be disabled for combined audiences when editing an activity. (TGT-43422)
* Fixed an issue that prevented some customers from seeing the list of available audiences while editing an activity. (TGT-43404)
* Fixed an issue that prevented some customers from deleting an IP address from the "[!UICONTROL IPs to exclude from [!DNL Target] reporting data]" list in [!UICONTROL Administration] > [!UICONTROL Reporting]. (TGT-43384)
* Fixed an issue that prevented the use of negative numbers in audience criterion that check that any variable is "greater than," "greater than or equal to," "less than," or "less than or equal to." (TGT-43367)
* Fixed an issue that prevented customers from seeing the [!UICONTROL Audience Details] card when creating combined audiences. (TGT-43303)
* Fixed an issue that caused the [!DNL Target] UI or new [!UICONTROL Audiences] UI to prematurely time out for some customers. (TGT-42590 & TGT-43273)

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
