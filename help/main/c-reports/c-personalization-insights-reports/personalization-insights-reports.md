---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
description: Learn how to use the specialized reports for Automated Personalization (AP) and Auto-Target (AT) activities - Automated Segments and Important Attributes.
title: How Do I Use the Personalization Insights Reports?
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
---
# ![PREMIUM](/help/main/assets/premium.png) Personalization Insights reports

Two specialized reports are available to users of [!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] (AT) activities: the [!UICONTROL Automated Segments] and [!UICONTROL Important Attributes] reports.

>[!NOTE]
>
>Consider the following when using Personalization Insights reports:
>
>* AP and AT activities are available as part of the [!DNL Target Premium] solution. They are not included with [!DNL Target Standard] without a [!DNL Target Premium] license.
>
>* [!UICONTROL Personalization Insights] reports are available only for AP and AT activities that use a conversion optimization goal. Activities where the optimization goal was changed to conversion from revenue after the activity was already live are also not supported.
>
>* [!UICONTROL Personalization Insights] reports are available only if the [!UICONTROL Primary Goal] is selected from the the [!UICONTROL Report Metric] drop-down list.
>
>* [!UICONTROL Personalization Insights] reports are supported in the [default environment](/help/main/administrating-target/hosts.md) only.
>
>* [!UICONTROL Personalization Insights] reports are generated only for activities that are in the [!UICONTROL Live] status and have been activated and receiving traffic for at least 15 days.

## Personalization Insights Reporting overview {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

The goal of the [!UICONTROL Personalization Insights] reports is to provide more information on how the [!UICONTROL Target] personalization models behind your AP and AT activities personalize visitor traffic. The [Random Forest algorithm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) is the basis for the [!DNL Target] personalization models.

Because the goal of the [!UICONTROL Personalization Insights] reports is to understand how the [!DNL Target] personalization models decided to send which visitor to what piece(s) of content, the [!UICONTROL Personalization Insights] reports reflect only a sub-segment of all the traffic served by your AP or AT activity. Specifically, the two reports are reflective of all traffic that used the personalization model. In other words, [!UICONTROL Personalization Insights] reports do not consider control traffic or traffic that is served by the overall winner model.

Two [!UICONTROL Personalization Insights] reports are available:

| Report | Details |
|--- |--- |
|[!UICONTROL Automated Segments]|Different visitors respond differently to the offers/experiences in your AP/AT activity. This report shows how different automated segments defined by the [!DNL Target] personalization models responded to the offers/experiences in the activity.|
|[!UICONTROL Important Attributes]|In different activities, different attributes are more, or less, important to how the model decides to personalize. This report shows the top attributes that influenced the model and their relative importance.|

## Interpreting attributes in Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

There are two types of attributes represented in [!UICONTROL Personalization Insights] reports that are used in your AP or Auto Target models:

* **Attributes automatically collected by Target:** [!DNL Target] uses a base data set to build its personalization algorithms in AP and AT activities that are reflected in Personalization Insights. See [Data Collection for Target's Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md) for data types, example attributes, and their [!UICONTROL Personalization Insights] naming convention. Note that although these attributes are considered, an individual activity’s models might not use all of these attributes in the final model. 
* **Attributes passed to Target:** See [Uploading Data for the Target Personalization Algorithms](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] provides many ways for you to pass in additional data to [!DNL Target] to enrich the base data set used to build its personalization algorithms in AP and AT activities:

| Data Type | Description | Data Type Naming Convention |
|--- |--- |--- |
|Profile Attributes, including profile scripts, Profile Update API, and in-page profile attributes|Any information you've decided to include in Target's user profile.<br>This information could come from profile scripts, information uploaded using the Profile Update API, or in-mbox profile parameters prefixed with "profile."|`Custom - Profile - [parameter name]`|
|Page Parameters (also called “mbox parameters”)|Name/value pairs passed in directly through page code that are not stored in the visitor's profile for future use.|`Custom - Mbox Parameter - [parameter name]`|
|Customer Attributes|Customer attributes let you upload visitor profile data via FTP to the Experience Cloud. Once uploaded, leverage the data in Adobe Analytics and Adobe Target.|`Custom - Customer Attributes - [parameter name]`|
|Shared Audiences (Adobe Audience Manager or Adobe Analytics)|Audiences created through Adobe Audience Manager or Adobe Analytics and shared with Target.|`Custom - Experience Cloud Segment - [segment name]`|
|Shared Audiences (Adobe Experience Platform/Real-time CDP)|Audiences created through Adobe Experience Platform/Real-time CDP and shared with Target via Destinations.|`Custom - Adobe Experience Platform Segment - [segment name]`|
|Shared Attributes (Adobe Experience Platform/Real-time CDP)|Attributes created through Adobe Experience Platform/Real-time CDP and shared with Target via Destinations. This feature is currently in Beta.|`Custom - Adobe Experience Platform Attribute - [attribute name]]`|
|In-Activity Reporting Audiences/ Segments|Audiences defined in your AP or Auto Target activity during setup in “Goals & Metrics.”|`Custom - Reporting Segment - [segment name]`|

## Frequently Asked Questions

List of frequently asked questions about [!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] [!UICONTROL Insights] reports.

### How long does data for [!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] models persist?

[!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] models are trained on the last 45 days of user behavior (user profiles, impression events, and conversion events) for the activity. 

[!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] models retain user behavior, training records, and model decision data for 90 days to produce [!UICONTROL Insights] reports. After 90 days, training records and model decisions are discarded. [!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] models also retain aggregated experience/offer-level impression and conversion data for reporting purposes for two years. This data is aggregate-level data only and does not contain any individual-level profile data.

## Training video: Using the Personalization Insights reports ![Tutorial badge](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

For more information, see [Using the Personalization Insights Reports in Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe Blogs

* Part 1: [Taking the Mystery Out of the Magic of AI-Driven Personalization](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Part 2: [A Peek Behind the Curtain of AI for Personalization in Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Part 3: [MAGIX — the Solution to the Black Box Issue of AI-Driven Personalization](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
