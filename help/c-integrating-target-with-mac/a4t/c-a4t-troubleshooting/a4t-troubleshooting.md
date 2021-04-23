---
keywords: analytics tracking server;A4T;analytics segments;report suites;incorrect data;orphaned;sdid;VisitorAPI.js;mboxMCSDID;phantom;unspecified
description: Explore common issues customers have encountered when using Analytics for [!DNL Target] (A4T).
title: How Do I Troubleshoot the Analytics and [!DNL Target] Integration (A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
---
# Troubleshoot the Analytics and [!DNL Target] integration (A4T)

This topic covers some common issues that have been encountered when using [!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T).

## Activities do not show data in Analytics, but are instead listed as "unspecified." {#unspecified}

There are several reasons why data shows as "unspecified" could happen:

* Classification in [!DNL Target] hasn't fully processed.

  Classification generally takes from 24 through 72 hours to classify reports after the first save.

* The report suite doesn't contain any data, but [!DNL Target] has tried to classify hits. [!DNL Target] cannot classify data until the first hit occurs.

  Ensure that the report suite has had at least one hit. 

* The classification call from [!DNL Target] to [!DNL Analytics] failed.

  [Contact Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for assistance.

If you break down the "unspecified" row by the "Analytics for Target" dimension and it consists no activity ids, it means that everything is classified properly. If activity ids are listed there, then it serves as an indication for a classification issue.

>[!NOTE]
>
>Sometimes data displays correctly in reports, but then reverts to "unspecified" because a new activity was added that hasn’t completed classification. Remember that it generally takes from 24 through 72 hours to classify reports after the first save.
>
>No data is lost when listed as "unspecified." The data is properly assigned to the appropriate activity or experience after the classification runs.

## A4T Activity reports include a row with many "unspecified" events. {#added_unspecified_events}

There might be an "[!UICONTROL Unspecified]" events row shown in your report, depending on the metric you use to display your data with.

Typically, this row displays if you choose a common metric in the report that is not [!DNL Target]-specific (for example, [!UICONTROL Page Views], [!UICONTROL Visits], [!UICONTROL Unique Visitors], and so forth). In this case, the [!UICONTROL “Unspecified”] row includes all the [!UICONTROL Page Views], [!UICONTROL Visits], and [!UICONTROL Unique Visitors] that are not associated to [!DNL Target] activities.

That row won’t have any [!DNL Target]-associated information (for example, no visitors, visits, or impressions). For more information, see [“Unspecified,” “None,” “Other,” and “Unknown” in reporting](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) in the *Analytics tech notes*.

If you choose a [!DNL Target]-specific metric in the report, that [!UICONTROL “Unspecified”] row does not display. The only way to avoid having it in the report altogether is to set a [!DNL Target] call on every request sent from that page, which is not common or necessary.

## My Analytics data shows an inflated visit or visitor count since starting A4T. {#section_4BE374E573D44FB7918611699B74F58E}

For more information, see [Minimizing Inflated Visit and Visitor Counts in A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Estimated lift in revenue metric does not show correct data. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Lift and confidence details are not available in Analytics. They are, however, available in the Target reports.

## Activities do not appear in Analytics reports. {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T activities require an analytics tracking server to be specified. See [Using an Analytics Tracking Server](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) to make sure that your Analytics Tracking Server is set up correctly.

>[!NOTE]
>
>You do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). The mbox.js or at.js library automatically sends tracking server values to [!DNL Target]. During activity creation, you can leave the [!UICONTROL Tracking Server] field empty on the [!UICONTROL Goals & Settings] page.

## My Analytics segments don't appear in Target. {#section_DEE87F1557834F448E99381D3D02EEEF}

Make sure you have the right permissions before you start creating A4T activities:

* Belong to the Web Services Access group in Adobe Analytics to be able to use Analytics as the reporting source for Target 
* Be a member of one or more Experience Cloud groups that have access to Analytics and Target. 
* Verify that Analytics and Target appear in the Marketing Apps section of the left navigation.

## Bounce rates, bounces, and exits metrics appear as positives in reports. {#section_B5C3D56EF0344407AE67ABEB93037F5A}

These metrics appearing as positives in reports is a known issue.

Although these metrics are negative, the lift is shown as if they were positive in the Target reports. For example, even though you want a lower bounce rate, the higher bounce rate is shown as the winner with highest lift. Be aware of these and similar metrics, and whether you'd prefer to decrease or increase the numbers, when making decisions based on your reports.

## The report suite I need does not display. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

The list of report suites that appears in [!DNL Target Standard/Premium] is the list of report suites that have been configured for [!DNL Analytics] as the reporting source for [!DNL Target] (A4T). You might not see every report suite that you have.

If you are using multiple reporting sources, the report suites must be present in the default reporting source set in [!DNL Target] as well. If the report suites are not in the default reporting source, the reports suites do not display.

If you still don't see the report suite that you are looking for, contact [Client Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to get it enabled.

## I'm not seeing as much data in reports as expected. {#section_75002584FA63456D8D9086172925DD8D}

Review your implementation, especially on pages where your visitors qualify for experiences and ensure that the supplemental data IDs match in the [!DNL Target] and [!DNL Analytics] calls. 

* **at.js 1.x**: In the [!DNL Target] call, the supplemental ID is contained in the `mboxMCSDID` parameter. In the [!DNL Analytics] call, the supplemental ID is contained in the `sdid` parameter.
* **at.js 2.x**: In the [!DNL Target] call, the supplemental ID is returned in the HTTP header as the value for `experienceCloud.analytics.supplementalDataId`. In the [!DNL Analytics] call, the supplemental ID is contained in the `sdid` parameter.

The easiest way to examine the supplemental ID is by using the Adobe Experience Platform Debugger.

If you have not installed the debugger, see [Introduction to the Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![Debugger](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

If there is no supplemental data ID in the [!DNL Target] call, confirm that the [!DNL VisitorAPI.js] file is loaded before [!DNL at.js] or [!DNL mbox.js]. If there is no supplemental data ID in the [!DNL Analytics] call, confirm that the [!DNL Target] call fires before the [!DNL Analytics] call.

For more information, see [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) or contact [Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
