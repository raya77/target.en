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

## [!DNL Target] platform release (July 20, 2022)

This release contains the following features, enhancements, and fixes:

|Feature|Description|
| --- | --- |
|Improved audience evaluation accuracy and reduced end-user latency through IPv6 support (TNT-43364, TNT-44692) |Visitors' geo-locations are now determined by IPv6 addresses, if available, as opposed to only IPv4 addresses. Delivery APIs also support IPv6 input parameters. Filtering and allow-listing support both IPv4 and IPv6 addresses. The IPv6 support in this release means visitors will be more accurately included in audiences (more accurately qualify for activities or be included in filtering criteria). It also improves data latency, as IPv6 clients will route directly, avoiding the overhead of the the IPv6-to-IPv4 gateway.|
|Fixed A4T client-side payload handling issue (TNT-44926)|With A4T server-side integration, if Adobe Target identifies a request as coming from a bot, it does not forward the payload to Analytics, and there is no mod_stats event in recorded in the [!DNL Target] logs. With this release, A4T client-side logging has been enhanced so that the behavior regarding the A4T payload is the same as with A4T server-side: Visitors that are identified as bots are excluded from [!DNL Target] counting/reporting. (Note the issue in question was limited to implementations that used client-side payload handling; server-side was not impacted. With this release, the behavior is now consistent for both server-side and client-side payload handling.)|

## [!DNL Target Standard/Premium] 22.6.2 (June 30, 2022)

This release contains the following features, enhancements, and fixes:

|Feature|Description|
| --- | ---  |
|In-product notifications|Get the following relevant in-product notifications:<ul><li>**Activities**: Notifications for all activity types when an activity is approved or deactivated, either manually or when it reaches its start or end date. The notification includes the name of the activity with a link to the activity’s overview page.</li><li>**Profile scripts** Notifications when a profile script is activated or deactivated, either manually or by Target.</li><li>**Recommendations feeds**: Notifications when a Recommendations feed is activated or deactivated, either manually or by Target. Notifications are also sent when a Recommendations feed fails.</li></ul> By default, notifications are received by product admins, publishers, and approvers. Notifications are configurable inside Experience Cloud preferences.<br>For more information see [Notifications and announcements](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements).|
|*Adobe Target Developer Guide*|The *Adobe Target Developer Guide* consolidates all [!DNL Target] developer content in one convenient guide. The guide includes information about implementing [!DNL Target] and [!DNL Recommendations], [!DNL Target] SDKs, and [!DNL Target] APIs.<br>For more information, see [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.|

* Users with the [!UICONTROL Editor] role can no longer edit audiences in live activities. (TGT-43582)
* A warning message displays if a customer attempts to save an audience with an exclamation mark ( ! ) as the first character of the audience's name (for example !London). (TGT-43643)
* Fixed an issue that caused audiences definition details cards for some customers to indicate that an ended activity is still live. (TGT-43527)

## [!DNL Target Standard/Premium] 22.6.1 (staggered release: June 7-9, 2022)

This release will be available according to the following staggered schedule:

* **June 7**: Asia-Pacific (APAC) region
* **June 8**: Americas region
* **June 9**: Europe, Middle East, and Africa (EMEA) region

This release contains the following enhancements and fixes:

* An enhancement was delivered for the new [!UICONTROL Audiences] page to prevent an inconsistent state between the old database where the audiences were stored in the past and the new architecture that is retrieving the information directly from the backend. (TGT-43552)
* Fixed an issue that prevented some customers from saving combined audiences caused by the Target UI creating "empty" containers. (TGT-43588)

## Target platform release (May 25, 2022)

This release contains the following enhancements and fixes:

* Added [User Agent Client Hints](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank} support.
* Fixed an issue that intermittently caused timeouts when rendering [!UICONTROL Offer Decisions] in [!UICONTROL Experience Targeting] (XT) activities. (TNT-44611)

## at.js version 2.9.0 (May 27, 2022) 

* Added [User Agent Client Hints](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank} support.
* Fixed a bug where multiple mbox requests on the same page have different impression IDs.

## Additional release notes and version details

|Resource|Details|
|--- |--- |
|[Release notes: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en)|Details about changes in each version of the Platform Web SDK.|
|[at.js version details](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}|Details about changes in each version of the [!DNL Adobe Target] at.js JavaScript library.|

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
