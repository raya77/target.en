---
keywords: responsive;mobile viewports;viewport;devices;mobile;responsive web design;rwd
description: Mobile viewports help you see how your Adobe Target activities look on Screens of various sizes. Find a list of popular device viewport sizes and resolutions.
title: How Do I Use Mobile Viewports for Responsive Experiences?
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
---
# Mobile viewports for responsive experiences

Mobile viewports let you preview your [!DNL Adobe Target] activities on screens of various sizes.

The mobile viewport preview feature is designed for responsive sites that render well on various devices, windows, and screen sizes. Responsive sites automatically adjust and adapt to any screen size, including desktops, laptops, tablets, or mobile phones.

>[!NOTE]
>
> * Use mobile viewports if your site is responsive and the same elements in your desktop page are used on your mobile page in a different configuration. If you have a separate mobile site with a separate structure, such as `m.mysite.com`, use a [multipage activity](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) instead.
>
>* Mobile viewports are not available if overlapped by a redirect offer overlay.

A viewport is defined by the size of the rectangle filled by a web page on your screen. The viewport is the size of the browser window, minus the scroll bars and toolbars. Browsers use "CSS pixels." For many devices, such as those with retina screens, the viewport is smaller than the advertised device resolution.

Below are the viewports and resolutions for popular devices. Remember to use the viewport size in [!DNL Target]. 

>[!NOTE]
>
>Various websites list viewport sizes for popular devices. For example, see [https://viewportsizer.com/devices/](https://viewportsizer.com/devices/). Consult the device maker's website for the most accurate, up-to-date information.

|  Device  | Viewport Size (width x height)  | Device Resolution (width x height) |
|---|---|---|
|iPhone 12|390 x 844|1170 x 2532|
|iPhone 12 Mini|360 x 780|1080 x 2340|
|iPhone 12 Pro|390 x 844|1170 x 2532|
|iPhone 12 Pro Max|428 x 926|1248 x 2778|
|  iPhone SE | 214 x 379 | 640 x 1136 |
|  iPhone 11 Pro Max | 414 x 896 | 1242 x 2688 |
|  iPhone 11 Xs Max | 414 x 896 | 1242 x 2688 |
|  iPhone 11 | 414 x 896 | 828 x 1792 |
|  iPhone 11 Xr | 414 x 896 | 828 x 1792 |
|  iPhone 11 Pro | 375 x 812 | 1125 x 2436 |
|  iPhone 11 X | 375 x 812 | 1125 x 2436 |
|  iPhone 11 Xs | 375 x 812 | 1125 x 2436 |
|  iPhone X  | 375 x 812  | 1125 x 2436 |
|  iPhone 8 Plus  | 414 x 736  | 1080 x 1920  |
|  iPhone 8  | 375 x 667  | 750 x 1334  |
|  iPhone 7 Plus  | 414 x 736  | 1080 x 1920  |
|  iPhone 7  | 375 x 667  | 750 x 1334  |
|  iPhone 6s Plus  | 414 x 736  | 1080 x 1920  |
|  iPhone 6s  | 375 x 667  | 750 x 1334  |
|  iPhone 6 Plus  | 414 x 736  | 1080 x 1920  |
|  iPhone 6  | 375 x 667  | 750 x 1334  |
|  iPad Pro  | 1024 x 1366  | 2048 x 2732  |
|  iPad Third & Fourth Generation  | 768 x 1024  | 1536 x 2048  |
|  iPad Air 1 & 2  | 768 x 1024  | 1536 x 2048  |
|  iPad Mini  | 768 x 1024  | 768 x 1024  |
|  iPad Mini 2 & 3  | 768 x 1024  | 1536 x 2048  |
|  Nexus 6P  | 411 x 731  | 1440 x 2560  |
|  Nexus 5X  | 411 x 731  | 1080 x 1920  |
|  Google Pixel  | 411 x 731  | 1080 x 1920  |
|  Google Pixel XL  | 411 x 731  | 1440 x 2560  |
|  Google Pixel 2  | 411 x 731  | 1080 x 1920  |
|  Google Pixel 2 XL  | 411 x 823  | 1440 x 2880  |
|  Samsung Galaxy Note 5  | 480 x 853  | 1440 x 2560  |
|  LG G5  | 360w x 640  | 1440 x 2560  |
|  LG G4  | 360w x 640  | 1440 x 2560  |
|  LG G3  | 360w x 640  | 1440 x 2560  |
|  One Plus 3  | 480 x 853  | 1080 x 1920  |
|  Samsung Galaxy S9  | 360 x 740  | 1440 x 2960  |
|  Samsung Galaxy S9+  | 360 x 740  | 1440 x 2960  |
|  Samsung Galaxy S8  | 360 x 740  | 1440 x 2960  |
|  Samsung Galaxy S8+  | 360 x 740  | 1440 x 2960  |
|  Samsung Galaxy S7  | 360 x 640  | 1440 x 2560  |
|  Samsung Galaxy S7 Edge  | 360 x 640  | 1440 x 2560  |
|  Nexus 7 (2013)  | 600 x 960  | 1200 x 1920  |
|  Nexus 9  | 768 x 1024  | 1536 x 2048  |
|  Samsung Galaxy Tab 10  | 800 x 1280  | 800 x 1280  |
|  Chromebook Pixel  | 1280 x 850  | 2560 x 1700  |

To deliver an activity to visitors on a particular device, choose the appropriate audience for that device in the activity diagram. Use the Mobile Web Composer to edit the page in the activity for that device. To run an activity across your entire digital experience to ensure it looks good across all devices, don't apply targeting. Instead, use mobile viewports to preview the activity on each screen size.

For responsive sites, typically your site is designed to open in a different view when accessed by a device with a specific screen size. Those screen sizes that trigger the new views are known as CSS breakpoints. CSS breakpoints are points where website content responds depending on device width to display the optimal layout to visitors. CSS breakpoints are also called [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries). 

Save your CSS breakpoints in [!DNL Target] so you can preview your experiences for each view you define. Each of these experiences displays in a mobile viewport in the [!DNL Target] interface. Open the view for each screen size by clicking that viewport along the top of the display.

If your site is not responsive, use the Mobile Web Composer to view a site if your activity is targeted to a specific device.

>[!IMPORTANT]
>
>You can edit an experience from within mobile viewports. However, these changes apply to all viewports and devices, not just the viewport that you're working in. Similarly, editing an experience in the normal desktop view changes the page for all screen sizes, not just the desktop view. Currently, [!DNL Target] does not support viewport-specific page changes.

## Mobile viewport configuration {#task_B4B161499DC0470584ED922A4D20FCAB}

Configure mobile viewports you want to make available while creating your experiences.

1. Click **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**.
1. In the **[!UICONTROL Mobile viewports configuration]** section, click **[!UICONTROL Add]**.

   ![Add viewport](/help/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   Or

   To change the configuration of an existing mobile viewport, select that viewport, then click the [!UICONTROL Edit] (pencil) icon.

1. Type a name for the mobile viewport.

   Give your mobile viewport a descriptive name that is easy to recognize. The name can be up to 36 characters long.

1. Specify the screen size of the mobile device, both width and height.

   The width can be 150 to 968 pixels. The height can be 150 to 1280 pixels.
   
1. (Optional) Select the operating system of the device.

   Options:

   * Android 
   * iOS 
   * Windows 
   * Symbian 
   * Blackberry

   If you use the [Enhanced Experience Composer](/help/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) and choose an operating system, [!DNL Target] emulates that device when you view the page. For example, if there is a different look and feel for Android than for iOS on your responsive site, [!DNL Target] mimics that behavior.

1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>If you attempt to delete a mobile viewport that is in use, the following message displays: "This viewport is currently associated to one or multiple activities. You need to remove the viewport from those activities before being able to delete it."

## Create a responsive experience {#task_D6332438B5EE48CCA8AF199270F1CAEF}

Add mobile viewports to your [!DNL Target] activities to create responsive experiences for mobile screens.

1. Create the [desired activity](/help/c-activities/activities.md).
1. In the [!UICONTROL Visual Experience Composer] (VEC), click the **[!UICONTROL Settings]** gear icon, then select **[!UICONTROL Add Mobile Viewports]**.

   ![Add Mobile Viewports option](/help/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. Click the **[!UICONTROL Devices]** icon, then enable each device that should have a mobile viewport.

   ![Enable mobile viewports](/help/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   The mobile viewports are listed from smallest to largest according to width.

1. Edit the mobile viewports as desired.

   Any changes you make to the experience are applied to the experience on all devices. For example, you change the text in a heading.

   Mouse over the name of a viewport to see the viewport's size.

   ![iPhone 11 Pro Max responsive experience](/help/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. If desired, toggle between portrait and landscape modes by clicking the desired orientation icon.

   ![Orientation options](/help/c-experiences/c-visual-experience-composer/assets/orientation.png)

## Training videos 

The following videos contain more information about the concepts discussed in this article.

### Visual Experience Composer (2 of 2) (7:29) ![Overview badge](/help/assets/overview.png)

The following demo video includes information about using the Visual Experience composer to work with mobile viewports:

* Rename and duplicate an experience
* Create a redirect experience
* Target an activity to a single URL or a group of URLs
* Create a multi-page activity
* Preview and build experience for responsive websites
* Use overlays to highlight types of elements

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Account Preferences in Adobe Target ![Overview badge](/help/assets/overview.png)

This video includes information about setting up mobile viewports, beginning at 4:40 in the video.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
