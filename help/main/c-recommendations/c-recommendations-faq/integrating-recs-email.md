---
keywords: email;ESP;email service provider;rawbox;delivery API;download-only template;email template;batch processing;build-time email
description: Learn how to integrate email with Adobe [!DNL Target Recommendations], including using the [!DNL Target] Delivery API, rawbox templates, and down-load only templates.
title: How Do I Integrate Recommendations with Email?
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
---
# ![PREMIUM](/help/main/assets/premium.png) Integrate [!DNL Recommendations] with email

[!DNL Adobe Target] supports send-time personalization of recommendations in email. 

Three methods for integrating [!DNL Target Recommendations] with your Email Service Provider (ESP) are available. Your ESP's capabilities determine which method to use. Your account manager or consultant can help you choose the option that works best for you.

|Method|Details|
| --- | --- |
|[Method 1: [!DNL Adobe Target Delivery API]](#delivery-api) (Preferred)|Use the [!DNL Adobe Target Delivery API] to make per-customer/per-email requests for recommendations.|
|[Method 2: [!DNL Adobe Rawbox API]](#rawbox)|Use the [!DNL Adobe Target Rawbox API] to make per-customer/per-email requests for recommendations.|
|[Method 3: [!DNL Recommendations Download API]](#download-api)|Use the Recommendations Download API to request bulk recommendations for a list of products or categories in CSV format.|

Using method 1 or method 2 requires your ESP to make calls to an external API on a per-customer/per-email basis and wait for content to be returned. These methods are not supported by all ESPs; contact your ESP to determine if it is compatible with this integration pattern.
 
Using method 3 requires your ESP to join a list of recommendations by product ID or category ID to your list of emails. This method can be based on an attribute such as the customer’s last viewed product, last purchased product, or most viewed category. However, your ESP must have access to this data in its customer profile in order to perform the join. Contact your ESP to determine if it has access to this data and is compatible with this integration pattern.
 
Open-time personalization of recommendations is not supported by [!DNL Adobe Target].

>[!IMPORTANT]
>
>The following capacity guidelines apply to the Delivery API and rawbox email template methods described below (methods 1 and 2):
>
>* Requests should be rate-limited to the lower of 1,000 requests per second or 25 times your peak daily traffic.
>* Ramp traffic in steps of 200 requests per second each minute.
> 
>Contact your account manager if you want to use higher rate limits.

## Method 1: Use the delivery API (Preferred) {#delivery-api}

The delivery API is a POST request that works with build-time email. This option is the preferred method for build-time email.

Most email clients do not allow POST requests. Therefore, this API is not recommended for open-time use cases. Some email clients, such as Gmail or Outlook, can cache the content or block the image and require the recipient to pro-actively allow the image to render.

You cannot return default content using the delivery API.

The following code is a sample API delivery request:

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

Where `clientcode` is your [!DNL Target] client code.

>[!NOTE]
>
>Be sure to provide a unique value for both `sessionId` and one of `tntId` or `thirdPartyId` for each email recipient (for example, for each API call). If you do not provide unique values for these fields, API response can slow or fail due to many events generated within a single profile.

See [Delivery API documentation](https://developer.adobe.com/target/implement/delivery-api/) for more information.

## Method 2: Use a rawbox email template {#rawbox}

A rawbox is similar to an mbox request, but for non-Web environments, such as email service providers (ESPs). Because you don't have the [!DNL Adobe Experience Platform Web SDK] or [!DNL at.js] to use in rawbox requests, you must create your requests manually. The examples below explain how to work with rawbox requests in email.

>[!NOTE]
>
>When using a rawbox and [!DNL Target], see the important security notice under [Create allowlists that specify hosts that are authorized to send mbox calls to [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist).

This approach allows you to track performance of recommendations in emails, test them in the normal way with a recommendation, and continue tracking on the site.

Set up a [!DNL Recommendations] activity in [!DNL Target], using the [Form-Based Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) option. For the location, select the name of the mbox you've chosen to use in the rawbox request coming from the ESP. Select a design with the look and feel you want for your email. At email build time, the ESP makes a call to the [!DNL Target] servers for each rawbox in each email being generated. Your ESP must have a way to include the returned HTML in the email when it is sent.

The email system you use must be able to handle the following scenarios:

### A valid response is received, but no recommendations are present

* In this case, the response is whatever is set as the `mboxDefault` parameter value. See explanation below on this parameter.
* The email provider should have a default HTML block of recommendations to use in this case.

### The [!DNL Target] server times out and returns without data

* In this case, the [!DNL Target] server returns the following content:

  `//ERROR: application server timeout`

* The email application should search for that text and must be able to handle the error. The email provider has multiple options for handling this case:

  * Try another server call immediately (recommended, perhaps with an attempt counter).
  * Toss out that particular email and continue to the next one.
  * Queue that particular email and rerun failed emails as a batch at the end of the initial run.

### Sample request URL

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Required parameters: {#reqparams}

>[!NOTE]
>
>To use [!DNL Recommendations] in email, the rawbox call must usually include either the `entity.id` or `entity.categoryId` or both, depending on the type of recommendation criteria. The sample call above includes both.

| Parameter | Value | Description | Validation |
|--- |--- |--- |--- |
|`client_code`|*client_code*|The client’s code used in Recommendations. Your Adobe consultant can provide this value.||
|`mbox`|*mboxName*|The mbox name that is used for targeting.|Same validation as for all mbox calls.<br>250 character limit.<br>Cannot contain any of the following characters: `', ", %22, %27, <, >, %3C, %3E`|
|`mboxXDomain`|disabled|Prevents the response from setting a cookie in non-web environments.||
|`entity.id`<br>(Required for certain types of criteria: view/view, view/bought, bought/bought)|*entity_id*|The productId the recommendation is based on, such as an abandoned product in the cart, or a previous purchase.<br>If required by the criteria, the rawbox call must include the `entity.id`.||
|`entity.event.detailsOnly`|true|If `entity.id` is passed, it is highly recommended to also pass this parameter to prevent the request from incrementing the number of tallied page views for an item, so as not to skew product view-based algorithms.||
|`entity.categoryId`<br>(Required for certain types of criteria: most viewed by category and top sellers by category)|*category_id*|The category the recommendation is based on, such as top sellers in a category.<br>If required by the criteria, the rawbox call must include the `entity.categoryId`.||
|`mboxDefault`|*`https://www.default.com`*|If the `mboxNoRedirect` parameter is not present, `mboxDefault` should be an absolute URL that returns default content if no recommendation is available. This URL can be an image or other static content.<br>If the `mboxNoRedirect` parameter is present, `mboxDefault` can be any text indicating there are no recommendations, for example `no_content`.<br>The email provider must handle the case where this value is returned and insert default HTML into the email. <br> **Security best practice**: If the domain used in the `mboxDefault` URL is not allowlisted, you can be exposed to a risk of an Open Redirect Vulnerability. To avoid the unauthorized use of Redirector links or `mboxDefault` by third parties, Adobe recommends you use "authorized hosts" to allowlist the default redirect URL domains. Target uses hosts to allowlist domains to which you want to allow redirects. For more information, see [Create Allowlists that specify hosts that are authorized to send mbox calls to [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist) in *Hosts*.||
|`mboxHost`|*mbox_host*|The domain that is added to the default environment (host group) when the call fires.||
|`mboxPC`|Empty|(Required for recommendations that use a visitor's profile.)<br>If no “thirdPartyId” was provided, a new tntId is generated and returned as part of the response. Otherwise remains empty.<br>**Note**: Be sure to provide a unique value of `mboxSession` and `mboxPC` for each email recipient (i.e., for each API call). If you do not provide unique values for these fields, API response can slow or fail due to the large number of events generated within a single profile.|1 < Length < 128<br>Cannot contain more than a single “.” (dot).<br>The only dot allowed is for profile location suffix.|

### Optional parameters

| Parameter | Value | Description | Validation |
|--- |--- |--- |--- |
|`mboxPC`<br>(Optional)|*mboxPCId*|Target visitor ID. Use this value when if you want to track a user full-circle back to your site across multiple visits, or when using a user profile parameter.<br>This value must be the actual [!DNL Adobe Target] PCID for the user, which would be exported from the website to your CRM. The email provider would retrieve this ID from your CRM or Data Warehouse, and use it for the value of this parameter.<br>The `mboxPC` value is also useful for tracking visitor site behavior across multiple visits for metrics tracking when a recommendation is part of an A/B activity.<br>**Note**: Be sure to provide a unique value of `mboxSession` and `mboxPC` for each email recipient (i.e., for each API call). If you do not provide unique values for these fields, API response can slow or fail due to the large number of events generated within a single profile.|1 < Length < 128<br>Cannot contain more than a single "." (dot).<br>The only dot allowed is for profile location suffix.|
|`mboxNoRedirect`<br>(Optional)|1|By default, the caller is redirected when no deliverable content is found. Use to disable the default behavior.||
|`mbox3rdPartyId`|*xxx*|Use this option if you have your own custom visitor ID to use for profile targeting.||

### Potential [!DNL Target] server responses

| Response | Description |
|--- |--- |
|//ERROR:|Generated by load balancer when it can't return content|
|Success|The `mboxNoRedirect` parameter is set to 'true' and the server does not return any recommendations (i.e., there is no match for the mbox or the server cache is not initialized).|
|bad request|The `mbox` parameter is missing.<ul><li>Either `mboxDefault` or the `mboxNoRedirect` parameter is not specified.</li><li>`mboxTrace` request parameter is specified but `mboxNoRedirect` is not.</li><li>`mboxTarget`parameter is not specified when mbox names end with `-clicked` suffix.</li></ul>|
|`Cannot redirect to default content, please specify mboxDefault parameter`|`mboxDefault` not specified when no match for the request exists and `mboxNoRedirect` parameter is not specified.|
|`Invalid mbox name:= MBOX_NAME`|Indicates `mbox` parameter contains invalid characters.|
|`Mbox name [MBOX_NAME] is too long`|Indicates `mbox` parameter is longer than 250 characters.|

## Method 3: Use the Recommendations Download API {#download-api}

Set up a recommendation as usual, but choose **download only** in the presentation section instead of a template and mbox combination. Then in the ESP, tell the ESP what recommendation ID you created. The ESP accesses the recommendation data via API. This data shows which items should be recommended for a particular category or key item, such as items in an abandoned cart. The ESP stores this data, connects it with their own look and feel, displays information about each item, and delivers that in the emails.

With this option, the recommendations server cannot directly track the performance of a recommendation or split traffic across multiple algorithm/template combinations. Also, the recommendations are not tied to a visitor profile.

For more information about the download API, see [Legacy APIs > Download](/help/main/assets/adobe-recommendations-classic.pdf).
