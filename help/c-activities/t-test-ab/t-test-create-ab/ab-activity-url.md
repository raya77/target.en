---
keywords: activity url;url;different url
description: Learn how to specify the Activity URL that determines the page that is used in the test and that opens when the test is designed using Adobe Target.
title: What Is the  Activity URL In an A/B Activity?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
---
# Activity URL

The Activity URL determines the page that is used in the test and that opens when the test is designed using Adobe Target.

When prompted during activity creation, specify the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] does not differentiate between URL protocols ( [!DNL https] and [!DNL http]). As a result, [!DNL `http://www.adobe.com`] and [!DNL `https://www.adobe.com`] both match.

## Specify a different URL

By default, the [!UICONTROL Visual Experience Composer] opens the page that is specified in your [Visual Experience Composer settings](/help/administrating-target/visual-experience-composer-set-up.md)
. You can specify a different page during activity creation.

To display a different page after the [!UICONTROL Visual Experience Composer] opens, click the **[!UICONTROL Configure]** gear icon, then select **[!UICONTROL Page Delivery]**. Enter the URL in the Activity URL field.

![Page Delivery dialog box](/help/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

Additional rules can be based on any of the following:

* URL 
* Domain 
* Path 
* Hash (#) Fragment 
* Query 
* mbox Parameter

Additional rules can be joined to the Activity URL with AND or OR. All rules you add are evaluated against each other with AND.

Click **[!UICONTROL Save]** when you have finished.

>[!NOTE]
>
>If you entered a URL for a site that does not include the [!DNL Target] Standard JavaScript code, you cannot select page elements.

By default, the [!UICONTROL Visual Experience Composer] does not allow changes to elements containing JavaScript, such as rotating banners. You can toggle off **[!UICONTROL Render using JavaScript]** if you want to be able to alter those elements using the [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>If you change the URL after making changes to a page for one or more experiences, the experience is reset using the new page and the changes you made are lost.
