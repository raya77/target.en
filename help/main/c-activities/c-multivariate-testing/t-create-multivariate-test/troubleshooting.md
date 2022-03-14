---
keywords: Multivariate Tests;troubleshoot;troubleshooting;mvt
description: Explore potential challenges you might face while using Multivariate Test (MVT) activities in Adobe Target, along with suggested solutions.
title: How Do I Troubleshoot Multivariate Tests?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
---
# Troubleshoot Multivariate Tests

This topic contains suggestions for resolving some issues that might occur when designing a [!UICONTROL Multivariate] (MVT) test in [!DNL Adobe Target].

* When editing an activity, if you used [!DNL Analytics]-based metrics and the report suite doesn't load (spinner displays), switch the metrics to [!DNL Target] metrics and then switch again to [!DNL Analytics]-based metric. The report suite should now load. 
* If you make changes to a test that is already running, you might reset the test and its data.

  [!DNL Target] lets you edit a live activity. Be aware that editing an activity that is in progress could reset the test, so reports might not recognize some of the changes.

  It is safe to make small changes, such as editing existing text or html offers.

  The specific actions that reset experience names and reports are:

  * Adding a new location
  * Deleting a location
  * Adding new offers or deleting offers from an exiting location
