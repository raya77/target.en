---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: Learn how to send Adobe [!DNL Target] mobile app activity information to Adobe Analytics for post Ad Hoc segmentation.
title: Can I Send Mobile App Activity Information to Analytics?
feature: Implement Mobile
role: Developer
exl-id: 33812f14-320f-40c3-8234-d6006fb4d6bc
---
# Send activity information to Adobe Analytics

This section describes how to send [!DNL Target] mobile app activity information to Adobe [!DNL Analytics] for post hoc segmentation.

**Prerequisites**

* This integration requires that [!DNL Analytics] and [!DNL Target] are implemented using the mobile SDK. 
* Ensure that your report suite is enabled to receive activity information from [!DNL Target].

  This is usually done by adding the [!DNL Target] client code to the [!DNL Analytics] report suite. This might be enabled already if you are using the SiteCatalyst-Test&Target integration for web activities. Contact Adobe Client Care if you have any questions about this step.

1. Obtain the activity information.

   If you include a string like the following in your experience content, [!DNL Target] returns the activity information that you can send to [!DNL Analytics]:

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Replace the text in your experience json code with something like the following example:

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   In this example, a node with the variable `tntVal` is added to obtain the activity information. Add similar code for the other experiences, with an appropriate title and message.

   This string delivers a number (such as 115110:0:0) in the response from [!DNL Target]. This indicates the activity ID, experience ID, and traffic type. The following is a sample response from [!DNL Target]:

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Parse the JSON object.

   Parse the response that came back from [!DNL Target] in the callback. You can use `NSJSONSerialization` to parse this response and store it in a dictionary or an array.

   Refer to the [NSJSONSerialization documentation](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) for more information.

1. Send the data to [!DNL Analytics].

   Add the parsed activity information (such as `tntVal` in the above response) to your context data object in an [!DNL Analytics] call. This [!DNL Analytics] call containing the context data can be fired immediately or it can wait until the next [!DNL Analytics] call is fired.

   For example, this call can be fired in the callback of the `targetLoadRequest` call:

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`is a reserved event key in the mobile SDK. The post-classification of the `tntVal` variable in [!DNL Analytics] works in the same way in the mobile SDK as it does on the web (JavaScript). After the information is processed in [!DNL Analytics], you should see activity and experience names in the [!DNL Analytics] interface.
