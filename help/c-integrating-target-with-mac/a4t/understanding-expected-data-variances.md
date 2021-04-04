---
keywords: data variances;analytics;differences;variance;a4t;analytics for target;analytics as the reporting source;discrepancies;discrepancy
description: Learn about the expected data variances between Adobe Target and Analytics when not using Analytics for Target (A4T), which eliminates data variance altogether.
title: What Is the Expected Data Variance between Analytics and A4T?
feature: Analytics for Target (A4T)
exl-id: 9e63f309-8ec1-4ed5-a1f9-6c3098a7b8f6
---
# Expected data variances between Adobe Target and Adobe Analytics when using and not using A4T

Information about expected data variances between [!DNL Target] and Adobe [!DNL Analytics] when *using* and *not* using Analytics as the Reporting Source (A4T). A4T significantly reduces data variance.

## Expected data variance when using A4T {#expected-using-a4t}

With A4T, both Analytics and Target reporting of activities use Analytics data exclusively, so there is little variance between the solutions in Target activity reports. In some circumstances, however, customers compare Target data to Analytics data outside the scope of the A4T integration and, thus, experience the variance issues described below.

Here are a few scenarios in which you can experience expected data variance: 

* A4T allows for the possibility that a Target hit (top of page) occurs, but no Analytics hit (bottom of page) occurs. For example, suppose a visitor loads the page, but closes the browser before the Analytics call triggered. In these cases, A4T excludes the Target hit from the data. Allowing Target hits (again, top of page) to count as Analytics hits in the absence of an actual Analytics call creates inconsistencies with the data set in Analytics (visitor inflation, and so forth).

  If a redirect test is set up in Target to split traffic 50/50 (or 25/25/25/25, and so forth), user behavior might not be divided evenly. If you see an uneven split, it simply means that one group of users failed to execute an Analytics call on the landing page more than the other groups did. This failure to execute the Analytics call for one group caused the Target hit for that user to be excluded, creating the unevenness.

  Adobe hopes to address this issue in the future as Adobe teams work toward A4T on the Adobe Experience Platform. Adobe teams are determining how to handle these different events occurring at different times on the page.

  >[!NOTE]
  >
  >A known issue exits that is causing a limited number of customers using redirects with A4T to see a higher percentage of unstitched hit rates. See [Known issues and resolved issues](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Expected data variance when *not using* A4T {#expected-not-using-a4t}

Variances of 15-20% are normal, even with similar data sets. Systems that count differently can result in much higher data variances, as much as 35-50%. Sometimes, variances can be even higher.

Although actual data can vary significantly, trends are usually consistent. As long as the differences and trends remain consistent, the data remains valuable and useful. If the differences and trends are inconsistent, it could mean that something is set up incorrectly. In this case, contact your account representative for assistance.

[!DNL Analytics] uses a system based on visits and transactions, but [!DNL Target] uses visitor-based metrics. Whenever a visitor opens a page, it counts as a visit in [!DNL Analytics], but [!DNL Target] does not count the visit until the conditions set in the activity are met.

Reports in [!DNL Target] show performance based on the conversion mbox selected when defining the activity. However, this conversion mbox data is not sent to [!DNL Analytics], which has its own conversion variables as defined by your [!DNL Analytics] tagging implementation. Where you expect identical data (for example, if a retailer's order confirm that page contains both a conversion mbox and an [!DNL Analytics] purchase event), data can differ due to the placement of these tags. In general, trends in the two products' reports are similar.

Expected data variances can be caused by both technical and business variances.

### Examples of Technical Variances {#section_C3B50ED2E2F9416FAC91437CF1A87369}

The following can cause data variances based on technical differences:

* [!DNL Target] visitors must allow cookies and JavaScript 
* 1st- and 3rd-party cookies are processed differently; as a result, data from these cookie types do not match 
* Relative location of tags on pages and "leakage" caused by visitors who exit the page before it fully loads 
* Time zone considerations 
* Differences in which devices can be counted

### Examples of Business Variances {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

The following can cause data variances based on business differences:

* Differences between visitor and visit metrics 
* Targeting on activities excludes some visitors 
* A single mbox on multiple pages, counting visitors on each of those pages 
* Activity priorities can include some visitors and exclude others on a page 
* Visitors who have converted once can be counted again when they reenter the activity 
* [!DNL Analytics] counts all conversions for all visits and visitors, but [!DNL Target] counts conversions only for those visits and visitors that are included in the activity
