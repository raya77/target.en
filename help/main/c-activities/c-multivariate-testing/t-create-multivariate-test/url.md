---
keywords: Multivariate Tests;activity url
description: Learn how to specify the Activity URL that determines the page that is used in the test and that opens when the Multivariate Test activity is designed using Adobe Target.
title: What Is the Activity URL In an Multivariate (MVT) Activity?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
---
# Activity URL

The activity URL determines the page that is used in the [!UICONTROL Multivariate Test] (MVT), and that opens when the test is designed in [!DNL Adobe Target].

When prompted during [activity creation](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), specify the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] does not differentiate between URL protocols ( [!DNL https] and [!DNL http]). As a result, [!DNL `https://www.adobe.com`] and [!DNL `http://www.adobe.com`] both match.

By default, the [!UICONTROL Visual Experience Composer] (VEC) opens the page that is specified in your [Visual Experience Composer settings](/help/main/administrating-target/visual-experience-composer-set-up.md). You can specify a different page during activity creation.

To display a different page after the VEC opens, click the **[!UICONTROL Configure]** icon, then select **[!UICONTROL Page Delivery]**, then specify the URL.

![Page Delivery dialog box](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

Additional rules can be based on any of the following:

* URL 
* Domain 
* Path 
* Hash (#) Fragment 
* Query 
* Parameter

Additional rules can be joined to the Activity URL with AND or OR. All rules you add are evaluated against each other with AND.

Click **[!UICONTROL Save]** when you have finished.

>[!NOTE]
>
>If you entered a URL for a site that does not include the Target Standard JavaScript code, you cannot select page elements.

By default, the VEC does not allow changes to elements containing JavaScript, such as rotating banners. You can toggle off **[!UICONTROL Render using JavaScript]** if you want to be able to alter those elements using the [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>If you change the URL after making changes to a page for one or more experiences, the experience is reset using the new page and the changes you made are lost.
