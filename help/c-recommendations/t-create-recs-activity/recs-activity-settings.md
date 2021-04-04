---
keywords: Recommendations;Settings;name;objective;priority;duration;reporting settings;other metadata
description: Learn how to configure the settings used to describe and control a Recommendations activity in Adobe Target.
title: How Do I Configure Recommendations Activity Settings?
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
---
# ![PREMIUM](/help/assets/premium.png) Recommendations Activity settings{#recommendations-activity-settings}

Information about the settings you can use to describe and control a [!UICONTROL Recommendations] activity in [!DNL Adobe Target].

![Recommendations Goals & Settings page](/help/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

The following sections describe the available settings for a [!UICONTROL Recommendations] activity.

## Name

Provide a descriptive name that will help you and your team identify the activity.

The following characters are not allowed in an activity name:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

If you specify a [!UICONTROL Recommendations] activity name that already exists for another activity in [!UICONTROL Recommendations Classic], the new activity is resynced with a new name. The new name is the original name appended with a timestamp to make it unique. This new name is displayed in both [!DNL Target Standard/Premium] and [!UICONTROL Recommendations Classic].

## Objective

(Optional) Describe the goal of the activity.

## Priority

Adjust the slider to determine the priority level.

The priority is used if multiple activities are assigned to the same location with the same audience. If two or more activities are assigned to the location, the activity with the highest priority displays.

## Duration

Set the duration of the activity.

The activity can start when activated, or you can set a specific date and time. Likewise, the activity can either end when it is deactivated or you can set a date and time. The time picker uses a 24-hour clock, with 00:00 being midnight. The time zone is set to the time zone configured in your browser. To use a different time zone, set your browser to another time zone and restart the browser.

## Reporting Settings

* **Reporting Source:** Select the reporting source: [!DNL Adobe Target] or [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md). Do not change the reporting source after the activity goes live. Changing the reporting source after an activity goes live causes inconsistent reporting.
* **Goal Metric:** Select the success metric that determines whether the activity is successful.
* **Additional Metrics:** Configure additional success metrics to be used in your reports.
* **Audiences for Reporting:** Define audiences that can be used when filtering your reports.

## Other Metadata

Enter notes about your activity.

## Training video: Activity Settings (3:02) ![Tutorial badge](/help/assets/tutorial.png)

This video includes information about activity settings.

* Enter an objective for your activity 
* Set the priority level of your activities 
* Schedule activity start and end times 
* Add audiences for reporting to create report filters 
* Enter notes for your activities

>[!VIDEO](https://video.tv.adobe.com/v/17381)
