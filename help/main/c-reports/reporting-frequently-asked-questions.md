---
keywords: troubleshooting;metric discrepancies;FAQ;reports;new visitor;new visitors;returning visitor;returning visitors;return visit;new visit
description: Explore a list of frequently asked questions and answers about Adobe [!DNL Target] reporting.
title: Where Can I Find Answers to Questions About [!DNL Target] Reporting?
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
---
# Reporting FAQ

List of frequently asked questions about reporting in [!DNL Adobe Target].

## How are the New Visitors and Returning Visitors metrics counted? {#methodology}

A New Visitor's first visit lasts as long as the visitor is active on the site.
If the user is inactive for 30 minutes or longer, the session is reset. Resetting the session means that this visitor becomes a Return Visitor upon the next visit or becoming active again after 30 minutes of inactivity. 
If the visitor moves around the site every 29 minutes for an entire day, this visitor is counted as a New Visitor that entire day. The session was never reset because the visitor never went over the 30-minute threshold.  

The following information explains in more detail how New Visitors and Returning Visitors are counted. Examples are also included explaining why the sum of these two segments doesn't always add up to the number of total visitors.

### New Visitors

A visitor is included in the New Visitors segment if one of the following conditions is met:

* It is the visitor’s first time visiting the site.
* It is the visitor's first time visiting the site since clearing cookies.
* It is the visitor’s first time visiting the site since the [Visitor profile lifetime](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) has expired.

### Returning Visitors 

The visitor is included in the Returning Visitors segment if the user previously visited the site, left for at least 30 minutes, and returned to the site again with the same cookies. As long as a visitor returns within their profile lifetime, this visitor a returning visitor.

Suppose that your profile lifetime is set for 14 days (the default). A visitor is included in the Returning Visitors segment if the following conditions are met:

* A visitor visits the site for the first time and is recorded as a New Visitor.
* The visitor leaves the site, but returns six days later.

Because the profile lifetime is set for 14 days, this visitor is included in the Returning Visitors segment. If the visitor has deleted cookies within that six-day period, that visitor is included in the New Visitors segment.

### Examples that explain discrepancies between metric counts 

**Example 1**: If these two segments are applied to an activity, the New Visitors segment and the Returning Visitors segment do not always add up to the total number of visitors.

Consider the following example, taking in the conditions mentioned above for New Visitors and Returning Visitors:

* A visitor visits the site for the first time and is counted as a New Visitor.
* The visitor returns to the site after the conditions are met for Returning Visitors and is counted as a Returning Visitor.

This visitor is counted as a single visitor in the activity’s overall visitor count even though being counted in both the New Visitors and Returning Visitors segments.

**Example 2**: Discrepancies between the counts for New Visitors and Returning Visitors also depend on how you configure the activity's [success metrics](/help/main/c-activities/r-success-metrics/success-metrics.md).

For example:

Several new visitors visit your site and are qualified for an activity. These new visitors are counted towards the New Visitors segment. All of these visitors also recorded a visit into that activity.

Some visitors hit the conversion metric, which was configured as "Increment Count & Keep User in Activity." Suppose some of these users hit the conversion metric multiple times, the conversion metric does not increase. Given that setup, however, some users might hit the conversion metric and then navigate back to the home page, qualifying into the activity again to record a new visit.

## Why do my [!UICONTROL Experience Targeting] (XT) reports contain metrics for control experiences?

XT activities should always have a control experience. If you are using an XT activity in a similar manner to an [!UICONTROL A/B Test] activity, which is a fairly common scenario, the control experience data is useful. You can ignore the control experience data if you find it not useful in your reports.

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

Metric numbers, for example visits, reported by [!DNL Target] are always lower than the reported numbers in other [!DNL Experience Cloud] solutions for several reasons:

* [!DNL Target] counts visits only for visitors that qualified for the activity. Other solutions count visits for visitors that display the page, regardless of which activity brought them to the page. 
* There might be situations where different activities compete for the same location (mutually exclusive). As a result, visitors see different content on a web page, which affects the metric numbers reported by [!DNL Target].

## Why is there no data available for my activity's report? {#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/main/administrating-target/hosts.md)) selected in the report's settings.

If you have a development environment selected, you might see the following error message: "There is no data available for the selected report settings."

To change the environment for an activity's report:

1. Click **[!UICONTROL Activities]**, click the desired activity from the list, then click the **[!UICONTROL Reports]** tab. 
1. Click the gear icon to configure report settings.

   ![A/B Settings dialog box](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. From the **[!UICONTROL Environment]** drop-down list, select **[!UICONTROL Production]**.

   Report data might not be available if you have a development environment selected. 

1. Click **[!UICONTROL Save]**.

For more information about environments, see [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## Why is the traffic split between my experiences uneven in my A/B or MVT activity? {#uneven}

For example, I set the traffic split to be 50/50 or 25/25/25/25 but I'm seeing a vastly different distribution between experiences in the reporting. There are several explainable reasons for uneven visitor counts in [!DNL Target] reporting:

* When a [!DNL Target] activity is first launched, the traffic distribution can be uneven because of the edge node architecture that [!DNL Target] uses to optimize experience delivery. The best practice is to give an activity some time to collect more data and the distribution will normalize. For more information on [!DNL Adobe Target] architecture and Edge nodes, see [How Adobe Target works](/help/main/c-intro/how-target-works.md).
* If you are in [!DNL Target] or [!DNL Analytics] and you're using the **[!UICONTROL Visits]** metric, remember that [!DNL Target] is a visitor-based system and the traffic distribution for an A/B or MVT test is assigned at the visitor level. Thus, if you examine activity results using the **[!UICONTROL Visits]** metric, the traffic distribution might appear uneven because certain visitors might have multiple visits. Visitors is the standard normalizing metric when evaluating activity performance.
* The best practice for A/B and MVT tests is to keep traffic splits even. Changing the traffic distribution between experiences (say from 90/10 to 50/50) during a test can lead to uneven visitors across experiences. The lower traffic experience might never "catch up."
* If you are following the above best practices and the traffic split does not normalize over time, you should check the following:

  * Are you using the latest at.js library? For more information about the current version and associated release notes, see [at.js version details](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

  * Is it a redirect test? Incorrect timing of tags firing on the page can lead to uneven traffic splits, especially when using [!DNL Analytics] as the data source for a [!DNL Target] activity. For details to remedy uneven traffic distribution on a redirect activity with Analytics for Target (A4T), see [Redirect offers - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
