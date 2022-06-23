---
keywords: Automated Personalization;ap;upload data;offline data;personalization algorithm;auto target;auto-target;best practices
description: Learn how to upload offline data, such as CRM information, when building personalization models in Adobe [!DNL Target] Automated Personalization (AP) activities.
title: How Can I Upload Data for Personalization Algorithms?
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
---
# Upload data for the [!DNL Target] personalization algorithms

Offline data, such as CRM information or customer churn propensity scores, can be incredibly valuable when building personalization models in [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) activities.

 There are several ways to input data in [!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] personalization algorithms. In addition to the methods in [Methods to get Data into Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}, Experience Cloud shared audiences (Adobe Analytics, Audience Management){target=_blank} and in-activity reporting audiences are also used in our algorithms.

For information about the data automatically collected and used by Automated Personalization and Auto-Target personalization algorithms, see [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Best Practices {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

The following list presents best practices for uploading data for Target's personalization algorithms:

* The more high-quality data that is available to Target’s personalization algorithms, the better the quality the resulting models in your AP and Auto Target activities. 
* Limit using multiple profile scripts or attributes that serve the same purpose. 
* Don’t pass a unique Id, such as a session ID if not needed. 
* Review what data Target automatically collects ( [Data Collection for Target's Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md)) so that you don’t send duplicate information. For example, Target uses IP addresses to determine visitors' ZIP codes. It is not necessary to pass this information as a separate variable. 
* Do not pass multiple values in the same attribute/variable. If multiple variables are concatenated, Target’s personalization algorithms treat each string as a unique value, reducing the value of the information for personalization. 
* Use a memorable and meaningful naming convention to make your [Personalization Insights Reports](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) more understandable.
