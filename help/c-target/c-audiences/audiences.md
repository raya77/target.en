---
keywords: audience;audience rules;create audience;creating audience;targeting audience;reporting audience;report audience;segment;custom profile parameters;audience definition;audiences list
description: Learn how to use the [!UICONTROL Audiences] list in [!DNL Adobe Target].
title: How Do I Use the Audience List?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
---
# Create audiences

Audiences in [!DNL Adobe Target] determine who sees content and experiences in a targeted activity.

Audiences are used anywhere targeting is available. When targeting an activity, you have the following options:

* Select a reusable audience from the [!UICONTROL Audiences] list
* [Create an activity-specific audience](/help/c-target/creating-activity-only-audience.md) and target it
* [Combine multiple audiences](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) to create an ad hoc audience

You can also use audience data collected by [!DNL Adobe Analytics] for real-time targeting and personalization in [!DNL Target] and other [!DNL Adobe Experience Cloud] applications. See [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) in the *Experience Cloud Central Interface Components* guide.

There are two types of audiences in [!DNL Target]:

* **Targeting audiences:** Used to deliver different content to different types of visitors. 
* **Reporting audiences:** Used to determine how different types of visitors respond to the same content so you can analyze your test results.

  In [!DNL Target], you can configure reporting audiences only if you use [!DNL Target] as your reporting source. If you use [Adobe Analytics as your reporting source](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), you must configure your reporting audiences within [!DNL Analytics].

## Use the [!UICONTROL Audiences] list

To access the [!UICONTROL Audiences] list, click **[!UICONTROL Audiences]** in the top menu bar:

![[!UICONTROL Audiences] list](assets/audiences_list.png)

The [!UICONTROL Audiences] list contains the audiences that you can use in your activities. Use the [!UICONTROL Audiences] list to create, edit, duplicate, copy, or combine audiences. The list also shows the source where the audience was created:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >The [!DNL Adobe Experience Platform] source is in a Beta testing program, but is available to all [!DNL Target] customers using the [!DNL [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)]. Audiences available from the [!DNL Adobe Experience Platform] can be used as is or [combined with existing audiences](/help/c-target/combining-multiple-audiences.md).

Predefined audiences, such as "[!UICONTROL New Visitors]" and "[!UICONTROL Returning Visitors]," cannot be renamed.

When working with audiences that were originally created in [!DNL Experience Cloud] or [!DNL Adobe Experience Platform], [!DNL Target] alerts you if you reference an audience in [!DNL Target] activities that have later been deleted in [!DNL Experience Cloud] or [!DNL Adobe Experience Platform].

* If an audience was deleted in [!DNL Experience Cloud] or [!DNL Adobe Experience Platform], a warning icon in both the [!UICONTROL Audience] list and the audience picker displays. A tool-tip in the [!DNL Target] UI also indicates that the audience was deleted in [!DNL Experience Cloud] or [!DNL Adobe Experience Platform]. 
* If you attempt to combine multiple audiences with a deleted audience, or if you attempt to save an activity that references a deleted audience, a warning message displays.

You can also target custom profile parameters and `user.` parameters. When creating an audience, drag the attributes you want to use to target your activity into the audience builder window. If the desired attribute does not display, the attribute has not been fired by an mbox. Other custom mbox parameters are available in the [!UICONTROL Custom Parameters] drop-down list.

Use the [!UICONTROL Filters] button to filter the [!UICONTROL Audiences] list by source: [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud], and [!DNL Adobe Experience Platform].

![Filters option in the [!UICONTROL Audiences] list](assets/filters.png)

Use the [!UICONTROL Search audiences] box to search your [!UICONTROL Audiences] list. You can search for any part of an audience name, or you can enclose a specific string in quotes.

You can sort the [!UICONTROL Audiences] list by audience name or by the date when it was last modified. To sort by name or date, click the column header, then select to display audiences in ascending or descending order.

## View audience definitions {#section_11B9C4A777E14D36BA1E925021945780}

You can view audience definition details on a pop-up card in various places in the [!DNL Target] UI without opening the audience. This functionality applies to audiences created in [!DNL Target Standard/Premium] and audiences imported from [!DNL Target Classic] or created via API.

For example, the following audience definition card is accessed by clicking the [!UICONTROL View Details] icon for the desired audience:

![Activities > Audience definition](assets/audience_definition_list.png)

The following audience definition card is accessed by clicking the [!UICONTROL View Details] icon on an activity's [!UICONTROL Overview] page:

![Activities > Audience definition](assets/view-details-activity-overview.png)

The audience definition card shows they audience's type, source, and attributes. Click **[!UICONTROL View full details]** to see other activities that reference that audience, if applicable. If you are viewing an audience definition card from an activity's [!UICONTROL Overview] page, click **[!UICONTROL Audience Usage]**.

The audience usage information can help you avoid accidental impact to other activities while editing audiences. Information includes [!UICONTROL Live Activities], [!UICONTROL Inactive Activities], [!UICONTROL Archived Activities], and [!UICONTROL Syncing Activities]. This feature is available for all audiences (Library audiences and [activity-only audiences](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

If an audience is [combined with another audience](/help/c-target/combining-multiple-audiences.md) and the combined audience is used to create an activity, the usage information for both audiences lists that newly created activity.

![](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## Training video: Using Audiences ![Tutorial badge](/help/assets/tutorial.png)

This video includes information about using audiences.

* Explain the term "audience" 
* Explain the two ways audiences are used for optimization 
* Find audiences in the Audiences List 
* Target an activity to an audience 
* Use audiences for passive reporting in an activity

>[!VIDEO](https://video.tv.adobe.com/v/17398)
