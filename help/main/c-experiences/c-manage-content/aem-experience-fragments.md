---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: Learn how to use [!DNL Adobe Experience Manager] experience fragments in [!DNL Adobe Target] activities.
title: How Do I Use [!DNL Adobe Experience Manager] (AEM) Experience Fragments?
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
---
# AEM experience fragments

Use experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an [!DNL Adobe Experience Manager] (AEM) customer. For more information, see [Requirements](#section_AE6F0971E1574B3AA324003599B96E5A) below.

Using experience fragments created in [!DNL AEM] in [!DNL Target] activities lets you combine the ease-of-use and power of [!DNL AEM] with powerful Artificial Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

[!DNL AEM] brings together all of your content and assets in a central location to fuel your personalization strategy. [!DNL AEM] lets you easily create content for desktops, tablets, and mobile devices in one location without writing code. There’s no need to create pages for every device. [!DNL AEM] automatically adjusts each experience using your content.

[!DNL Target] lets you deliver personalized experiences at scale based on a combination of rules-based and AI-driven machine learning approaches that incorporate behavioral, contextual, and offline variables. With [!DNL Target], you can easily set up and run [A/B Test](/help/main/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Experience fragments represent a huge step forward to link the content/experience creators and managers to the optimization and personalization professionals who are driving business outcomes using [!DNL Target].

## Requirements {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within [!DNL Target]. In addition, you must be using [!DNL AEM] as a Cloud Service or [!DNL AEM] 6.4 (or later). Your account representative can help ensure that you meet the requirements to use this feature:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.  
* [!DNL Adobe Target Standard] or [!DNL Adobe Target Premium] account. 

>[!NOTE]
>
>[!DNL Adobe Experience Manager] 6.3 and 6.4 have reached end-of-life and are no longer supported (except for customers who purchased extended support).

Contact [Adobe Target Customer Care](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## Creating and configuring experience fragments in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use [!DNL AEM] experience fragments in [!DNL Target], you must perform the following steps:

### Step 1: Integrate [!DNL AEM] with [!DNL Target]

For more information, see:

* **AEM as a Cloud Service**: [Integrating with Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} in the *Experience Manager as a Cloud Service* guide. 
* **Adobe I/O**: [Integration with Adobe Target using Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank} in the *Administering User Guide* documentation.
* **[!DNL AEM] 6.5**: [Opting into Adobe Analytics and Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en){target=_blank} in the *Adobe Experience Manager 6.5* documentation.
* **[!DNL AEM] 6.4**: [Opting into Adobe Analytics and Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank} in the *Adobe Experience Manager 6.4* documentation.

### Step 2: Create the experience fragment

Experience fragments are created in [!DNL AEM]. For more information, see:

* **AEM as a Cloud Service**: [Experience Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} in the *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM] 6.5**: [Experience Fragments](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en){target=_blank} in the *Adobe Experience Manager 6.5* documentation.
* **[!DNL AEM] 6.4**: [Experience Fragments](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en){target=_blank} in the *Adobe Experience Manager 6.4* documentation.

### Step 3: Configure [!DNL AEM] to share the experience fragment with [!DNL Target]

1. From within [!DNL AEM], select the desired experience fragment or its containing folder, then click **[!UICONTROL Properties]**.
2. Click the **[!UICONTROL Cloud Services]** tab, then from the **[!UICONTROL Cloud Service Configuration]** drop-down list, select **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. Click **[!UICONTROL Save & Close]**.

### Step 4: Publish the experience fragment and export it into [!DNL Target]

Depending on your [!DNL AEM] version, see the following links for step-by-step instructions:

* **AEM as a Cloud Service**: [Exporting Experience Fragments to Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} in the *Experience Manager as a Cloud Service* guide. 
* **[!DNL AEM] 6.5**: [Exporting an Experience Fragment to Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} in the *Adobe Experience Manager 6.5* documentation. 
* **[!DNL AEM] 6.4**: [Exporting an Experience Fragment to Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank} in the *Adobe Experience Manager 6.4* documentation.

## Using experience fragments in [!DNL Target] activities {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

After performing the preceding tasks, the experience fragment displays on the [!UICONTROL Offers] page in [!DNL Target].

>[!NOTE]
>
>* [!DNL Target] currently looks for experience fragments to import every ten minutes. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
>
>* The experience fragment is imported into [!DNL Target] as an HTML offer. That experience fragment "primary" version remains in [!DNL AEM]. You cannot edit the experience fragment in [!DNL Target].

You can hover over an experience fragment in the list, then click the [!UICONTROL View] icon ![View icon](assets/icon_info.png) to see additional information about the experience fragment, including its public offer delivery URL and its [!DNL AEM] path.

You can consume experience fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully use the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Target](/help/main/c-activities/auto-target/auto-target-to-optimize.md) while creating an A/B Test.
>
>Experience fragments are not supported in [!DNL Recommendations] activities. However, to use experience fragments for recommendations you can create an [!UICONTROL A/B Test] activity (including [!UICONTROL Auto-Allocate] and [!UICONTROL Auto-Target]) or an [!UICONTROL Experience Targeting] (XT) activity and [include recommendations as an offer](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). 

**To consume experience fragments using the VEC:**

1. In [!DNL Target], while creating or editing an experience in the [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), click the location on the page where you want to insert [!DNL AEM] content, then select the desired option to display the [!UICONTROL Choose an Experience Fragment] list.

   * [!UICONTROL Insert Before]
   * [!UICONTROL Insert After]
   * [!UICONTROL Swap with Experience Fragment]

   The [!UICONTROL Experience Fragment] list displays the content created in [!DNL AEM] that is now natively available from within [!DNL Target].

   >[!NOTE]
   >
   >The [!UICONTROL Swap with Experience Fragment] option is not available for images. If you want to use this option with an image, click the container element that contains the desired image.

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Done]**. 
1. Finish configuring the activity.

   For more information about configuring the various activity types, see the following topics:

    * **A/B Test:** [Create an A/B Test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) 
    * **Auto-Allocate:** [Auto-Allocate](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 
    * **Auto-Target:** [Auto-Target](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
    * **Automated Personalization (AP):** [Creating an Automated Personalization Activity](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) 
    * **Experience Targeting (XT):** [Create an Experience Targeting Activity](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765) 
    * **Multivariate Test (MVT):** [Create a Multivariate Test](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710) 
    * **Recommendations:** [Create a Recommendations Activity](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**To consume experience fragments using the Form-based Experience Composer:**

1. In [!DNL Target], while creating or editing an experience in the [Form-Based Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), select the location on the page where you want to insert [!DNL AEM] content, then select **[!UICONTROL Change Experience Fragment]** to display the [!UICONTROL Choose an Experience Fragment] list.

   ![](assets/experience_fragment_list.png)

   The [!UICONTROL Experience Fragment] list displays the content created in [!DNL AEM] that is now natively available from within [!DNL Target]. 

1. Select the desired experience fragment, then click **[!UICONTROL Save]**. 
1. Finish configuring the activity.

## Considerations {#considerations}

* [!DNL Target] currently looks for experience fragments to import every ten minutes. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is imported into [!DNL Target] as an HTML offer. The experience fragment "primary" version remains in [!DNL AEM]. You cannot edit the experience fragment in [!DNL Target].
* You cannot create experience fragments using [!DNL Adobe I/O]. Create experience fragments using AEM, as explained above.
* If you update your experience fragment in AEM, the experience fragment must be published and exported to [!DNL Target] again so [!DNL Target] can use the latest changes.

## Removing ClientLibs and extraneous HTML from Experience Fragments exported to Target

When using experience fragment offers with [!DNL Target] on a page delivered by AEM, the targeted page already contains all of the necessary Client Libraries. Note also that extraneous HTML elements in the offer are also not necessary.

Sometimes entire HTML pages wrap the experience fragment and cause problems. Ensure that the experience fragment is a small piece of HTML and not a full HTML page with HTML, HEAD, BODY, and so forth.

For more information, see the following blog post: [AEM 6.5: Removing ClientLibs from Experience Fragments exported to Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Training video: Using AEM experience fragments with [!DNL Adobe Target]

The following video shows you how to set up and use experience fragments: 

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>The [!DNL AEM] deeplink feature discussed at 4:54 has been removed.

For more detailed information, see [Using Experience Fragments with Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) on the *AEM Sites Videos and Tutorials* page.
