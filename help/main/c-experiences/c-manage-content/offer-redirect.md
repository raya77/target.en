---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: Learn how to create redirect offers in Adobe [!DNL Target] to cause a browser to redirect to a new page. 
title: How Do I Create Redirect Offers?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
---
# Create redirect offers

Redirect offers in [!DNL Adobe Target] cause a browser to redirect to a new page.

You might have two completely different pages to test instead of just changing pieces of content within a page. In this case, your A/B test compares page A vs. page B. Set up an A/B Test activities with two experiences: one pointing to the default page A, and the other redirecting to page B. The offer is configured to redirect the visitor to a different page.

>[!NOTE]
>
> * Redirect offers can be created on the [!UICONTROL Offers] > [!UICONTROL Code Offers] page or in the [Forms-Based Experience Composer](/help/main/c-experiences/form-experience-composer.md). You cannot create or apply redirect offers in the Visual Experience Composer (VEC). Content will be injected in the [!DNL Target] request locations, so these are most likely not appropriate for a global [!DNL Target] request.
>
>* You cannot use redirect offers in ajax mboxes (`mboxUpdate`).
>
>* For redirect offers in activities using A4T, your implementation must meet certain minimum requirements. In addition, there is important information that you need to know. For more information, see [Redirect Offers - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* For information about setting up an experience that redirects, see [Redirect to a URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

The redirect offer executes JavaScript code to redirect the browser. It uses the `window.location.replace();` method, so the page the visitor is redirected from is not stored in the browser history. This allows the visitor to still use the back button in their browser.

>[!NOTE]
>
>If you want to pass the referrer value of the landing page, it is recommended that you use an HTML offer rather than a redirect offer.

## Create a redirect offer from the Code Offers page

1. Click **[!UICONTROL Offers]**, then select the **[!UICONTROL Code Offers]** tab.

   ![Code Offers tab](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Click **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Create Redirect Offer dialog box](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Provide a descriptive name for the offer.

   A descriptive name helps you and others quickly find the offer in the Assets library.

1. Enter the URL for the unique content or destination you want to redirect to. This must be an absolute URL.

   >[!NOTE]
   >
   >Redirect offers result in an infinite loop if the redirect URL also qualifies the user for the same activity. You should ensure that the user does not re-qualify for the activity after being redirected.

1. Select the desired options to customize your redirect offer:

   * **Include all URL parameters:** Slide the toggle to enable this option if you want all the URL parameters present on the previous page to be propagated to the redirected page.

      For example, you want to redirect people directly from a men's page to a men's shirts category page. You also want the dynamic parameters in the URL to be passed because this is how you track if people reached your site via email, banner ad, search ad, or organically. By enabling this option, your redirect offer on page `https://www.mycompany.com/mens.html?emailId=123` will automatically become `https://www.mycompany.com/mensShirts.html?emailId=123` when all you entered in the URL box was `https://www.mycompany.com/mensShirts.html`. 

   * **Pass mbox session ID:** Required to redirect to a different domain. Slide the toggle to enable this option if you want the `sessionId` to automatically be included in the redirect. This is required only when you are testing clicks from an email or clicks from one domain to another. The `sessionId` matches the visitor's cookie so the visitor can continue to be tracked and the proper content is shown.

      If you use the 1st- & 3rd-party cookie setup, you do not need to pass the mbox session ID when crossing domains. It is persistent on the 3rd-party cookie, so it is not necessary in the URL.

1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>Ask your Implementation Consultant before launching these tests.

## Create a redirect offer using the Form-Based Experience Composer

1. While creating an activity using the [Form-Based Experience Composer](/help/main/c-experiences/form-experience-composer.md), select the location to display the **[!UICONTROL Content]** section.

   ![Content section in Form-Based Experience Composer](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Click the **[!UICONTROL Default Content]** drop-down list, then click **[!UICONTROL Change Redirect Offer]**.

   ![Change Redirect Offer option](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Click **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Create Redirect Offer dialog box](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Provide a descriptive name for the offer.

   A descriptive name helps you and others quickly find the offer in the Assets library.

1. Enter the URL for the unique content or destination you want to redirect to. This must be an absolute URL.

   >[!NOTE]
   >
   >Redirect offers result in an infinite loop if the redirect URL also qualifies the user for the same activity. You should ensure that the user does not re-qualify for the activity after being redirected.

1. Select the desired options to customize your redirect offer:

   * **Include all URL parameters:** Slide the toggle to enable this option if you want all the URL parameters present on the previous page to be propagated to the redirected page.

      For example, you want to redirect people directly from a men's page to a men's shirts category page. You also want the dynamic parameters in the URL to be passed because this is how you track if people reached your site via email, banner ad, search ad, or organically. By enabling this option, your redirect offer on page `https://www.mycompany.com/mens.html?emailId=123` will automatically become `https://www.mycompany.com/mensShirts.html?emailId=123` when all you entered in the URL box was `https://www.mycompany.com/mensShirts.html`. 

   * **Pass mbox session ID:** Required to redirect to a different domain. Slide the toggle to enable this option if you want the `sessionId` to automatically be included in the redirect. This is required only when you are testing clicks from an email or clicks from one domain to another. The `sessionId` matches the visitor's cookie so the visitor can continue to be tracked and the proper content is shown.

      If you use the 1st- & 3rd-party cookie setup, you do not need to pass the mbox session ID when crossing domains. It is persistent on the 3rd-party cookie, so it is not necessary in the URL.

1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>Ask your Implementation Consultant before launching these tests.

## Use redirect offers in activities

You must apply redirect offers using the [!UICONTROL Form-Based Experience Composer]. You cannot currently apply redirect offers using the VEC.

The [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] is a non-visual experience and offer creation interface that’s useful in creating experiences for use in [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP), and [!UICONTROL Recommendations] activities when the visual experience composer is not available or practical for use. For example, you might use the [!UICONTROL Form-Based Experience Composer] to create experiences that use redirect offers.

1. Create or edit an activity in the [!UICONTROL Form-Based Experience Composer].

   See [Form-Based Experience Composer](/help/main/c-experiences/form-experience-composer.md) for detailed step-by-step instructions.

1. Specify the desired location and add any audience refinements as necessary.

1. Click the drop-down list in the **[!UICONTROL Content]** section, then click **[!UICONTROL Change Redirect Offer]**.

   ![Change Redirect Offer option](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Select the desired redirect offer from the [!UICONTROL Select Remote Offer] dialog box, then click **[!UICONTROL Done]**.

1. Finish configuring the activity.

## Training video: Form-based Composer ![Tutorial badge](/help/main/assets/tutorial.png)

This video provides a demo of the form-based composer, which you can use to create redirect offers.

* Create an activity using the Form-Based Experience Composer 
* Understand when to use Form-Based Experience Composer vs. the Visual Experience Composer 
* Use refinements to target a location

>[!VIDEO](https://video.tv.adobe.com/v/17390)
