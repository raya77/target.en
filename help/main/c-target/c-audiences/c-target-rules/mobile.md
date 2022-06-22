---
keywords: targeting;mobile;target mobile;deviceatlas;iphone;iphone models;device atlas;displaywidth;display width;display height;type of device;displayheight;phone;tablet;device model
description: Learn how to create audiences in [!DNL Adobe Target] to target mobile devices.
title: Can I Target Visitors Based on Mobile Options?
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
---
# Mobile

Create audiences in [!DNL Adobe Target] to target mobile devices based on parameters such as mobile device, type of device, device vendor, screen dimensions, and more.

For example, you might want to show different content to users who visit your page using a phone than you would show if they visit using a computer. In that case, you could select the [!UICONTROL Mobile] audience, then select the **[!UICONTROL Is Mobile Phone]** option. You could then add any specific details that are important to you, such as the type of phone, size of the screen (in pixels), and so on.

Mobile targeting is delivered by [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), a service of DotMobi. DeviceAtlas is a comprehensive database of mobile devices built on data compiled from numerous sources, including manufacturers and network operators. This data is then verified, cross-referenced, and validated to build a large and accurate mobile device database available.

Device detection is accomplished by analyzing User-Agent strings. Some device manufacturers, such as Apple, disable this functionality by not providing enough information in the UA.

For example, Apple devices don't share device model-specific tokens in the UA. The result is that it is not possible to detect iPhone models (such as iPhone 12 Pro, iPhone 12, iPhone 11 Pro Max, and so forth) using a simple keyword-based method.

To solve this issue, [!DNL Target] collects additional data to accurately detect iPhones and other Apple devices using the following parameters:

| Parameter | Type | Description |
|--- |--- |--- |
|devicePixelRatio|String|Ratio between physical pixels and device-independent pixels (dips) on the browser. For example, “1.5” or “2”|
|screenOrientation|String|The device and the browser's JavaScript engine support Device Orientation. Can be Landscape or Portrait.|
|webGLRenderer|String|Browser renderer of the graphics driver.|

>[!NOTE]
>
>Customers using the Mobile SDK do not need to do anything to apply this functionality. Customers using at.js must [upgrade to at.js version 1.5.0](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) (or later).

You can choose more than one mobile device property. Multiple selections are joined with an OR operator.

Customers who are using a custom integration (not using at.js or the Mobile SDK) can collect these parameters themselves and pass them as mbox parameters.

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**. 
1. Name the audience and add an optional description. 
1. Drag and drop **[!UICONTROL Mobile]** into the audience builder pane.
1. Click **[!UICONTROL Select]**, then select one of the following options:

    * Device Marketing Name 
    * Device Model 
    * Device Vendor 
    * Is Mobile Device 
    * Is Mobile Phone 
    * Is Tablet 
    * OS 
    * Screen Height (px) 
    * Screen Width (px)

   >[!NOTE]
   >
   >You can target by mobile device carrier using the [Geo settings](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Optional) Set up additional rules for the audience. 
1. Click **[!UICONTROL Done]**.

The following illustration shows an audience targeting visitors using devices manufactured by Google that are mobile devices.

![Target mobile devices](assets/target_mobile.png)

## Considerations

Consider the following information when targeting mobile devices: 

### Targeting devices running iOS 12.2 or later

Due to the new changes introduced in iOS 12.2, creating an audience with rules defined by [!UICONTROL Device Marketing Name] and [!UICONTROL Device Model] that specify iPhone Models is impacted. [!DNL Target] can no longer target users who have iPhones with iOS 12.2 (or later) installed on them. However, if those users do not have iOS 12.2 (or later), then the iPhone Model targeting continues to work correctly.

The iOS 12.2 (or later) update does not affect the identification of the following models because these models do not support upgrading to iOS 12.2: iPhone, iPhone 3G, iPhone 3GS, iPhone 4, iPhone 4s, iPhone 5, iPhone 5c, iPad, iPad 2, iPad / Retina display, iPad Retina (4th Generation), iPod Touch 4, and iPod Touch 5.

### Targeting devices running Safari 14.0.2 (or later)

When using mobile rules to target devices running Safari version 14.0.2 (or later) on macOS, due to a known issue involving Apple's user agents and DeviceAtlas, [!DNL Target] incorrectly identifies Safari on Mac and iPad devices. This issue will be addressed in the future.

## Training video: Creating Audiences

This video includes information about using audience categories.

* Create audiences 
* Define audience categories

>[!VIDEO](https://video.tv.adobe.com/v/17392)
