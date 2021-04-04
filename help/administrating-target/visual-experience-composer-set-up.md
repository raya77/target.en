---
keywords: visual experience composer;vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css selectors
description: Learn how to configure the Adobe Target Visual Experience Composer (VEC) by specifying its general settings, mobile viewport configuration, and CSS selectors.
title: How Do I Configure the Visual Experience Composer (VEC)?
feature: Administration & Configuration
role: Administrator
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
---
# Configure the Visual Experience Composer

Configure the [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) by specifying its general settings, mobile viewport configuration, and CSS selectors.

To access the [!UICONTROL Visual Experience Composer] configuration page, click **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer].**

>[!NOTE]
>
>Be aware that settings on this page apply to the entire [!DNL Target] account. 

![Visual Experience Composer configuration page](/help/administrating-target/assets/vec.png)

## General Settings

You can specify general settings to the Visual Experience Composer.

![General Settings section](/help/administrating-target/assets/general-settings.png)

The following settings are available:

### Default URL

Set the default URL used by the [!UICONTROL Visual Experience Composer]. This is the default page, such as your home page, used whenever you set up an experience for each new activity. If you do not set a default URL, you must enter a URL for each activity when you create it.

### Enable Enhanced Experience Composer {#eec}

Allows editing on iFrame-busting sites and sites with mixed content. Some sites might not be compatible with the enhanced version. Deselect this option to revert to the original [!UICONTROL Visual Experience Composer]. Activity delivery on sites is not affected by this choice.

For more information, see [Troubleshooting the Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

You can also enable the [!UICONTROL Enhanced Experience Composer] at the activity level.

### Load Mixed Content

Enable mixed content while opening a website using the [!UICONTROL Enhanced Experience Composer] (EEC). Enabling this option avoids the extra overhead of loading static resources via [!DNL Target] proxy servers.

This option is helpful if, for example:

* Your Content Security Policy (CSP) headers allow loading mixed content without the use of proxy servers with the EEC enabled.
* Your HTTP website faces increased load time in the EEC, wherein JavaScript, images, and so forth take longer to load via proxy.

### Generate experience snapshots in the activity flow diagram

Enabling experience snapshots generates thumbnails for your experiences in the activity workflow diagram. Disabling snapshots might result in faster performance for some users.

## ![Premium badge](/help/assets/premium.png) Mobile Viewport Configuration

You can add devices to use when previewing experiences. Each device has an associated audience.

![Mobile Viewport Configuration section](/help/administrating-target/assets/mobile-viewport-configuration.png)

Click **[!UICONTROL Add]**, specify a descriptive name for the mobile viewport, specify the width and height, select the desired operating system, then click [!UICONTROL Save].

For information about how to add a mobile viewport, see [Mobile Viewport Configuration](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## CSS Selectors {#css}

Specify how [!DNL Target] generates CSS selectors.

![CSS Selectors section](/help/administrating-target/assets/css-selectors.png)

These options help [!DNL Target] understand your site's structure to generate better CSS selectors for content delivery. By default, [!DNL Target] generates selectors based on element IDs on the page. If your site uses few IDs, or duplicates IDs on the same page, then using classes might be a better option.

You can choose one or both of the following options:

### Use element IDs

Deselect this option if the same ID is used for multiple elements or if element ID might change on page load.

### Use element classes

By default, [!DNL Target] only uses element IDs. However, if your page is designed to use classes to identify elements, such as a page built with [!DNL Adobe Experience Manager], you should also select [!UICONTROL Use element classes].

>[!NOTE]
>
>Although everything has been done to assure accuracy, be aware that using classes can result in errors. If you do not select either option, accuracy is also affected. The order of accuracy is IDs > classes > neither option. Always be sure to test your page to make sure the selectors are correct.

You can override this setting per activity (click the [!UICONTROL Settings] gear icon, then select [!UICONTROL CSS Selectors]). This is especially useful if you have multiple sites that are configured differently.

>[!NOTE]
>
>Overriding the setting per activity is not available in [!UICONTROL Automated Personalization] and [!UICONTROL Multivariate Testing] activities.  See [Element Selectors Used in the Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) for additional information about selectors.

## Training video: Account Preferences (7:33) ![Overview badge](/help/assets/overview.png)

This video includes information about account preferences.

* Describe the account settings available in [!DNL Target Standard]

>[!NOTE]
>
>The [!DNL Target] [!UICONTROL Administration] menu UI (formerly [!UICONTROL Setup]) has been redesigned to provide improved performance, reduce the maintenance time required when releasing new features, and to improve the user experience across the product. The information in the following video is generally correct; however, options might be in slightly different locations. Updated videos will be posted soon.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
