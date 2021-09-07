---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action;event codes
description: Find answers to questions about classifications and using [!UICONTROL Analytics for Target] (A4T).
title: Where Can I Find Information About Classifications with A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
---
# Classifications - A4T FAQ

This topic contains answers to questions that are frequently asked about classifications and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## After using the [!UICONTROL Classifications Importer] to download classifications, how do I match the post-tnt-action value with an activity name? {#section_6045DAC488B248418F430E663C38D001}

You can download the classifications for the A4T/TNT string from the Admin Tools [Classification Importer](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html). The variable is called “TNT” in the export list. The downloaded data includes the friendly names for activities, experiences, and so forth.

This lookup file is useful for customers that receive [!DNL Adobe]’s clickstream data feed. The file provides friendly names for the `post_tnt` and `post_tnt_action` columns.

For standard [!UICONTROL A/B Test] and [!UICONTROL Experience Targeting] (XT) activities, the format of the TNT string is:

```
activityID:experienceID:targettype|event
```

For [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities, the format of the TNT string is:

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` and `algorithmId` are internal identifiers used by [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target] activities.
* Event = 0 represents an experience entrance. 
* Event = 1 represents an experience visit. 
* Event = 2 represents an activity impression. 
* Event = 3-32766 represents analytics success metric id.
* Event = 32767 represents an activity conversion.
* Event -1 or 65535 represents that the user is removed from the activity or experience. This situation often happens when the visitor converts. The visitor is released from the experience and is now available to qualify for any other experience.

You can import the classification file on a frequent basis from the UI using a [browser import](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) or an [FTP import](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). You can also engage with Engineering Services to obtain the file as a lookup table along with a clickstream data feed.
