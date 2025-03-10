---
keywords: targeting;a4t;geo;geotargeting;geotargeting accuracy;country;state;city;zip code;dma;mobile carrier;city codes;region codes;country codes;metro codes;profile scripts;geotargeting profile scripts;geotargeting mobile
description: Learn how to create audiences in [!DNL Adobe Target] to target users based on their geographical location.
title: Can I Target Visitors Based on Location?
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
---
# Geo

Use audiences in [!DNL Adobe Target] to target users based on their geographical location.

Geo location parameters let you target activities and experiences based on your visitors' geography. You can include or exclude visitors based on their country, state/province, city, zip/postal code, latitude, longitude, DMA, or mobile carrier. This data is sent with each [!DNL Target] request and is based on the visitor's IP address. Select these parameters just like any targeting values.

## Create an Audience with geo targeting {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**. 
1. Name the audience and add an optional description. 
1. Drag and drop **[!UICONTROL Geo]** into the audience builder pane.

1. Click **[!UICONTROL Select]**, then select one of the following options:

   * [!UICONTROL Country/Region] 
   * [!UICONTROL State] 
   * [!UICONTROL City] 
   * [!UICONTROL Zip Code] 
   * [!UICONTROL Longitude]
   * [!UICONTROL Latitude] 
   * [!UICONTROL DMA] 
   * [!UICONTROL Mobile Carrier]

   A visitor's IP address is passed with an mbox request, once per visit (session), to resolve geo targeting parameters for that visitor.

   For [!UICONTROL Mobile Carrier], [!DNL Target] uses the IP address registration data (who owns the block of IP addresses) to determine the appropriate mobile carrier using [Mobile Country Codes (MCC) and Mobile Network Codes MNC)](https://www.mcc-mnc.com).

1. Specify an operator and the appropriate value.
1. (Optional) Set up additional rules for the audience. 
1. Click **[!UICONTROL Done]**.

The following illustration shows an audience that targets users accessing the activity from a latitude greater than 44° and a longitude less than 22°.

![target_geo image](assets/target_geo.png)

## Accuracy {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

The accuracy of geo targeting depends on several factors. WiFi connections are more accurate than cellular networks. When the visitor is using a cellular data connection, the accuracy of the geo-lookup can be affected by location, the provider's data relationship with [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), and other factors. Cell tower-based network connections might be less accurate than wired or WiFi connections. Also, a visitor's IP address might be mapped to the visitor's ISP location, which might not be the same as the visitor's actual location. Some mobile geo-location issues can be solved using the [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

The following table shows the accuracy of IP-based geographical information from [DigitalEnvoy](https://www.digitalelement.com/solutions/) for wired or WiFi Internet connections. DigitalEnvoy provides the most accurate data in the industry. Global accuracy is more than 99.9 percent at the country level and is up to 97 percent accurate at a city level. Accuracy information does not apply to cell tower-based networks.

| Country | State | City | Region |
|--- |--- |--- |--- |
|US|99.99%|96%|94%|
|Canada|99.99%|96%|94%|
|Europe|99.99%|||
|UK|99.99%||87%|
|Germany|99.99%|95%|93%|
|Scandinavia|99%|Low 90s|Mid 80s|
|Spain|99.99%|Around 90%|Mid to high 90s|
|Asia|99%|Mid 90s|Low 90s|
|Japan|99.99%|Mid 90s|Low 90s|
|Australia|99.99%|94%|91%|

## Use geo-targeting in profile scripts {#section_92C93138542C4A94997E3F4BE3F5DA28}

You can use geo information for profile scripts.

For example, use:

* `profile.geolocation.country` 
* `profile.geolocation.state` 
* `profile.geolocation.city` 
* `profile.geolocation.zip` 
* `profile.geolocation.dma` 
* `profile.geolocation.domainName` 
* `profile.geolocation.ispName` 
* `profile.geolocation.connectionSpeed` 
* `profile.geolocation.mobileCarrier`

So, you can write a target expression called "From North America" with the following code:

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## Use geo-targeting values as tokens {#section_E7F7FDF62C3B4934A6565D04B24655F6}

You can use `profile.geolocation` values directly as tokens in offers, plugins, and so forth.

For example, use:

* `${profile.geolocation.country}` 
* `${profile.geolocation.state}` 
* `${profile.geolocation.city}` 
* `${profile.geolocation.zip}` 
* `${profile.geolocation.dma}` 
* `${profile.geolocation.domainName}` 
* `${profile.geolocation.ispName}` 
* `${profile.geolocation.connectionSpeed}` 
* `${profile.geolocation.mobileCarrier}` 
* `${profile.geolocation.latitude}` 
* `${profile.geolocation.longitude}`

## Geo-targeting FAQ {#section_DD308A53AF0F48FA8C81423580561FE7}

The following questions are frequently asked about geo-targeting:

### How do I specify latitude and longitude?

* The value for latitude and longitude should be a numeric value in degrees. 
* The value for latitude and longitude can have a maximum precision of five decimal places. 
* The value for latitude should be between -90 and 90. 
* The value for longitude should be between -180 and 180.

### How does geo-targeting work for mobile devices?

Most mobile device users access content via WiFi, which means [!DNL Target]'s IP-based geo targeting is as accurate as on a desktop. Cell tower-based connections might be less accurate because the visitor's IP address is based on the tower where the signal is being picked up. Some mobile geo-location issues can be solved using the [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

### How does geo feature handle visitors from AOL?

Due to the way AOL proxies its traffic, [!DNL Target] can only target them at a country level. For example, a campaign targeted to France successfully targets AOL users in France. But a campaign targeted to Paris does not successfully target AOL users in Paris. If your intent is to specifically target AOL users, you can set the region field to "aol." In fact, you can target US AOL users by specifying two targeting conditions: country exactly matches "united states" and region exactly matches "aol."

### What location granularity does geo-targeting provide?

* Country - global 
* State/province/region - global 
* City - global 
* Zip/postal code - US, Germany, Canada 
* DMA/ITV (UK) - US, UK 
* Mobile carrier - global

### How can I test my activities as if I'm a user coming from a different location?

* **at.js 1.*x***: You can override your IP address with an IP address from a different location and use the `mboxOverride.browserIp url` parameter. For example, if your company is in the UK, but your global campaign targets visitors in Auckland, New Zealand, use this style of URL assuming that `60.234.0.39` is an IP address in Auckland:

  `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

  Clear your cookies before doing testing the activity.

  >[!NOTE]
  >
  >`mboxOverride.browserIp` is supported in at.js 1.*x* only. This functionality is not supported in at.js 2.*x*.

* **at.js 2.*x***: To override your IP address with at.js 2.*x*, install a browser extension/plugin (such as X-Forwarded-For Header for Chrome or Firefox). This extension lets you pass the x-forwarded-for header in your page requests. 

### How are territories, such as Puerto Rico and Hong Kong, mapped into the geo-targeting structure?

Puerto Rico, Hong Kong, and other territories are treated as separate "Country" values.

### Does [!DNL Target] capture (and store) information such as Zip Code when activity is targeted with geo-location targeting capabilities?

No, [!DNL Target] uses geo data during the session only, then the data is discarded.

## Training video: Creating Audiences ![Tutorial badge](/help/main/assets/tutorial.png)

This video includes information about using audience categories.

* Create audiences 
* Define audience categories

>[!VIDEO](https://video.tv.adobe.com/v/17392)
