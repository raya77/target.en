---
keywords: qa;qa mode; activity qa;qa url;qa urls;preview url;preview urls
description: Learn how to use Adobe [!DNL Target] QA URLs to perform easy end-to-end activity QA with preview links that never change, optional audience targeting, and QA reporting that stays segmented from live activity data.
title: How Do I QA Activities?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
---
# Activity QA 

Use QA URLs in [!DNL Adobe Target] to perform easy end-to-end activity QA with preview links that never change, optional audience targeting, and QA reporting that stays segmented from live activity data.

[!UICONTROL Activity QA] lets you fully test your [!DNL Target] activities before launching them live. The [!UICONTROL Activity QA] functionality includes:

* Links to share with team members that never change or require regeneration, regardless of updates made to the experiences or activities. This feature lets you fully test your activities across the entire user journey.
* Audience conditions optionally respected so marketers can test targeting criteria or ignore targeting criteria to QA the appearance of experiences without having to meet the audience conditions. 
* QA reporting is captured so that marketers can confirm that metrics are incrementing as expected and the QA report data is kept separate from production reporting (for non-A4T reporting). 
* The ability to preview an experience in isolation or with other live activities satisfying the delivery criteria (page/Target request/audience). 
* The ability to QA the entire user journey. You can access your site once with the QA link and then browse the entire site while in Activity QA. You remain in Activity QA until you end the session or until you use the [QA Target bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) to force yourself out of [!UICONTROL Activity QA]. This feature is useful if you have an activity spanning multiple web pages.

  >[!NOTE]
  >
  >This functionality is true for at.js implementations with version 2.*x* or later. For at.js 1.*x* implementations, this functionality is true only if the visitor's browser doesn't block third-party cookies.

## Accessing and Sharing a QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. From an activity's [!UICONTROL Overview] page, click the **[!UICONTROL Activity QA]** link.

   ![Activity QA link](assets/qa_link.png)

1. Configure the following settings:

   ![QA Link configuration options](assets/qa_link_config.png)

    * **[!UICONTROL Match audience rules to see experiences]:** Sometimes you want to confirm that your audience matching works. Other times you want to check the look and feel of the activity. If this setting is toggled to the "on" position, testers must meet targeting requirements to qualify to see the experiences. For Experience Targeting (XT) activities, a single activity URL is provided. The experience you see is determined by you qualifying for one of the targeting rules.

      If this setting is toggled to the "off" position, clicking the links show you the experiences regardless of whether you qualify or not. When performing QA, you can switch back and forth between requiring or not requiring that audience targeting is respected. 
    
    * **Show default content for all other activities:** If this option is toggled to the "on" position, default content is shown for all other activities. For example, the preview is shown in isolation without considering all other live activities on the same page/[!DNL Target] request.

      If this setting is toggled to "off," consider the following:

        * If there are collisions between the activity you are testing and other live activities, [normal priority rules](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) apply. Because of collisions, it is possible you cannot see the activity that you are intending to QA. 
        * Metrics increment for the viewed activities, but only in the QA reporting environment.

1. Click **[!UICONTROL Done]** to save your changes. 
1. Share the activity link URLs with members of your organization for testing.

   Activity links never expire and you do not need to resend links if someone changes an activity or experience. However, if you apply a different audience from the [!UICONTROL Audience Library], rather than simply editing the activity, a new link is generated that you must reshare.

   Each Activity link URL (for Experience A, Experience B, and so forth) lets you start the user journey from the corresponding experience. Click the URL generated for an experience and then proceed with normal site browsing to see experiences on multiple pages (if multiple pages exist). Only one URL is generated per experience, even if the experience spans multiple pages (template testing or multi-page testing). 
   
   You can navigate the site to see the other pages because the [!UICONTROL Activity QA] mode is sticky. This situation is true for at.js implementations with version 2.*x* or later. For at.js 1.*x* implementations, this situation is true only if the visitor's browser doesn't block third-party cookies.

1. To see reports generated from activity link URLs, click the activity's **[!UICONTROL Reports]** page, click the **[!UICONTROL Settings]** icon (  ![](assets/icon_gear.png) ), then select **[!UICONTROL QA Mode Traffic]** from the **[!UICONTROL Environment]** drop-down list.

## Considerations {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* The [!UICONTROL Activity QA] link displays on the [!UICONTROL Overview] page of all activity types except for [!UICONTROL Auto-Target] and [!UICONTROL Automated Personalization] (AP).
* [!UICONTROL Activity QA] preview links for saved activities might not load if there are too many saved activities in your account. Retrying the preview links should work. To prevent this situation from continuing to happen, archive saved activities that are no longer actively used.
* [!UICONTROL Activity QA] URLs are available with activities with Analytics as the reporting source (A4T). Hits generated while performing QA using [!UICONTROL Activity QA] flow to the same report suite where the activity's data flows even after the activity goes live. 
* [!UICONTROL Activity QA] does not display content for archived activities or activities that are past their end dates. If you deactivate an ended activity, you must save the activity again for [!UICONTROL Activity QA] to work. 
* Activities imported into [!DNL Target Standard/Premium] (from [!DNL Target Classic], for example) do not support QA URLs. 
* In [!UICONTROL Auto-Allocate] and [!UICONTROL Recommendations] activities, the model is not affected by the visits captured in [!UICONTROL Activity QA]. 
* [!UICONTROL Activity QA] is sticky. After you browse a website in [!UICONTROL Activity QA], your [!DNL Target] session must expire or you must have [!DNL Target] release you from [!UICONTROL Activity QA] before you can view your site like a typical visitor. Use the [Target QA bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) to force yourself out of [!UICONTROL Activity QA].

  You can also manually force yourself out by loading a page on your site with the `at_preview_token` parameter with an empty value (for example, `https://www.mysite.com/?at_preview_token=`). 

* If you specified "URL is" while creating the activity [refinements in the Form-based Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) or [page delivery options in the Visual Experience Composer)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), the QA URL does not work because [!UICONTROL Activity QA] appends URL parameters. To solve this issue, click the QA URL to go to your site, remove the appended parameters from the URL, then load the new URL.
* If you have at.js 1.*x*, [!UICONTROL Activity QA] mode is not sticky if you use Safari or another browser that blocks 3rd-party cookies. In these cases, you must add the preview parameters to each URL you navigate to. The same is true if you have implemented [CNAME](/help/main/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md).
* If an activity uses multiple experience audiences (for example, a US and UK site that are included in the same activity), QA links are not generated for the four combinations (Experience A/US Site, Experience A/UK Site, Experience B/US Site, Experience B/UK Site). Only two QA links (Experience A and Experience B) are created and users must qualify for the appropriate audience to see the page. A UK QA person cannot see the US site. 
* All `at_preview` parameters and values are already URL encoded. Most of the time, everything works as expected. However, some customers must load balancers or Web servers that try to encode the query string parameters again.

  Because of this double encoding, when [!DNL Target] tries to decode the `at_preview_token`, [!DNL Target] can't extract the correct token value, resulting in preview not working.

  Adobe recommends that you talk to your IT team to ensure that all preview parameters are allowlisted so that these values are not transformed in any way.

  The following table lists the parameters that can be allowlisted in your domain:

  | Parameter | Type | Value | Description |
  |--- |--- |--- |--- |
  |`at_preview_token`|Encrypted string|Mandatory; no default value|An encrypted entity that contains the list of campaigns IDs that are can be executed in QA mode.|
  |`at_preview_index`|String|Empty|Format of the parameter is `<campaignIndex>` or `<campaignIndex>_< experienceIndex>`<br>Both indexes start with 1.|
  |`at_preview_listed_activities_only`|Boolean (true/false)|Default value: false|If "true," all campaigns specified in the `at_preview_index` parameters are processed.<br>If "false," all the campaigns from the page are processed, even if they were not specified in the preview token.|
  |`at_preview_evaluate_as_true_audience_ids`|String|Empty|Underscore-separated ("_") list of segmentId-s that should always (at targeting and reporting level) be evaluated as "true" in the scope of the [!DNL Target] request.|
  |`_AT_Debug`|String|Window or console|Console logging or new window.|
  |`adobe_mc_ref`|||Passes the referring URL of the default page to the new page. When used with `AppMeasurement.js` version 2.1 (or later), [!DNL Adobe Analytics] uses this parameter value as the referring URL on the new page.|
  |`adobe_mc_sdid`|||Passes the [!DNL Supplemental Data Id] (SDID) and [!DNL Experience Cloud Org Id] from the default page to the new page. Passing these IDs allow [!UICONTROL Analytics for Target] (A4T) to "stitch" together the [!DNL Target] request on the default page with the [!DNL Analytics] request on the new page.|

* The [!UICONTROL Target QA Mode] UI shows only the first URL of an experience in a multi-page activity. The assumption is that you are creating a journey test and you move from URL1 to URL2. However, if you want to go to URL2 independently, copy all the URL parameters provided against URL1 and apply them to URL2 after placing a "?" just like you see in URL1.
* Activity QA preview links for saved activities might not load if there are too many saved activities in your account. Retry the preview links. Archive saved activities that are no longer actively used to prevent this issue from continuing to happen.

## Target JavaScript library [!UICONTROL QA Mode] compatibility {#compatibility}

[!DNL Target] supports the following JavaScript libraries:

* [at.js 1.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [at.js 2.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [Adobe Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)

The following table lists the various activity types and indicates whether [!UICONTROL Activity QA] mode is supported for each library:

|Activity type|at.js 1.x|at.js 2.x|Platform Web SDK|
| --- | --- | --- | --- |
|[!UICONTROL A/B Test]|Yes|Yes|Yes|
|[!UICONTROL Auto-Allocate]|Yes|Yes|Yes|
|[!UICONTROL Auto-Target]|No|No|No|
|[!UICONTROL Automated Personalization] (AP)|No|No|No|
|[!UICONTROL Experience Targeting] (XT)|Yes|Yes|Yes|
|[!UICONTROL Multivariate Test] (MVT)|Yes|Yes|Yes|
|[!UICONTROL Recommendations]|Yes|Yes|Yes|

## Preview URLs {#preview}

Experience preview URLs can be generated for all [!DNL Target] activity types. Preview URLs let you see experience content directly on your site before the activity is live for preview and QA purposes. Experience preview URLs bypass targeting to force viewing of a particular experience. 

For information about how preview URLs function with [!UICONTROL Automated Personalization] (AP) activities, see [Preview Automated Personalization activities with experience preview URLs](/help/main/c-activities/t-automated-personalization/experience-preview.md).

To access and share a preview URL, from an activity's **[!UICONTROL Overview]** page, click the **[!UICONTROL Activity QA]** link.

>[!NOTE]
>
>The [!UICONTROL Activity QA] link and the preview URL are the same for all activities other than [!DNL Target] AP activities.

The following table lists the various activity types and indicates whether the preview URLs feature is supported for each library or API:

|Activity type|at.js 1.x|at.js 2.x|Platform Web SDK|
| --- | --- | --- | --- |
|[!UICONTROL A/B Test]|Yes|Yes|Yes|
|[!UICONTROL Auto-Allocate]|Yes|Yes|Yes|
|[!UICONTROL Auto-Target]|Yes|Yes|Yes|
|[!UICONTROL Automated Personalization] (AP)|Yes|Yes|Yes|
|[!UICONTROL Experience Targeting] (XT)|Yes|Yes|Yes|
|[!UICONTROL Multivariate Test] (MVT)|Yes|Yes|Yes|
|[!UICONTROL Recommendations]|Yes|Yes|Yes|

