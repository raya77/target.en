---
keywords: implement;implementing;setting up;setup;page parameter;tomcat;url encoded;in-page profile attribute;mbox parameter;in-page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;dataprovider;data provider
description: Get data into Target (page parameters, profile attributes, script profile attributes, data providers, single and bulk profile update APIs, Customer Attributes).
title: How Do I Get Data into Target?
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
---
# Methods overview

Information about the different methods you can use to get data into [!DNL Adobe Target].

Available methods include:

|Method|Details|
| --- | --- |
|[Page parameters](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>(also called "mbox parameters")|Page parameters are name/value pairs passed in directly through page code that are not stored in the visitor's profile for future use.<br>Page parameters are useful to send additional page data to Target that does not need to be stored with the visitor's profile for future targeting use. These values are instead used to describe the page or the action the user took on the specific page.|
|[In-page profile attributes](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>(also called "in-mbox profile attributes)|In-page profile attributes are name/value pairs passed directly through page code that are stored in the visitor's profile for future use.<br>In-page profile attributes allow user-specific data to be stored in Target's profile for later targeting and segmentation.|
|[Script profile attributes](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md)|Script profile attributes are name/value pairs defined in the Target solution. The value is determined from executing a JavaScript snippet on Target's server per server call.<br>Users write small code snippets that execute per mbox call, and before a visitor is evaluated for audience and activity membership.|
|[Data providers](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md)|Data providers is a capability that allows you to easily pass data from third parties to Target.|
|Bulk profile update API|Via API, send a .csv file to Target with visitor profile updates for many visitors. Each visitor profile can be updated with multiple in-page profile attributes in one call.|
|Single profile update API|Almost identical to the Bulk Profile Update API, but one visitor profile is updated at a time, in line in the API call instead of with a .csv file.|
|Customer attributes|Customer attributes let you upload visitor profile data via FTP to the Experience Cloud. Once uploaded, leverage the data in Adobe Analytics and Adobe Target.|







## Bulk profile update API {#section_92AB4820A5624C669D9A1F1B6220D4FA}

Via API, send a .csv file to Target with visitor profile updates for many visitors. Each visitor profile can be updated with multiple in-page profile attributes in one call.

This option is very similar to Customer Attributes with a few differences:

* Customer Attributes use an FTP upload while the Target Bulk Profile Update API uses an HTTP POST API.
* Customer Attributes data can be shared with Analytics. Bulk Profile Update is useable only in Target.
* Customer Attributes support creating a profile for a user Target has not yet seen. The Bulk Profile Update API updates existing Target profiles only.
* Customer Attributes require the use of the Experience Cloud ID (ECID). The Bulk Profile Update API requires either the TNT ID or the `mbox3rdPartyId`.
* You cannot send the following characters in `mbox3rdPartyID`: plus sign (+) and forward slash (/).

### Format

The .csv file must refer to each visitor via his or her Target PCID or mboxThirdPartyId . The Experience Cloud ID (ECID) is not supported. All profile attributes/values are created and updated via the API. Format details are available in the API documentation.

### Example Use Cases

Your CRM or other internal system stores valuable data about your visitors that you want to consistently update into Target, without exposing the profile data in your page implementation.

### Benefits of Method

No limit on the number of profile attributes.

Profile attributes sent via the site can be updated via the API and vice versa.

### Caveats

The size of the batch file must be less than 50 MB. In addition, the total number of rows should not exceed 500,000 rows per upload.

There is no limit on the number or rows you can upload over a period of 24 hours in subsequent batches. However, the ingestion process might be throttled during business hours to ensure that other processes run efficiently.

Consecutive [V2 batch update calls](https://developers.adobetarget.com/api/#updating-profiles) without mbox calls in between for the same thirdPartyIds override the properties updated in the first batch update call.

### Code Examples

See [Updating Profiles](https://developers.adobetarget.com/api/#updating-profiles).

### Links to Relevant Information

[Updating Profiles](https://developers.adobetarget.com/api/#updating-profiles)

## Single profile update API {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Almost identical to the Bulk Profile Update API, but one visitor profile is updated at a time, in line in the API call instead of with a .csv file.

### Format

The visitor must be identified via the Target mboxPC value or mboxThirdPartyId value. The Experience Cloud ID (ECID) is not supported.

### Example Use Cases

You want to update Target in real-time when a visitor performs some offline action, such as reaching a call center, a loan is funded, using a loyalty card in store, accessing a kiosk, and so forth.

### Benefits of Method

No limit on the number of profile attributes.

Profile attributes sent via the site can be updated via the API and vice versa.

### Caveats

Limit of 1,000,000 API calls (1 million) per 24-hour period

Updates profiles only. Cannot create a profile for a potential user Target has yet to see.

### Code Examples

GET and POST supported. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Links to Relevant Information

[Updating Profiles](https://developers.adobetarget.com/api/#updating-profiles)

## Customer Attributes {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Customer attributes let you upload visitor profile data via FTP to the Experience Cloud. Once uploaded, leverage the data in Adobe Analytics and Adobe Target.

Target Standard customers can leverage 5 attributes, Target Premium customers can leverage 200 attributes.

### Format

A .csv file with Experience Cloud IDs (ECIDs) and attribute name/value pairs is uploaded via FTP or manually in the Experience Cloud UI.

### Example Use Cases

Your CRM or other internal system stores valuable information you want to share with Adobe's Experience Cloud, including Target and Analytics.

### Benefits of Method

Uploading customer data creates a profile entry for that visitor in Target, even if Target has yet to see the visitor.

Same data is automatically available in Target and Analytics.

FTP can be a simpler implementation method than API.

### Caveats

Target Standard customers can leverage 5 attributes, Target Premium customers can leverage 200 attributes

Can only update values via Customer Attributes, not on page.

Requires Experience Cloud ID (ECID) implementation.

### Code Examples

Details can be found in [Create a customer attribute source and upload the data file](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Links to Relevant Information

[Create a customer attribute source and upload the data file](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
