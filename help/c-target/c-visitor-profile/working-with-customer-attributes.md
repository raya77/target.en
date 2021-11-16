---
keywords: customer relationship management;customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm;adobe experience cloud people
description: Learn how to use enterprise customer data from a customer relationship management (CRM) database for content targeting in [!DNL Adobe Target].
title: What Are Customer Attributes and How Do I Use Them?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
---
# [undefined](/help/c-target/c-visitor-profile/working-with-customer-attributes.md)

Information about using enterprise customer data from Customer Relationship Management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud People] service.

Enterprise customer data collected through multiple sources and stored inside CRM databases can be used in [!DNL Target] to strategically deliver the most relevant content to customers, specifically focusing on returning customers. Audiences and customer attributes in the [!DNL People] service (formerly Profiles and Audiences) brings together data collection and analysis with testing and optimization, making data and insights actionable.

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

[Customer Attributes](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) in the [!DNL People] service is part of the [!DNL Adobe Experience Cloud] and provides enterprises a tool to push their customer data to the [!DNL Experience Cloud] platform. 

Data onboarded to the [!DNL Experience Cloud] is available for all [!DNL Experience Cloud] workflows. [!DNL Target] uses this data for targeting returning customer based on attributes. [!DNL Adobe Analytics] consumes these attributes and they can be used for analysis and segmentation.

![crs example](/help/c-target/c-visitor-profile/assets/crs.png)

Consider the following information as your work with customer attributes and [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL People] service. For more information, see "Prerequisites for uploading Customer Attributes" in [Customer attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) in the *Experience Cloud Services and Administration documentation*. 
* Be aware of the limitations concerning file uploads, as documented in [About data file and data sources for Customer Attributes](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en) in the *Experience Cloud Central Interface Components Guide*. As best practice:

  * Upload single large files (within the [limits specified](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en)). Single large files are preferred over multiple smaller files.
  * If you must split the upload into several files, ensure that files are fully processed before submitting new files. Ensure that each file in a batch is fully processed prior to submitting the next batch.

* [!DNL Adobe] does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. In the current design, there is a possibility that a small percentage of data (up to 0.1% of large production batches) might not be onboarded. 
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. For more information, see [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD). 
* If the `vst.*` parameters are the only thing identifying the visitor, the existing "authenticated" profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile comes into play only if `authState` is changed to AUTHENTICATED (1).

  For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` does not fetch the profile that might have been created through a Customer Attributes import. If the desired behavior is to fetch the authenticated profile, the `vst.myDataSource.authState` must have the value of 1 (AUTHENTICATED).

* You cannot send the following characters in `mbox3rdPartyID`: plus sign (+) and forward slash (/).

## Access Customer Attributes in the People service

1. In the [!DNL Adobe Experience Cloud], click the menu icon ( ![menu icon](/help/c-target/c-visitor-profile/assets/menu-icon.png) ) then click **[!UICONTROL People]**.

   ![People](/help/c-target/c-visitor-profile/assets/people.png)

1. Click the **[!UICONTROL Customer Attributes]** tab.

   ![Customer Attributes tab](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Customer attribute workflow for [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Complete the following steps to use CRM data in [!DNL Target], as illustrated below:

![crm workflow](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) in the *Experience Cloud Services and Administration documentation*.

1. Create a data file.

   Export customer data from your CRM to CSV format to create a .csv file. Alternately, a zip or gzip file can be created for uploading. Ensure that first row of the CSV file is the header and all rows (customer data) have the same number of entries.

   The following illustration shows a sample enterprise customer data file:

   ![crs sample](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   The following illustration shows a sample enterprise customer .csv file:

   ![csv sample](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Create the attribute source and upload the data file.

   Specify a Name and Description of the data source and the alias Id. The alias Id is a unique ID to be used in your Customer Attribute code in `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >The data source name and the attribute name cannot contain a period.

   Your data file must comply with the file Upload Requirements and must not exceed 100 MB. If your file is too large, or you have data that must be uploaded on a recurring basis you can FTP your files instead.

   * **HTTPS:** You can drag-and-drop the .csv data file or click **[!UICONTROL Browse]** to upload from your file system. 
   * **FTP:** Click the FTP link to [upload the file through FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). First step is to provide a password for the Adobe-provided FTP server. Specify the password, then click **[!UICONTROL Done]**.

   Now transfer your CSV/ZIP/GZIP file to the FTP server. After this file transfer is successful, create a file with the same name and a `.fin` extension. Transfer this empty file to the server. This indicates an End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. Validate the schema.

   The validation process lets you map display names and descriptions to uploaded attributes (strings, integers, numbers, and so on). Map each attribute to its correct data type, display name, and description.

   Click **[!UICONTROL Save]** after the schema validation is complete. The file upload time varies depending on the size.

   ![Validate schema](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Upload schema](/help/c-target/c-visitor-profile/assets/upload1.png)

1. Configure subscriptions and activate the attribute source.

   Click **[!UICONTROL Add Subscription]**, then select the solution to subscribe these attributes. [Configure subscriptions](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) sets up the data flow between the [!DNL Experience Cloud] and solutions. Activating the attribute source allows the data to flow to subscribed solutions. The customer records you have uploaded are matched up with incoming ID signals from your website or application.

   ![Configure solution](/help/c-target/c-visitor-profile/assets/solution.png)

   ![Activate](/help/c-target/c-visitor-profile/assets/activate.png)

   While performing this step, be aware of the following limitations:

   * The maximum file size for each upload using the HTTP method is 100 MB. 
   * The maximum file size for each upload using the FTP method is 4 GB. 
   * The number of attributes allowed to subscribe: 5 for [!DNL Target Standard] and 200 for [!DNL Target Premium].

## Use customer attributes in [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

You can use customer attributes in [!DNL Target] in the following ways:

### Creating targeting audiences

In [!DNL Target], you can select a customer attribute from the [!UICONTROL Visitor Profile] section when creating an audience. All customer attributes have the prefix &lt; data_source_name &gt; in the list. Combine these attributes as required with other data attributes to build audiences.

![Target Audience](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### Creating profile scripts using tokens

Customer attributes can be referenced in profile scripts using format `crs.get('<Datasource Name>.<Attribute name>')`.

This profile script can be used directly in offers for delivering attributes that belong to the current visitor.

### Using mbox3rdPartyID in your website for a successful implementation and usage

Pass `mbox3rdPartyId` as a parameter to the global mbox inside the `targetPageParams()` method. The value of `mbox3rdPartyId` should be set to the customer ID that was present in the CSV data file.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Using the Experience Cloud ID Service

If you are using the Experience Cloud ID service, you must set a Customer ID and Authentication State to use customer attributes in targeting. For more information, see [Customer IDs and Authentication State](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) in the *Experience Cloud ID Service Help*.

For more information about using customer attributes in [!DNL Target], see the following resources:

* [Create a customer attribute source and upload the data file](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud Services and Administration documentation* 

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

You might encounter the following issues when working with customer attributes and [!DNL Target].

>[!NOTE]
>
>Issues 1 and 2 cause approximately 60% of problems in this area. Issue 3 causes approximately 30% of problems. Issue 4 causes approximately 5% of problems. The remaining 5% are due to miscellaneous issues.

### Issue 1: Customer attributes are removed because the profile is too large

There is no character limit on a particular field in the user's profile, but if the profile gets larger than 64 K, it is truncated by removing the oldest attributes until the profile is below 64 K again.

### Issue 2: Attributes not listing in the Audience Library in [!DNL Target], even after several days

This is usually a Pipeline connection problem. As a resolution, ask your Customer Attributes team to republish the feed.

### Issue 3: Delivery not working based on the attribute

The profile has not been updated on the edge yet. As a resolution, ask your Customer Attributes team to republish the feed.

### Issue 4: Implementation issues

Be aware of the following implementation issues:

* The Visitor Id was not passed correctly. The ID was passed in `mboxMCGVID` instead of `setCustomerId`.
* The Visitor Id was passed correctly, but the AUTHENTICATION state was not set to Authenticated.
* `mbox3rdPartyId` was not passed correctly.

### Issue 5: `mboxUpdate` not performed properly

`mboxUpdate`  was not performed properly with `mbox3rdPartyId`.

### Issue 6: Customer attributes are not being imported into [!DNL Target]

If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default).

## Training video: Upload Offline Data using Customer Attributes ![Tutorial badge](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

This video shows you how to import offline CRM, help desk, point-of-sale, and other marketing data into the [!DNL Experience Cloud People] service and associate it with visitors using their known IDs.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
