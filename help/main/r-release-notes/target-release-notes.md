---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Learn about the new features, enhancements, and fixes included in the upcoming release of Adobe Target, including SDKs, APIs, and JavaScript libraries.
title: What New Features and Enhancements Are Included in the Upcoming Release?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
---
# Target release notes (prerelease)

This article contains prerelease information. Release dates, features, and other information are subject to change without notice. 

**Last Updated: July 20, 2022**

To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages could be the same, depending on the timing of releases. The issue numbers in parentheses are for internal [!DNL Adobe] use.

## [!DNL Target] platform release (July 20, 2022)

This release contains the following features, enhancements, and fixes:

|Feature|Description|
| --- | --- |
|Improved audience evaluation accuracy and reduced end-user latency through IPv6 support (TNT-43364, TNT-44692) |Visitors' geo-locations are now determined by IPv6 addresses, if available, as opposed to only IPv4 addresses. Delivery APIs also support IPv6 input parameters. Filtering and allow-listing support both IPv4 and IPv6 addresses. The IPv6 support in this release means visitors will be more accurately included in audiences (more accurately qualify for activities or be included in filtering criteria). It also improves data latency, as IPv6 clients will route directly, avoiding the overhead of the the IPv6-to-IPv4 gateway.|
|Fixed A4T client-side payload handling issue (TNT-44926)|With A4T server-side integration, if Adobe Target identifies a request as coming from a bot, it does not forward the payload to Analytics, and there is no mod_stats event in recorded in the [!DNL Target] logs. <!--- Prior to this release, A4T client-side integrations would forward the payload to [!DNL Analytics], even when it had been identified as bot traffic. This inconsistency between server- versus client-side would lead to discrepancies, as A4T reports for the latter included the bot traffic. Furthermore, bot traffic was not necessarily identified nor flagged, meaning it was not possible to disambiguate or remove the bot traffic from the rest of the traffic. And even if a customer did account for bot traffic on their own, it would not necessarily match the set of traffic that [!DNL Target] identified and excluded as bot traffic, thus leading to split discrepancies or other issues. ---> With this release, A4T client-side logging has been enhanced so that the behavior regarding the A4T payload is the same as with A4T server-side: Visitors that are identified as bots are excluded from [!DNL Target] counting/reporting, for both server-side and client-side payload handling. (Note this issue was limited to implementations that used client-side payload handling; server-side was not impacted. With this release, the behavior is now consistent for both server-side and client-side.)|


## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to [!DNL Target] and other [!DNL Adobe Experience Cloud] solutions, sign up for the [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
