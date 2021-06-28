---
keywords: Targeting;visual experience composer;vec;troubleshoot visual experience composer;troubleshooting;tls;tls 1.2
description: Learn how to troubleshoot problems that sometimes occur in the Adobe [!DNL Target] Visual Experience Composer (VEC) under certain conditions.
title: How Do I Troubleshoot Issues Related to the Visual Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
---
# Troubleshooting issues related to the Visual Experience Composer

Display problems sometimes occur in the [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) under certain conditions.

## When I open my website in the Visual Experience Composer, the [!DNL Target] libraries do not load. (VEC only) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

Target adds two parameters (`mboxEdit=1` and `mboxDisable=1`) while opening the website in the Visual Experience Composer.

If your website (specially Single Page Apps), trims our parameters or actually removes them while navigating from one page to another (without a page reload) the Target functionality breaks and the Target libraries do not load. 
To avoid this problem, ensure that you do not trim or remove these two parameters.  

## My page won't open in the EEC, or loads slowly. Activities or experiences load slowly in the VEC. (VEC only) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Several issues can affect page performance in the Target experience composers. Some common issues include:

* You do not have an mbox on the page. 
* Your site uses proxy blocking, which does not allow the page to be opened in either experience composer. 
* Your site doesn't allow itself to be opened in an iFrame.

If issues occur in the Enhanced Experience Composer, try turning off the Enhanced Experience Composer and use the Visual Experience Composer instead.

To disable the Enhanced Experience Composer, go to **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** and turn off the **[!UICONTROL Enable Enhanced Experience Composer]** option.

Some users see the following error message in the console:

![Console error message](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

If neither the Visual Experience Composer nor the Enhanced Experience Composer works, use a browser extension like Requestly (Chrome or Firefox) or Modify Response Headers (Firefox) that can overwrite the X-Frames header options for your site and allow them to be loaded in iFrames, enabling the VEC. If you are unable to use browser extensions, use the Form Composer.

>[!NOTE]
>
>In addition to the following information, you can use the [Adobe Target VEC Helper browser extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) for Google Chrome.


>[!NOTE]
>
>These plugins should be used only in the context of VEC editing.
>
>For the Requestly extension, whenever there is a need to remove headers, you should do either of following:
>
>* Add URL rules for the URL that you want to open in the VEC so that headers are removed for those URLs only.
>
>* Enable the rule when you are editing in the VEC and disable the rule when you are not using the VEC.
>
>For the Modify Response Header extension (Firefox), because you can't add a URL rule, you must do the following:
>
>* Enable the rule when you are editing in the VEC and disable the rule when you are not using the VEC.

**To use the Requestly extension on Chrome or Firefox:**

1. Turn off the Enhanced Experienced Composer. 
1. Install the Requestly browser extension on Chrome or Firefox. 
1. Open the extension and configure it using the following: 
1. Select **[!UICONTROL Modify headers]**. 
1. Enter the following:

    * Rule name 
    * Modification rules

        * Toggle **[!UICONTROL Add]** to **[!UICONTROL Remove]**. 
        * Toggle **[!UICONTROL Request]** to **[!UICONTROL Response]**. 
        * Enter "X-Frame-Options" as the header name. 
        * Repeat previous steps and enter "x-frame-options" as the header name.

          >[!NOTE]
          >
          >Headers that are manipulated via Requestly are case sensitive.

        * Change **[!UICONTROL Equals]** to **[!UICONTROL Contains]** as the condition for the source URL and enter the URL of the activity that you are trying to load in the VEC.

      ![](assets/chrome_extension.png)

1. Click **[!UICONTROL Save]**.

   ![](assets/requestly.png)

   You should now be able to load the page quickly with the Visual Experience Composer.

**To use the Modify Response Headers extension on Firefox:**

1. Install the Modify Response Headers on Firefox and restart the browser. 
1. From your Firefox extensions, select the Modify Response Headers extension. 
1. Click **[!UICONTROL Preferences]**. 
1. Select **[!UICONTROL Filter]** from the Action drop down. 
1. In the Header Name field, enter: **[!UICONTROL X-Frame-Options]**. 
1. Repeat Steps 4 and 5 to add a filter with **[!UICONTROL x-frame-options]**. 
1. Click **[!UICONTROL Add]**. 
1. Click **[!UICONTROL Start]**.

![](assets/firefox_extension.png)

After setting up an extension, open Target. Your pages should now load in the Visual Experience Composer, even if the Enhanced Experience Composer is disabled.

## My page does not display in the VEC (VEC only) {#section_87B3BEA4B6174CFDA6C9A69A1A051FA1}

* The browser is not supported. 
* The browser is blocking a non-secure page on a secure site.

  Click the icon to the left of the URL in the browser address bar and click **[!UICONTROL Disable protection on this page]** 
* You entered an invalid URL. 
* You have not entered a default URL in your account setup page.

Ensure that this setting is enabled, then download and update at.js on your website.

## The VEC appears broken when I use browse mode. (VEC only) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

While using browse mode, if you access a URL that does not have target.js or contains a frame-buster header, the Visual Experience Composer appears broken. Due to browser security concerns, Target cannot access the URL you navigated to.
