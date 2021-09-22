---
keywords: Click tracking;track clicks;clicks;AppMeasurement
description: Learn how [!DNL Adobe Target] lets you track clicks on any element as a success metric.
title: What is Click Tracking?
feature: Success Metrics
exl-id: 9181424b-179e-49fc-b760-b764a0c3458a
---
# Click tracking

[!DNL Adobe Target] lets you track clicks on any element as a success metric.

>[!NOTE]
>
>Tracking clicks is not supported on the global [!DNL Target] request when it is used as a location in a form-based activity.

## Set up click tracking {#section_5540C5A533114E57BAE022A600B02E72}

1. When setting your goals on the [!UICONTROL Goals & Settings] page for your activity , select the **[!UICONTROL Conversion]** success metric. 
1. For the action, select **[!UICONTROL Clicked an element]**, then click **[!UICONTROL Select elements]**.

   Your page opens in the [!UICONTROL Visual Experience Composer] (VEC). 

1. Select any elements that you want to track.

   See the *Considerations* section below for tips on selecting elements. 

1. Click **[!UICONTROL Save]** at the top of the screen to save your selections.

When an activity entrant clicks a selected element, that click is counted as a conversion.

## Selected Elements panel {#selected-elements}

For [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP), and [!UICONTROL Multivariate Test] (MVT) activities, a [!UICONTROL Selected Elements] panel lists the selected elements for click tracking on the right side.

![Selected Elements panel](/help/c-activities/r-success-metrics/assets/selected-elements.png)

There are several actions that can be applied when you hover over an element in the [!UICONTROL Selected Elements] panel. The following table describes each action that can be performed on an element:

|Action|Description|
| --- | --- |
|Information|Displays the element type and the full DOM path to the selector.|
|Edit|Lets you edit the CSS selector.|
|Delete|Deletes the element.|

### Add element

If you already know the DOM path to the selector, you can add it manually by clicking the plus icon at the top of the panel.

![Add Element icon](/help/c-activities/r-success-metrics/assets/add-element.png)

### Selected Elements popup

After selecting multiple elements for click tracking, you can click the [!UICONTROL Elements Selected] link on the activity's [!UICONTROL Goals & Settings] step to see the full list of elements selected for click tracking. The list contains the full DOM path for the element to help you validate that the selected element is to be used for click tracking.

![Elements Selected link](/help/c-activities/r-success-metrics/assets/elements-selected-link.png)

## Considerations {#considerations}

There are several things to consider when selecting elements:

* The DOM path feature is available when setting up click tracking. When you click an element on the page, the VEC options menu displays. In addition, the corresponding DOM path displays at the bottom of the page. You can use the DOM path to quickly see information about the selected element (type, ID, and class) and move up or down the DOM path to select the desired element. 

  ![DOM path illustration](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

  Like when creating experiences in Step 1 in the activity-creation workflow, the DOM path selector at the bottom of the page lets you choose an element. On selecting an element from the DOM path, the corresponding element in the VEC displays as "Selected." To unselect a selected element, you can click the element again in the DOM path selector or click the "Selected" box within the VEC.

  For more information, see [Navigate elements using the DOM path](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) in *Visual Experience Composer Options*.

* You can browse to a different page to track clicks on a page where you might not be changing content. This different page must be included in the activity using the [multipage feature](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) and [!DNL at.js] must be implemented on it. 
* If you select more than one element, if an entrant clicks on any one of the chosen elements, the click is counted. To count each item separately, set up individual success metrics for each element. To count one item by clicking several elements on a page, edit the CSS Element Selector to match multiple elements.
* Make sure you select the level of element you want to track. For example, when specifying a button, make sure you select the link and not the button text. 
* Click events are sent to [!DNL Target] on the same page as the click. 
* If the click-tracking metric is the Goal metric of an [!UICONTROL Analytics for Target] (A4T) activity, the visitor must click this element within 60 seconds of the page loading for the metric to track. 
* Click tracking does not work on elements that include escaped characters in their selectors, including the following:

  |  Character  | Description  |
  |---|---|
  |  #  | Number sign or Hash  |
  |  :  | Colon  |
  |  .  | Period  |
  |  $  | Dollar sign  |
  |  `[ ]`  | Square brackets  |

* If you use [!DNL at.js] click tracking and you also use [!DNL Analytics] AppMeasurement, [!DNL at.js] click tracking cancels all other click event handlers. As a result, the AppMeasurement click handler never executes.

  [!DNL at.js] has special handling for click tracking when the underlying element is an `A` (link) tag or `FORM` tag.

  The following steps are executed by [!DNL at.js] when the click tracking event is attached to an `A` (link) tag or a `FORM` tag:

  1. Invoke `event.preventDefault()`.

  1. Fire [!DNL Target] request.

  1. On [!DNL Target] request success or error callback, execute default behavior:

     * `A` (link) tag: The default behavior is to navigate to the URL defined by HREF attribute. 
     * `FORM` tag: The default behavior is to submit the form.

  This default behavior might interfere with [!DNL Analytics] click tracking. If you are using [!DNL Analytics], you should rely on [!DNL Analytics] for click tracking rather than [!DNL Target].

* Click tracking is not recorded on pages where the page and activity URL belong to different properties. Enterprise user permissions is a [!DNL Target Premium] feature. For more information, see [Enterprise user permissions](/help/administrating-target/c-user-management/property-channel/property-channel.md).

* Click-tracking metrics are not linked to any specific experience in an activity.

* Use audiences if it is necessary to restrict the scope of the click-tracking metrics.

* Multiple activities can define a click-track metric for the same selector. If so, when a visitor qualifies for one of those activities and clicks that selector, the click-track metric increases for all associated activities that the visitor qualified for.

## Training Video {#section_36607204DAE146E3B8E2C609D244EDB1}

This video includes information about creating click-tracking success metrics.

* Understand "goal" metrics 
* Understand and build [!UICONTROL Conversion], [!UICONTROL Revenue], and [!UICONTROL Engagement] metrics 
* Build a click-tracking metric

>[!VIDEO](https://video.tv.adobe.com/v/17380)
