---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: October 11, 2021**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>To avoid any potential issues with your sites, migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
