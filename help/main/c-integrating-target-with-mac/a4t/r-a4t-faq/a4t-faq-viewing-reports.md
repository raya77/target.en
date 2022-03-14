---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: Find answers to questions that are frequently asked about viewing reports when using Analytics for [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] activities.
title: Find Answers to Questions About Viewing Reports with A4T?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
---
# View reports - A4T FAQ

This topic contains answers to questions that are frequently asked about viewing reports when using [!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T).

## Can I view my [!DNL Target] activity data in Analysis Workspace? {#workspace}

You can use [!DNL Analysis Workspace] to analyze your [!DNL Target] activities and experiences. The [Analytics for Target panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) lets you see lift & confidence for as many as three success metrics. You can also dig deeper using tables and visualizations.

For detailed information and examples, open the [Analytics & Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## Where can segments be applied in Analysis Workspace? {#segmentation}

Segments are most commonly used at the top of a panel in the segment drop zone. The segment is applied to all tables and visualizations in the panel. This technique is most useful for seeing how the test affects a subset of people (for example, how did this test perform for people in the UK)?

A segment can also be layered directly within the freeform table, but note that you must overlay it across the entire table to preserve the lift & confidence calculations within the A4T Panel. Column level segments are not currently supported within the panel.

## When I apply a hit segment for a specific [!DNL Target] activity, why are unrelated experiences returned? {#activity-segmentation}

The [!DNL Target] variable sent to [!DNL Analytics] has a default 90-day expiration period. (Note: this expiration period can be adjusted by Customer Care if needed). As visitors navigate the site throughout this expiration window, they are part of many [!DNL Target] activities, all of which collect in the dimension. 

When you segment for an activity to be present in a hit, you get all the experiences that are part of that activity *plus* any other experiences that are persisting on that hit. 

## While configuring my Goal Metrics, why can't I access Advanced Settings?

For activities using [!DNL Analytics] as the reporting source (A4T), the goal metric uses the "[!UICONTROL Increment Count & Keep User in Activity]" and "[!UICONTROL On Every Impression]" settings. These settings are *not* configurable. 

For more information, see "While configuring my goal metrics, why can't I access the Advanced Settings options?" in [Metric definitions - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Should I use visitors, visits, or activity impressions as my normalizing metric (i.e. counting methodology)? {#metrics}

There are several options for normalizing metrics in A4T reporting. This metric, also referred to as the counting methodology, becomes the denominator of the lift calculation. It also affects how the data is aggregated before the confidence calculation is applied.

* ***Unique visitors*** increment once when a user first qualifies for an activity. 
* ***Visits*** increment for each session once a user (Unique Visitor) enters an activity, even if the activity is not viewed in subsequent visits. 
* ***Activity impressions*** increment each time activity content is served. (Measured by [!DNL Target]). 

When a visitor views a page that contains an activity, a variable is set for that visitor that contains the name of that activity. See the detailed scenarios below for how each counting methodology compares.

Consider the following:

* The above metrics trigger when a user qualifies for an activity and content is returned from [!DNL Target]. This does not necessarily mean that the user saw the offer. If an activity experience is below the fold and the user does not scroll down the page, then the offer was served by [!DNL Target] but not seen by the user. 
* [!UICONTROL Activity Impressions] (measured by [!DNL Target]) and [!UICONTROL Instances] (measured by [!DNL Analytics]) are equal, unless there are multiple mbox calls on the same page in the same activity. This causes multiple [!UICONTROL Activity Impressions] to be counted, but only a single [!UICONTROL Instance].

For more information, see [How to set up A4T reports in Analysis Workspace for Auto-Target activities](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.

## Why are "activity impressions" and "activity conversions" higher in Analysis Workspace than Reports & Analytics? {#sametouch}

[!DNL Reports & Analytics] applies a same-touch attribution model to "activity impressions" and "activity conversions," whereas [!DNL Analysis Workspace] displays the raw metrics, which can appear inflated due to persistence of the [!DNL Target] dimension.

To evaluate accurate [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. Models can be applied by clicking the column settings gear, enabling [!UICONTROL Non-default attribution models], then selecting [!UICONTROL Same Touch]. Learn more about attribution in [Attributes IQ overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) in the *Analytics Tools Guide*.

## What does "activity conversions" mean if the marketer picks an Analytics metric during activity setup? {#section_F3EBACF85AF846E9B366A549AAB64356}

"Activity conversions" are empty if an [!DNL Analytics] metric was selected as the conversion metric for the activity.

## Why do I see "unspecified" in the Analytics reports? What does it mean? {#unspecified}

In other reports, "unspecified" means data did not meet a classification rule, but in A4T this should never happen. If you see "unspecified," then the classification service hasn't run yet. It generally takes between 24 to 72 hours for activity data to appear in the reports. Even though the activities do not appear in this report until that time, all visitor data tied to those activities is captured and appear when the classification is complete.

After the classification period, data appears in these reports approximately an hour after it is collected from the website. All metrics, segments, and values in the reports come from the report suite you selected when you set up the activity.

In case classification was done for that activity, and you still see an "Unspecified" row in the report, make sure that the report isn't using a non-[!DNL Target] metric to display the data. Unless the report is using a [!DNL Target]-specific metric, that "Unspecified" row contains events for calls that are not associated with [!DNL Target]. That row will not contain any [!DNL Target]-associated information (for example, visitors/visits/impressions).

## Why are [!DNL Target] metrics sent to Analytics even after the activity has been deactivated? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

The [!DNL Target] variable sent to [!DNL Analytics] has a default 90-day expiration period. This expiration period can be adjusted by Customer Care if needed. This setting is global for all activities, however, so it should not be adjusted for one case.

You might see [!DNL Target] variables sent to [!DNL Analytics] after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled [!DNL Target] activity. If a user comes back to the site on day 45 and sees another activity, the entire A4T eVar value has its counter reset to 90 days. That means the first campaign from day 1 now could be persisting for up to 45 + 90 = 135 days. If the user keeps coming back, you might get to the point where you see metrics sent to [!DNL Analytics] in your reporting from much older activities. As users delete cookies and don’t return to the site, the numbers in that activity drop, but you can still see them.

This means that activities continue to get page views, visits, and so forth, for up to 90 days after the activity ends for visitors that became part of the activity while it was active. However, if you look at the [!UICONTROL Activity Impressions] metric, you should not see any impressions after the activity ended.

This is normal and expected behavior. The A4T variable functions like any other eVar—the value is associated with the user until it hits the expiration time period (90 days). As a result, if an activity is active for only two weeks, the value is still associated with the user for at least the next 90 days.

Best practice is view reports for that activity only for the time period the activity was live. The dates should be set correctly by default when you view the activity in [!DNL Analytics], so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

As an example, let’s assume that the A4T variable expires after 90 days and the test is active from January 1 through January 15.

On January 1, the user comes to the site and sees activity XYZ once and has five page views after that. In the next two weeks, the user never returns to the site. The data would look like this for this user:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors |
|--- |--- |--- |--- |--- |
|XYZ|1|5|1|1|

The user returns on February 1, views five more pages, and doesn’t encounter any more Target activities and the original activity is no longer active. Even though the activity is no longer active, it is still following the user via eVar persistence. The data now looks like this:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors |
|--- |--- |--- |--- |--- |
|XYZ|1|10|2|1|

The user comes back on March 1 and sees a new activity, ABC. The user also views five pages. Because activity XYZ is still following the user through persistence, and this user then has ABC set, you will see two line items in reporting:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors |
|--- |--- |--- |--- |--- |
|XYZ|1|15|3|1|
|ABC|1|5|1|1|

The user then comes back on April 1, views another five pages, and makes a purchase. The 90-day expiration of that first eVar value is reset on April 1, so you see that in reporting. And all the Target activities the user sees receives the credit for the conversion, but the total number of conversions is deduplicated:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors | Orders |
|--- |--- |--- |--- |--- |--- |
|XYZ|1|20|4|1|1|
|ABC|1|10|2|1|1|
|Total|2|20|3|1|1|

Because both experiences were seen before the conversion, they both get “credit” for the order. But, only one order took place in the system and the total reflects that. For [!DNL Target] reporting, because you aren’t putting a [!DNL Target] activity against another activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. You’re comparing the results of two items within the single activity. It's not possible for a user to see different experiences in the same activity so you don’t have to worry about cross-contamination of order credit.

For more information, see [Conversion Variables (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## Why do I continue to see more impressions after my activity has been deactivated? {#deactivated}

A source of impressions to an A4T activity's report after deactivation can be QA-mode traffic. Target normally doesn't log events for a deactivated activity, but Analytics doesn't have a way to know that impressions are coming from QA mode. When the Target activity report is retrieved from Analytics, it shows these impressions. This is working as designed because customers need a way to check A4T reports even if the activity is not active using QA mode. 

## Why do Analytics and Analytics for Adobe Target (A4T) calculate numbers for the Unique Visitors metric differently? {#section_0C3B648AB54041F9A2AA839D51791883}

When you run an A/B test, which uses the Students t-test (the confidence metric) to choose a winner of a test, one of the assumptions is that there is a fixed time horizon. The test isn’t statistically valid unless you are looking at that fixed sample size.

The [!UICONTROL Unique Visitors] metric is different in [!DNL Analytics] and [!DNL Target] only when you are looking at a period that is shorter than the actual test. If you haven’t reached your sample size, the test isn’t as reliable. See [How Not to Run an A/B Test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) on [Evan Miller's website](https://www.evanmiller.org/index.html) for more information.

The [!UICONTROL Unique Visitors] metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. Those people are part of the test and should be counted. If you want to see only the number of people who were exposed during a single week, you can create a segment of visitors who had an activity impression and apply it to the report.

You can shorten the amount of time the [!DNL Target] variable persists down to a session; however, that is problematic for tests where the conversion event isn’t as likely to happen within the same session.

## Why is the same visitor sometimes counted in multiple experiences in Analytics? {#section_1397E972D31C4207A142E4D2D6D794A2}

The following list explains reasons why the same visitor could be counted in multiple experiences in [!DNL Analytics]:

* The [!DNL Target] profile expired but the [!DNL Analytics] cookie is still there. In this situation, [!DNL Target] reevaluates the user but [!DNL Analytics] considers the visitor to be the same person. 
* If the visitor is using the `mbox3rdPartyId`, when the anonymous visitor is merged with the 3rd-party ID profile, [!DNL Target] could put the visitor into a different experience to match up with the 3rd-party ID. For more information, see [Real-Time Profile Syncing for mbox3rdPartyID](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732). 
* [!DNL Analytics] might be tracking different devices as the same visitor in a different way than [!DNL Target] tracks those devices: the 3rd-party ID setup in [!DNL Target] is different than in Analytics.

## Does A4T support virtual report suites? {#virtual}

Although virtual report suites are not included in the [!UICONTROL Report Suite] list, any A4T data shared with a report suite that is linked to a virtual report suite in [!DNL Analytics] has access to that data. Note that any audience created from a virtual report suites cannot be shared back to [!DNL Target].

## Can I change the percentage of traffic allocation in an activity that uses A4T after the activity has been activated?

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in [!DNL Analytics] because the change impacts only new visitors. Returning visitors are not impacted. 

As best practice, you should stop the existing activity and then create a new activity instead of changing the percentage after activation. Reporting for the new activity starts with new visitors and data from returning visitors do not cause inconsistent reporting.

## How are visits counted in Analytics and conversion credit allocated in an Auto-Target activity that uses A4T?

When a visitor qualifies for, views content, or converts in an A4T activity, [!DNL Target] sends event data to [!DNL Analytics]. This event data allows [!DNL Analytics] to attribute conversion events and other clickstream events happening on the page to the relevant [!DNL Target] activities and experiences.

Here a few points to keep in mind when viewing [!DNL Analytics] reports:

* In general as a best practice, your reporting window should begin from the start date of the activity.
* If a conversion happens outside the report's window, the conversion is not visible in [!DNL Analytics].
* When in the "targeted" portion of traffic for [!UICONTROL Auto-Target] activities, visitors might see different experiences from one session to the next. For example, if their profile or context has changed and [!DNL Target]'s machine-learning algorithms decide they are more likely to convert on a new experience. As visitors move from experience to experience, the visit count increments for each experience seen. This is unlike regular A/B Testing activities where experiences are sticky to a visitor across visits.
* If a visitor sees multiple experiences across visits, any conversion is always attributed to the last experience that the visitor saw. As mentioned, the visit count increments for each experience that the visitor saw. This can artificially depress the per-experience conversion rates when viewing experiences under the "[!UICONTROL Targeted]" dimension in [!DNL Adobe Analytics] reports.
