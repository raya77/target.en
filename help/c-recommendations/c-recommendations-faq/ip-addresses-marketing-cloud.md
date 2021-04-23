---
keywords: IP address;IP addresses;whitelist;allowlist;firewall;recs;feed;servers;adobe marketing cloud;recommendations
description: View a list of IP addresses used in [!DNL Target] Recommendations feed-processing servers to help you configure your firewall to allow IP addresses originating from Adobe servers.
title: What IP Addresses Do Recommendations Feed-Processing Servers Use?
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
---
# ![PREMIUM](/help/assets/premium.png) IP addresses used by Recommendations feed-processing servers

List of IP addresses used in [!DNL Adobe Target] [!DNL Recommendations] feed-processing servers to help you configure your firewall to allow IP addresses originating from Adobe servers.

[!DNL Target] [!UICONTROL Recommendations] activities use the following AWS hosts when accessing customers' FTP servers:

| Location | Host |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] APIs also use the same AWS hosts.

>[!NOTE]
>
>These IP addresses were last updated on March 16, 2021. Previously, the servers accessing the FTP servers were in the 192.243.242.0/24 IP address CIDR block. The servers hosting Recommendations APIs were in the 192.243.224.0/20 IP address CIDR block.
