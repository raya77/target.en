---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Discover why some websites might not open reliably in the Visual Experience Composer (VEC). The VEC Helper browser extension lets you load websites reliably within the VEC.
title: How Do I Use the Visual Experience Composer (VEC) Helper Extension?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
---
# Visual Experience Composer helper extension

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper browser extension for Google Chrome lets you load websites reliably within the VEC to rapidly author and QA web experiences.

>[!NOTE]
>
>The VEC Helper browser is a Chrome extension. This extension is not necessary when using Mozilla Firefox.

## Reasons why some websites might not open reliably in the VEC

* The website has strict security policies.
* The website is in an iframe.
* The at.js library is not yet implemented on the website.
* The customer's QA and/or stage site is not available to the outside world (the site is internal).
* You are using Google Chrome 80+ with enhanced SameSite cookie enforcement policies. For more information, see [How do the recently announced Google Chrome SameSite cookie enforcement policies impact the VEC and EEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

The VEC Helper browser extension for Chrome solves site-loading issues for which customers now rely on the [!DNL Target] [Enhanced Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md#eec) or third-party extensions, such as Requestly.

## Benefits of using the VEC Helper extension

* All iframe busting headers, such as X-Frame-Options and Content-Security-Policy, are implicitly removed from the website. There is no more need to create complicated Requestly rules.
* If a webpage does not yet contain the [!DNL Target] at.js JavaScript library, you can use the extension to inject the library so you can author experiences for the website. You can then create activities and QA them using preview links.

  Note that using the Enhanced Experience Composer (EEC), the extension does not inject at.js, but the SameSite Cookie functionality is still present. To inject at.js on the webpage, turn off the EEC.

* [Mobile viewports](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) are supported even without the [!UICONTROL Enhanced Experience Composer] (EEC).
* Customers new to [!DNL Target] can use the extension to experiment with [!DNL Target] even if their IT developers have not yet implemented [!DNL Target] on their websites.
* Partners servicing multiple customers' websites and [!DNL Target] accounts now have one simple mechanism to support VEC loading, instead of managing multiple rules in third-party tools.

## Obtain and install the VEC Helper browser extension

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Click **[!UICONTROL Add to Chrome > Add Extension]**.
1. Open the VEC in [!DNL Target].
1. To use the extension, click the VEC Helper browser extension icon ( ![VEC Helper icon](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) in your Chrome browser's toolbar while in the VEC or [QA Mode](/help/c-activities/c-activity-qa/activity-qa.md).
1. (Conditional) Slide the **[!UICONTROL Inject Target Libraries]** toggle to the "on" position if the webpage does not yet contain the [!DNL Target] at.js JavaScript library.

   The following illustration shows the VEC Helper with the [!UICONTROL Inject Target Libraries] setting enabled:

   ![VEC helper 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   The following illustration shows the VEC Helper asking you whether you want it to inject [!DNL Target] libraries in the page to enable authoring: 

   ![VEC helper 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Conditional) Slide the **[!UICONTROL Cookies]** toggle to the "on" position to automatically add the SameSite=None attribute browser fix, then specify the cookie name and domain.

   ![Cookies toggle in the VEC helper extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   The following links provide additional information:

   * For more information on the SameSite=None attribute browser fix, see "How do the recently announced Google Chrome SameSite cookie enforcement policies impact the VEC and EEC?" in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * The cookie name is "mbox" and the cookie domain is the second and top levels of the domains from which you serve the mbox. Because it is served from your company's domain, the cookie is a first party cookie. Example: `mycompany.com`. For more information, see [Adobe Target Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) in the *Experience Cloud Interface User Guide*.

## Notes

* Your implementation must use the [!DNL Target] at.js library. You cannot use an mbox.js implementation with the extension.
* The [!UICONTROL Inject Target libraries] flag in the extension is OFF by default. You can enable this flag if you want to use the VEC on a site that has not yet been implemented for [!DNL Target].

  This flag is a global setting. The flag is enabled or disabled for all websites opened in the VEC. So, for example, if you set this flag to "on" and open a website that is already implemented with at.js, you receive a message informing you that at.js is already loaded. Adobe anticipates that most customers already have at.js implemented on their pages and use the default setting of "off."

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* When using the extension to inject at.js while in [QA Mode](/help/c-activities/c-activity-qa/activity-qa.md), you must have another Chrome tab open. This Chrome tab must be authenticated to the same [!DNL Adobe Experience Cloud] Organization in which you created the activity.
* The following messages help keep you informed:

  * If you attempt to load a website using the VEC that fails to load, a message displays suggesting that you install the VEC Helper browser extension.
  * If at.js is not yet implemented on the website, a message displays in the VEC suggesting that you install the extension.
  * If the extension is enabled and is powering the loading, messages display when the extension injects the at.js library (if necessary) or helps open the website reliably within the VEC.
