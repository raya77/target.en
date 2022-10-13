---
kewords: redirect;redirect url;send to different page
description: Learn how to use the Redirect to URL option in Adobe [!DNL Target] when you want to send the visitor to a different page rather than showing content on the same page.
title: Can I Redirect a Page to a Different URL?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
---
# Redirect to a URL

Use the [!UICONTROL Redirect to URL] option in [!DNL Adobe Target] when you want to send the visitor to a different page rather than showing content on the same page.

 You might have two completely different pages to test instead of just changing pieces of content within a page. In this case, your A/B test compares page A vs. page B. Set up an A/B test campaign with two experiences: one pointing to the default page A, and the other redirecting to page B. In the Experience Action menu, located by clicking the letter label for the experience, choose **[!UICONTROL Redirect to URL]** and specify the URL of page B. The offer is configured to redirect the visitor to a different page.

The redirect offer executes JavaScript code to redirect the browser. It uses the `window.location.replace();`method, so the page the visitor is redirected from does not get stored in the browser history. This allows the visitor to still use the back button in their browser.

Redirect offers have a few limitations:

* For redirect offers in activities using A4T, your implementation must meet certain minimum requirements. In addition, there is important information that you need to know. For more information, see [Redirect Offers - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905). 
* When using the form-based Experience Composer, redirect offers should not be used in mboxes that are part of the page. A redirect offer should only be used from a script tag that is part of the HTML `<head>`. You should always use auto-create and set the redirect offer for the global mbox.

>[!NOTE]
>
>If you want to pass the referrer value of the landing page, it is recommended that you use an HTML offer rather than a redirect offer.

To create a redirect offer: 

1. Create an experience.
1. Hover over an experience with your mouse, then click the Redirect to URL icon (![icon_redirect_url image](assets/icon_redirect_url.png)).

   ![exp_actions image](assets/exp_actions.png)

1. Type the URL.
1. If desired, select the option to include current query parameters.

   If this option is selected, anything after the ? in the visitor's URL is appended to the redirect URL at the time of redirect.

   This option is selected by default. 
1. (Optional) Create additional rules.

   Additional rules can be based on any of the following:

   * URL 
   * Domain 
   * Path 
   * Hash (#) Fragment 
   * Query 
   * mbox Parameter

   Additional rules can be joined to the Activity URL with AND or OR. All rules you add are evaluated against each other with AND.

## Known issues

* Redirect activities in at.js implementations might cause the preview URL to enter into a loop (the offer is delivered repeatedly). You can use [QA Mode](/help/main/c-activities/c-activity-qa/activity-qa.md) instead to perform Preview and QA. This issue does not impact the actual delivery of the offer. (TGT-23019)
