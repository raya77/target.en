---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: Learn how to upload a CSV file to customize your recommendations in Adobe [!DNL Target] Recommendations.
title: How Do I Upload Custom Criteria in Recommendations?
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
---
# ![PREMIUM](/help/main/assets/premium.png) Upload custom criteria

Upload a CSV file to customize your recommendations in [!DNL Adobe Target].

There are multiple ways to reach the [!UICONTROL Create New Criteria] screen. Some screen options vary depending on how you reach the screen.

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Criteria you create here are automatically made available for all [!DNL Recommendations] activities.
* When you are creating a [!DNL Recommendations] activity using the [!UICONTROL Visual Experience Composer] (VEC), you are immediately taken to the [!UICONTROL Select Criteria] screen after you select an element on your page and click [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before], or [!UICONTROL Insert Recommendations After]. You can then select an available criteria or you can click **[!UICONTROL Create Criteria]**. If you create a new criteria, you can save your criteria for use with other [!DNL Recommendations] activities. For more information, see [Create a Recommendations activity](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* When you are editing a [!DNL Recommendations] activity, click in a [!UICONTROL Recommendations Location] box on your page, and select **[!UICONTROL Change Criteria]**. On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. You can save your new criteria for use with other [!DNL Recommendations] activities.

The following steps assume you access the [!UICONTROL Create New Criteria] screen by using the first method: the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen.

1. Click **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Click **[!UICONTROL Create Criteria]**.

1. Fill in the information in the [Basic Information](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) section.

   1. From the **[!UICONTROL Select Algorithm]** Type drop-down list, select **[!UICONTROL Custom Criteria]**.

   1. From the **[!UICONTROL Algorithm]** drop-down list, select **[!UICONTROL Custom Algorithm]**.

      >[!NOTE]
      >
      >The preceding steps cause the [!UICONTROL Upload CSV] section to display at the bottom of the [!UICONTROL Create New Criteria] dialog box.

1. (Conditional) Fill in the information in the [Backup Content](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) section.

1. (Conditional) Fill in the information in the [Inclusion Rules](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) section.

1. In the **[!UICONTROL Upload CSV]** section, select the **[!UICONTROL Location]** of your CSV file.

    ![Upload CSV section](assets/upload-csv.png)

   The CSV file must be formatted correctly to upload successfully. Click **[!UICONTROL Download the CSV template]** to get a correctly formatted CSV file.

   You have two location options:

    * **FTP:** To upload your CSV file from an FTP server, select **[!UICONTROL FTP]**, then enter the required information. You can use SSL, which uses the FTPS protocol to transfer your CSV file securely. 
    * **URL:** To upload your CSV file from a URL, select **[!UICONTROL URL]**, then enter a feed URL.

1. Click **[!UICONTROL Save]**.

## Considerations

* Custom criteria entities (rows) can contain up to 1,000 recommended items (columns).

* Custom criteria updates are by default "cumulative." New key-value pairs specified in the CSV upload file overwrite existing key-value pairs. Existing key-value pairs that don't have keys specified in the CSV upload are still available for delivery and expire in 31 days from the time they are last uploaded as part of the CSV file.

  Contact Client Care to enable the setting to discard the existing results that aren't included in the next CSV upload. If this setting is enabled, only the keys present in the custom CSV feed file are available for delivery. This setting applies to all custom criteria.

* Custom criteria feeds update once every 24 hours.

  You can see the upload and sync status of your custom criteria upload at the bottom of each criteria card on the [!UICONTROL Recommendations] > [!UICONTROL Criteria] page. You can also see the status in the [!UICONTROL Edit] dialog box when editing custom criteria.

* The flow for an error-free upload should be [!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful].

* The following are possible error messages you might receive if [!DNL Target] encounters a problem with the upload:

  | Error Message | Details |
  |--- |--- |
  |Unknown Error|Indicates an internal technical error.|
  |Parsing Error|There is likely an issue with the feed file format. Correct the file format and resave the algorithm, which restarts the file download process.|
  |Server Not Found|Provide an IP or Host Name that is visible on the internet.|
  |Credentials Error|Provide a valid user and password for an active account on the server.|
  |Directory Not Found|Provide a directory that exists on the server.|
  |File Not Found|Provide the name of a file that exists on the server in the directory indicated.|

## Training video: Create criteria in Recommendations (12:33) ![Tutorial badge](/help/main/assets/tutorial.png)

This video contains the following information (details about uploading custom criteria begins at 11:43):

* Create criteria
* Create criteria sequences
* Upload custom criteria

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
