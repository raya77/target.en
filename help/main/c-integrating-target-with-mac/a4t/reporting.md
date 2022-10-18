---
keywords: analytics for target;a4t;analytics as the reporting source;analytics
description: Learn how to use Analytics for [!DNL Target] (A4T). A4T provides access to Analytics reports for [!DNL Target] activities that use Analytics metrics and audience segments.
title: How Do I Use Reporting in A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
---
# A4T reporting

Using [!DNL Adobe Analytics] as your reporting source for [!DNL Adobe Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

 You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Overview {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] also calls [!DNL Analytics] whenever the conversion is made. [!DNL Analytics] adds the conversion as a specific new [!DNL Analytics] event named "Activity Conversion," which is tracked along with other data collected by [!DNL Analytics].

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. The data collected in that first 24 hours is still accurate and is assigned to the right experience.

## Reports in Analytics {#analytics}

In [!DNL Analytics], there are several dimensions and metrics made available after the A4T integration is enabled.

### Dimensions

* [!UICONTROL Analytics for Target] - The parent ID that is passed in through the integration. The format of this dimension is `Activity ID:Experience ID:3rd ID`. The dimensions below are classifications of this dimension.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - can be ignored

### Metrics

* [!UICONTROL Activity Impressions] - Matches the [!UICONTROL Entrants] number in the [!DNL Target] report.
* [!UICONTROL Activity Conversions] - Matches the [!UICONTROL Custom Conversions] number in the [!DNL Target] report.

In [!DNL Analysis Workspace], use the [!UICONTROL Analytics for Target] panel to analyze your [!DNL Target] activities and experiences with lift & confidence. For more information, see [Analytics for Target (A4T) Panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) in the *Analytics Tools Guide*.

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists "unspecified" instead of listing your activities, an update is required to your provisioned account. Please contact Customer Care to resolve this issue.

For detailed information and examples, open the [Analytics & Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Reports in [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite. 
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

  Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

  Any numbers that increase are shown as positives in the report, even when an increase is undesired. For example, even though you want a lower bounce rate, the higher bounce rate is shown as the winner with highest lift. Be aware of these and similar metrics, and whether you'd prefer to decrease or increase the numbers, when making decisions based on your reports.

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. You don't have to know exactly what you want to measure beforehand.

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Activity creation {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

During activity creation, you must specify a goal for the activity on the [!UICONTROL Settings] page. This goal becomes the default metric for the report and is always listed as the first option in the metrics selector. You cannot select segments for reporting like you would for a regular Target activity. A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing Offline Calculations for Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

You can perform offline calculations for confidence and confidence intervals for A4T using the [!DNL Target] [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) Excel file, but it requires a step with data exports in [!DNL Analytics].

For A4T, we use a [Welch's t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} calculation for continuous variables (rather than binary metrics). In Analytics, a visitor is always tracked, and every action taken is counted. Therefore, if the visitor purchases multiple times or visit a success metric multiple times, those additional hits are counted. This makes the metric a continuous variable. To perform the Welch's t-test calculation, the "sum of squares" is required to calculate the variance, which is used in the denominator of the t-statistic. [Statistical calculations in A/Bn tests](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explains the details of the mathematical formulas used. The sum of squares can be retrieved from [!DNL Analytics]. To get the sum of squares data, you need to perform a visitor-level export for the metric you are optimizing to, for a sample time period.

For example, if you're optimizing to page views per visitor, you'd export a sample of the total number of page views on a per visitor basis for a specified time frame, perhaps a couple of days (a few thousand data points is all you need). You would then square each value and sum the totals (the order of operations is critical here). This "sum of squares" value is then used in the Complete Confidence Calculator. Use the "revenue" section of that spreadsheet for these values.

**To use the [!DNL Analytics] data export feature to do this:**

1. Log in to [!DNL Adobe Analytics]. 
1. Click **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**. 
1. On the **[!UICONTROL Data Warehouse Request]** tab, fill in the fields.

   For more information about each field, see "Data Warehouse Descriptions" in [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Field | Instructions |
   |--- |--- |
   |Request Name|Specify a name for your request.|
   |Reporting Date|Specify a time period and granularity.<br>As best practice, choose no more than an hour or one day of data for your first request.  Data Warehouse files take longer to process the longer the time period requested, so it is always a best practice to request a small time period data first to make sure your file returns the expected result. Then, go to the Request Manager, duplicate your request, and ask for more data the second time. Also, if you toggle granularity to anything other than "None," the file size will increase drastically.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png)|
   |Available Segments|Apply a segment, as needed.|
   |Breakdowns|Select the desired dimensions:  Standard is out-of-the-box (OOTB), while Custom includes eVars & props. It is recommended you use "Visitor ID" if visitor ID level information is needed, rather than "Experience Cloud Visitor ID."<ul><li>Visitor ID is the final ID used by Analytics. It will either be AID (if the customer is legacy) or MID (if the customer is new or cleared cookies since the MC visitor ID service was launched).</li><li>Experience Cloud Visitor ID will only be set for customers who are new or cleared cookies since the MC visitor ID service was launched.</li></ul>|
   |Metrics|Select your desired metrics. Standard is OOTB, while Custom includes custom events.|
   |Report Preview|Review your settings before scheduling the report.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png)|
   |Schedule Delivery|Enter an email address to deliver the file to, name the file, then select [!UICONTROL Send Immediately].<br>Note: The file can be delivered via FTP under [!UICONTROL Advanced Delivery Options]<br>![Schedule Delivery](/help/main/c-reports/assets/datawarehouse3.png).|

1. Click **[!UICONTROL Request this Report]**.

   File delivery can take up to 72 hours, depending on the amount of data requested. You can check on the progress of your request at any time by clicking [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   If you would like to re-request data that you've requested in the past, you can duplicate an old request from the [!UICONTROL Request Manager] as needed.

For more information about [!DNL Data Warehouse], see the following links in the [!DNL Analytics] Help documentation:

* [Create a Data Warehouse request](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html) 
* [Data Warehouse best practices](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
