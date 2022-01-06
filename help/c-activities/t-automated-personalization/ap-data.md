---
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes;personalization algorithms;machine-learning algorithms;machine learning algorithms
description: Learn which data Adobe [!DNL Target] collects and uses to build its machine-learning algorithms in Automated Personalization (AP) and Auto-Target (AT) activities.
title: What Data is Collected to Build Machine-Learing Algorithms?
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
---
# ![PREMIUM](/help/assets/premium.png) Data used by [!DNL Target] machine learning algorithms

[!DNL Adobe Target] automatically collects and uses a variety of data to build its personalization algorithms in [!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] (AT) activities. When a visitor enters an AP or AT activity, a snapshot of information is passed to a set of "training records" (the visitor data that the personalization algorithms will learn on).

To learn more about the [!DNL Target] personalization algorithms, see [Random Forest Algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md).

## Default Adobe Target attribute categories

The following table shows the data collected by [!UICONTROL Automated Personalization] and [!UICONTROL Auto-Target] activities by default, without any configuration of [!DNL Target] or other [!DNL Adobe] solutions, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). You can augment the input data set at any time. To learn more about how to upload additional data, see [Uploading data for the [!DNL Target] personalization algorithms](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

|Data category|System prefix|Description|Display name in [!UICONTROL Insights] reports|
| --- | --- | --- | --- |
|Environment parameters|ENV|Information about a user’s environment, including operating system, browser, and time of day/day of week.|Browser - [Attribute Name]<br>Operating System - [Value]|
|Geography|GEO|Information about a user’s geography, obtained via IP lookup.|Geo - [geo attribute]|
|Mobile device|MOB|Information about a user’s mobile device.|Device - [device attribute]<br>Mobile - [mobile attribute]|
|Target reporting segments|SEG|Reporting segments configured in [!DNL Target] reporting.|Reporting Segment -[Segment Name]|
|Session behavior|SES|Information about user behavior, such as number of pages viewed.|Visitor Profile - [Attribute Name]|

## Custom Adobe Target attribute categories

The following table shows the customer-provided data collected by by [!UICONTROL Automated Personalization] and [!UICONTROL Auto-Target] activities. This data is collected only if you provide it, and as such, Adobe cannot describe this data like we can describe the data for other categories.

|Data category|System prefix|Description|Display name in [!UICONTROL Insights] reports|
| --- | --- | --- | --- |
|Page parameters|BOX|Custom page parameters (“mbox parameters”) passed in the call to [!DNL Target].|Custom - Mbox Parameter - [parameter name]|
|Target profile|PRO|Custom profile attributes directly uploaded to the [!DNL Target] profile via API or page parameter and [!DNL Target] profile scripts.|Custom - Visitor Profile - [attribute name]|
|Customer attributes|CRS|Customer Attributes uploaded to the Target Profile via the [Adobe Experience Cloud Customer Attributes Service](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}.|Custom - Visitor Profile - [attribute name]|
|URL parameters|URL|URL and any URL parameters for the currently-viewed page.|Custom - URL Parameter - [URL Parameter]|
|Referring URL|REF|Referring URL and any URL parameters for the referring URL.|Custom - [Referring URL Parameter] - [Parameter value]|
|Adobe Experience Cloud shared audiences|AAM|All audiences shared with [!DNL Target] from other [!DNL Adobe Experience Cloud] solutions (for example, [!DNL Adobe Audience Manager] and [!DNL Adobe Analytics], via the [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}).|Custom - Experience Cloud Audience - [Audience Name]|
|Adobe Experience Platform RTCDP audiences|UPS|AEP RTCDP Audiences shared with [!DNL Target] via Destinations.<br>Note that this functionality is not yet in [!DNL Target] but will be implemented in the future.||

## Blocking features from [!DNL Target] machine-learning algorithms

Features can be blocked from [!DNL Target] machine-learning algorithms, preventing them from being used in any [!UICONTROL Auto-Target] or [!UICONTROL Automated Personalization] model or activity. 

To block a category of features from [!DNL Target] machine-learning algorithms, contact [Adobe Customer Care](/help/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) and specify the feature categories you want blocked, using the above provided System Prefix(es). 

To block one or more specific features from [!DNL Target] machine-learning algorithms, contact [Adobe Customer Care](/help/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) and specify the specific feature names that should be blocked, using the below provided system name(s). The following sections contain detailed information about the various data types, including attribute names, descriptions, and sample values. 

## Device and mobile data {#device-mobile}

|Attribute name|Attribute description|Sample values|System name|
| --- | --- | --- | --- |
|Mobile - Device - Brand|The brand of the mobile device the visitor used to access the activity.|Apple||
|Mobile - Device - eReader|Specifies whether the device is an eReader.|0 is False, 1 is True||
|Mobile - Device - Game Console|Specifies whether the device is a game console.|0 is False, 1 is True||
|Mobile - Device - Media Player|Specifies whether the device is a media player.|0 is False, 1 is True||
|Mobile - Device - Mobile Phone|Specifies whether the device is a mobile phone.|0 is False, 1 is True||
|Mobile - Device - Model Name|The model name of the mobile device the visitor used to access the activity.|iPhone XS||
|Device - Set-Top Box|Specifies whether the device is a set-top box.|0 is False, 1 is True||
|Mobile - Device - Tablet|Specifies whether the device is a tablet.|0 is False, 1 is True||
|Mobile - Pixel Density (ppi)|The mobile device's pixel density the visitor used to access the activity.|1, 2, 3, etc.||
|Mobile - OS – OSX (Android, Windows, etc.)|Specifies whether the user used an OSX (or Android, Windows, etc.) device to access the activity.|0 is False, 1 is True||
|Mobile - Screen Height (px)|The mobile device's screen height (in pixels) the visitor used to access the activity.|1, 2, 3, etc.||
|Mobile - Screen Width (px)|The mobile device's screen width (in pixels) the visitor used to access the activity.|1, 2, 3, etc.||

## Environmental data {#env}

|Attribute name|Attribute description|Sample values|System name|
| --- | --- | --- | -- |
|Browser - Day of Week|The day of the week when the visitor accessed the activity.|0 to 6.<br>(0 is Sunday)||
|Browser - Hour of Day|The hour of the day when the visitor accessed the activity.|0 to 23<br>(0 is midnight)||
|Browser - Hour of Week|The hour of the week when the visitor accessed the activity.|0 to 168<br>(Sunday midnight is 0)||
|Browser - Language Setting|The language specified in the visitor's browser used to access the activity.|English<br>German||
|Browser - Screen Height (px)|The device's browser screen height (in pixels) the visitor used to access the activity.|1, 2, 3, etc.||
|Browser - Time of Day|The browser's time of day when the visitor accessed the activity.|0, 6, 12, 18<br>(0 is night, 6 is morning,<br>12 is afternoon, 18 is evening)||
|Browser - Timezone|The visitor's time zone while accessing the activity.|Pacific Time<br>Eastern Time<br>GMT||
|Browser - Type|The type of browser the visitor used while accessing the activity.|Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other||
|Browser - Weekday/Weekend|The work status when the visitor accessed the activity (weekend, work hours, or weekday free-time).|Saturday and Sunday is weekend<br>Monday-Friday 0900 to 1800 is work time<br>Monday-Friday after 1800 until 0900 is weekday free time||
|Browser - Window Height (px)|The browser's window height (in pixels) the visitor used to access the activity.|1, 2, 3, etc.||
|Browser - Window Width (px)|The browser's window width (in pixels) the visitor used to access the activity.|1, 2, 3, etc.||
|Device - Screen Height|The device's screen height the visitor used to access the activity.|1, 2, 3, etc.||
|Device - Screen Width|The device's screen width the visitor used to access the activity.|1, 2, 3, etc.||
|Operating System|The operating system on the visitor's device used to access the activity.|Mac OS<br>Windows<br>Linux<br>Search Bot<br>Unknown OS||
|Operating System - Version|The operating system's version the visitor used to access the activity.|Windows 10<br>Mac OS 10||
|Traffic Sources - Referring Landing Page URL|The first page the visitor saw when accessing your site.|`https://www.adobe.com/ecloud.html`||

## Geographical data {#geo}

|Attribute name|Attribute description|Sample values|System name|
| --- | --- | --- | --- |
|Geo - City|The city from which the visitor accessed the activity.|San Francisco||
|Geo - Country|The country from which the visitor accessed the activity.|Germany||
|Geo - DMA|The Designated Marketing Area (DMA) from which the visitor accessed the activity.|Charlottesville||
|Geo - Latitude|The latitude from which the visitor accessed the activity.|47.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy)||
|Geo - Longitude|The longitude from which the visitor accessed the activity.|-122.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy)||
|Geo - State/Region|The state or region from which the visitor accessed the activity.|Utah<br>New South Wales||
|Geo - Zip Code|The Zip Code from which the visitor accessed the activity.|84004||
|Mobile - Carrier|The mobile carrier the visitor used when accessing the activity.|Vodafone<br>T-Mobile||
|Network - Connection Speed|The network connection speed of the device when the visitor accessed the activity.|Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite||
|Network - Domain Name|The name of the network domain from which the visitor accessed the activity.|`nnt.net`||
|Network - ISP|The network from which the visitor accessed the activity.|nnt communications corporation||

## Session data {#session}

|Attribute name|Attribute description|Sample values|System name|
| --- | --- | --- | --- |
|Visitor Profile - Activity Lifetime Order Value|Specifies the sum of all order values across all visits/sessions to a particular activity.|Double||
|Visitor Profile - Activity Lifetime Time on Site|Specifies the visitor's total time spent on site, excluding the current session, and is updated when the session expires.|Double, milliseconds||
|Visitor Profile -Average Page Views per Visit during Activity|Specifies the average number of page views per session, excluding the current session.|Double||
|Visitor Profile - Average Time per Visit|Specifies the average time spent per visit/session. This does not include the current session.|Double, milliseconds||
|Visitor Profile - First Visit|Specifies the time of the first visit that the user interacted with Target.|Double, milliseconds||
|Visitor Profile - Hours since Last Visit|Specifies the hours since the last visit to this particular activity.|Double (Only integer positive number) 1, 2, 3, etc.||
|Visitor Profile - Impressions of Location/Content|Specifies the number of impressions to a particular location/content combination in a particular activity.|Double (Only integer positive number) 1, 2, 3, etc.||
|Visitor Profile - Last Target Interaction|Specifies the time of last interaction with Target. Interaction happens on every [!DNL Target] request because the current implementation of [!DNL Target] updates the profile on each request.|Double, milliseconds||
|Visitor Profile - Pages Seen Before Activity|Specifies the number of total page views (impressions), including current visit/session until the visitor enters the activity.|Double (Only integer positive number) 1, 2, 3, etc.||
|Visitor Profile - Page Views in Current Visit|Specifies the number of page views in current visit/session until the visitor enters the activity. More precisely, the number of impressions. These impressions are not real page views, rather this is the number of times the request reached Target. Target is not capable of distinguishing between timeouts or any other reasons the user did not receive or view the content.|Double (Only integer positive number)||
|Visitor Profile - Start of Current Visit|Specifies the time when the current visit/session with Target started. The visit with Target can be initiated without entering an activity. All that is required is a call to any [!DNL Target] request. A visitor might take awhile until entering the activity and the snapshot is taken.|Double, milliseconds||
|Visitor Profile - Start of Most Recent Visit|Specifies the time of when last visit/session with Target started. This attribute gets updated when the session expires.<br>If this is the first session for the visitor, it will result in `LAST_SESSION_START = 0.`|Double, milliseconds||
|Visitor Profile - Time Since Most Recent Visit When First Enter Activity|Specifies the duration between the previous session and the time when the user enters the activity and the snapshot is performed.|Double, milliseconds||
|Visitor Profile - Time in Visit Before Enter Activity|Specifies the difference between the last interaction with Target and when the current visit started. This attribute could be considered visit/session duration until the user enters the activity and the snapshot is performed.<br>Negative values happen when the session start and the last update time is triggered by the same [!DNL Target] call. Negatives values should be considered as 0 (zero).|Double, milliseconds||
|Visitor Profile -Total Visits|Specifies the total number of visits/sessions. Does not include the current visit/session.|Double (Only integer positive number) 1, 2, 3, etc.||
|Visitor Profile - Total Visits to Activity|Specifies the number of visits to a particular activity. If there is no previous visit, returns 0 (zero).|Double (Only integer positive number) 1, 2, 3, etc.||
|Visitor Profile - Total Visits to Activity with Conversion|Specifies the number of visits/sessions to a particular activity when there was at least one conversion during the visit.|Double||
|Visitor Profile - Visits to Activity with No Conversion|Number of visits/sessions with no conversions to a particular activity. This value is reset to zero after conversion, or -1 if conversion never happened.|Double (Only integer positive number) 1, 2, 3, etc.||
