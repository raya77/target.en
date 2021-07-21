---
keywords: Targeting;visual experience composer;whitelist;white list;allowlist;allow list;enhanced visual experience composer;vec;troubleshoot visual experience composer;troubleshooting;eec;enhanced experience composer;tls;tls 1.2
description: Learn how to troubleshoot problems that sometimes occur in the Adobe [!DNL Target] Visual Experience Composer (VEC) and the Enhanced Experience Composer (EEC) under certain conditions.
title: How Do I Troubleshoot Issues Related to the Visual Experience Composer and Enhanced Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
---
# Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer

Display problems and other issues sometimes occur in the [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) and the [!UICONTROL Enhanced Experience Composer] (EEC) under certain conditions.

## How do the Google Chrome SameSite cookie enforcement policies impact the VEC and EEC? {#samesite}

Be aware of the changes that impact the VEC and EEC when using the following Chrome releases: 

**Chrome 94 (September 21, 2021)**: With the impending changes planned for the Chrome 94 release (September 21, 2021), the following change impacts all users with Chrome 94+ browser versions:

* The command-line flag `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` will be removed.

**Chrome 91 (May 25, 2021)**: With the changes implemented for the Chrome 91 release (May 25, 2021), the following change impacts all users with Chrome 91+ browser versions:

* The flags `#same-site-by-default-cookies` and `#cookies-without-same-site-must-be-secure` have been removed from `chrome://flags`. This behavior is now enabled by default.

**Chrome 80 (August 2020)**: With the changes implemented in August 2020, all users with Chrome 80+ browser versions:

* Will *not* be able to use the VEC (with or without the VEC Helper extension installed and enabled) in password-protected pages of their sites. Your site login cookies are considered a 3rd-party cookie and are sent with the login request. The only exception is when your site login cookie already has the SameSite parameter set to “none.”
* Will *not* be able to download [!DNL Target] libraries while editing an activity (when these aren’t already on the site). This is because the download call is made from the customer domain towards a secured Adobe domain and is rejected as unauthenticated.
* The EEC will *not* function for all users because it is not able to set the SameSite attribute for cookies on `adobemc.com domain`. Without this attribute, the browser rejects these cookies, causing the EEC to fail.

### Determine which cookies are blocked

To check which cookies are blocked because of the SameSite cookie enforcement policies, use the Developer Tools in Chrome.

1. To access the Developer Tools, while viewing the VEC in Chrome, click the **[!UICONTROL ellipsis]** icon at the top-right corner of Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**.
1. Click the **[!UICONTROL Network]** tab > then look for blocked cookies.

   >[!NOTE]
   >
   >Use the **[!UICONTROL Has blocked cookies]** checkbox to make finding blocked cookies easier. 

   The following illustration shows a blocked cookie:

   ![Developer Tools > Network tab showing a blocked cookie](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### Google VEC Helper extension

Adobe has submitted an updated VEC Helper extension to the Google Chrome Store. This extension overwrites the cookie attributes to set the `SameSite="none"` attribute, when needed. The [updated extension can be found here](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en). For more information about installing and using the VEC Helper Extension, see [Visual Experience Composer helper extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

For your own site cookies, you must specify the cookies by name.

>[!NOTE]
>
>This approach is suitable only when all the cookies are set in a single domain. The VEC helper does not allow [!DNL Target] to specify cookies for more than one domain.

Toggle the [!UICONTROL Cookie] slider to the on position, then specify the cookie by name and the cookie domain. The cookie name is "mbox" and the cookie domain is the second and top levels of the domains from which you serve the mbox. Because it is served from your company's domain, the cookie is a first party cookie. Example: `mycompany.com`. For more information, see [Adobe Target Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) in the *Experience Cloud Interface User Guide*.

![Cookies toggle in the VEC helper extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### Alternatives and workarounds

Use one of the following options to ensure that your VEC and EEC continue to work as expected:

* Download and use the updated [VEC Helper extension](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en).
* Use the Mozilla Firefox browser. Firefox is not yet enforcing this policy.
* Use the following flags to run Google Chrome from the command line until September 21, 2021. After September 21, your website will no longer work in the VEC. If you update to Chrome 94, you must manually generate cookies with `SameSite=none` and `Secure` on your websites.

  ```
  --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
  ```

## Does [!DNL Target] support multi-level iframes?

[!DNL Target] does not support multi-level iframes. If your website loads an iframe that has a child iframe, at.js interacts with the parent iframe only. [!DNL Target] libraries do not interact with the child iframe.

As a workaround, you can add a page in the experience with the URL of the child iframe.

## When I try to edit a page, all I see is a spinner instead of my page. (VEC and EEC) {#section_313001039F79446DB28C70D932AF5F58}

This situation can happen if the URL contains a # character. To fix the issue, switch into Browse mode in the Visual Experience Composer, and then switch back to Compose mode. The spinner should go away and the page should load.

## Content Security Policy (CSP) headers block the [!DNL Target] libraries on my website. (VEC and EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

If your website's CSP headers block Target libraries, then loads the website but prevents editing, ensure that the Target libraries are not blocked.

>[!NOTE]
>
>In addition to the following information, you can use the [Adobe Target VEC Helper browser extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) for Google Chrome.

![](assets/cps_headers.png)

As a workaround, you can configure a Requestly rule to remove CSP headers, as shown below:

![](assets/cps_headers_2.png)

You can configure a similar Requestly rule for any header that causes a resource to not load inside the VEC.

For Requestly, whenever there is a need to remove headers, you should do either of following:

* Add URL rules for the URL that you want to open in the VEC so that headers are removed for those URLs only. 
* Enable the rule when you are editing in the VEC and disable the rule when you are not using the VEC.

## The VEC or EEC appears broken or does not initialize when re-editing a saved activity. (VEC and EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

If the website has changed outside of the Visual Experience Composer after the experience was defined, selectors on which actions were taken earlier cannot be found when the activity is opened for re-editing. The page appears broken, and no warning displays.

## The VEC or EEC does not show my rotating banners and other content containing JavaScript. (VEC and EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

By default, the Visual Experience Composer blocks JavaScript elements. You can work with these elements if you disable JavaScript in the Visual Experience Composer settings. Depending on how the site is set up, some items might continue to display incorrectly or to remain unavailable.

## When I change one element on the page, multiple elements change. (VEC and EEC) {#section_309188ACF34942989BE473F63C5710AF}

If the same DOM element ID is used on multiple elements on the page, changing one of those elements changes all elements with that ID. To prevent this from happening, an ID should be used only once on each page. This practice is a standard HTML best practice. For more information, see [Page Modification Scenarios](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## I can't edit experiences for an iFrame-busting site. (VEC and EEC) {#section_9FE266B964314F2EB75604B4D7047200}

This issue can be addressed by enabling the Enhanced Experience Composer. Click **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]**, then select the check box that enables the Enhanced Experience Composer. The Enhanced Experience Composer uses an Adobe-managed proxy to load your page for editing. This proxy allows editing on iFrame-busting sites and allows editing on sites and pages where you have not yet added Adobe Target code. The activities do not deliver to the site until the code has been added. Some sites may not load via the Enhanced Experience Composer, in which case you can uncheck this option to load the Visual Experience Composer via an iFrame.

>[!NOTE]
>
>Your locally hosted pages or pages that are not accessible outside your network are not accessible to the Adobe proxy server and cannot be opened in the EEC. These pages might include staging URLs, User Acceptance Testing (UAT) URLs, or locally hosted pages.

## I want to set up tests on pages that don't have the mbox/target implementation done yet. (VEC and EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

See "I can't edit experiences for an iFrame-bursting site" above.

## Bold and italic text styles with Edit Text/HTML or Change text/HTML do not show on my page. Sometimes the text disappears after applying these style changes. (VEC and EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

If you use **[!UICONTROL Edit Text/HTML]** in the Visual Experience Composer for A/B or Experience Targeting activities or **[!UICONTROL Change Text/HTML]** for Automated Personalization or Multivariate Test activities to make text bold or italic, those styles might not be applied on the page or the text disappears from the page in the Visual Experience Composer. This happens because of the way the rich-text editor applies these styles might interfere with the website markup.

If you see this issue:

1. Click the **[!UICONTROL HTML]** button in the rich-text editor to enter source editing mode. 
1. Find the styles text elements.

    * For bold text, change `<strong>` elements to `<b>`. 
    
    * For italic text, change `<em>` elements to `<i>`.

## For Automated Personalization activities, image swapping appears broken in the VEC or EEC. (VEC and EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

Adding an image offer to a location takes the full dimension of the original image space in the VEC or EEC. On delivery, the image is not expanded and is shown as it is, so there is no impact on delivery.
