---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features and Enhancements Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: July 18, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

## [!DNL Target Standard/Premium] 22.7.1 (July 20, 2022)

This release contains the following features, enhancements, and fixes:

|Feature|Description|
| --- | --- |
|Support for IPv6|IPv6 support is now provided in Edge delivery. A null value is returned for IPv6 (normal or dual) values.|
|A4T client-side payload handling enhancement|With A4T server-side integration, if Adobe Target identifies a request as coming from a bot, it does not forward the payload to Analytics, and there is no mod_stats event in recorded in the Target logs. Prior to this release, A4T client-side integrations would forward the payload to Analytics, even when it had been identified as bot traffic. This inconsistency between server- versus client-side would lead to discrepancies, as A4T reports for the latter included the bot traffic. Furthermore, bot traffic was not necessarily identified or flagged, meaning it was not possible to disambiguate or remove the bot traffic from the rest of the traffic. And even if a customer did account for bot traffic on their own, it would not necessarily match the set of traffic that Target identified and excluded as bot traffic, thus leading to split discrepancies or other issues. With this release, A4T client-side logging has been enhanced so that the behavior regarding the A4T payload is the same as with A4T server-side: Visitors that are identified as bots are excluded from Target counting/reporting, for both server-side and client-side implementations.|

## [!DNL Target Standard/Premium] 22.6.2 (June 30, 2022)

This release contains the following features, enhancements, and fixes:

|Feature|Description|
| --- | ---  |
|In-product notifications|Get the following relevant in-product notifications:<ul><li>**Activities**: Notifications for all activity types when an activity is approved or deactivated, either manually or when it reaches its start or end date. The notification includes the name of the activity with a link to the activity’s overview page.</li><li>**Profile scripts** Notifications when a profile script is activated or deactivated, either manually or by Target.</li><li>**Recommendations feeds**: Notifications when a Recommendations feed is activated or deactivated, either manually or by Target. Notifications are also sent when a Recommendations feed fails.</li></ul> By default, notifications are received by product admins, publishers, and approvers. Notifications are configurable inside Experience Cloud preferences.<br>For more information see [Notifications and announcements](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements).|
|*Adobe Target Developer Guide*|The *Adobe Target Developer Guide* consolidates all [!DNL Target] developer content in one convenient guide. The guide includes information about implementing [!DNL Target] and [!DNL Recommendations], [!DNL Target] SDKs, and [!DNL Target] APIs.<br>For more information, see [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.|

* Users with the [!UICONTROL Editor] role can no longer edit audiences in live activities. (TGT-43582)
* A warning message displays if a customer attempts to save an audience with an exclamation mark ( ! ) as the first character of the audience's name (for example !London). (TGT-43643)
* Fixed an issue that caused audiences definition details cards for some customers to indicate that an ended activity is still live. (TGT-43527)

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to [!DNL Target] and other [!DNL Adobe Experience Cloud] solutions, sign up for the [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
