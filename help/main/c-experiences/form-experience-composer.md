---
keywords: form-based experience composer;form-based composer;refinements
description: Learn how to use the Adobe [!DNL Target] Form-Based Experience Composer for non-visual experience creation. Use this composer when the VEC is not available or not practical to use.
title: How Do I Use the Form-Based Experience Composer?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
---
# Form-Based Experience Composer

The [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] is a non-visual experience and offer creation interface that’s useful in creating experiences for use in [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization], and [!UICONTROL Recommendations] activities when the [!UICONTROL Visual Experience Composer] (VEC) is not available or practical for use. For example, you might use the Form-Based Experience Composer to create experiences and offers for delivery in emails, kiosks, and voice assistants.

If you are creating a [!UICONTROL Recommendations] activity, there are no experiences. Choose your criteria and design. If you choose multiple criteria or designs, [!UICONTROL Target] automatically generates the experiences. 

1. Click **[!UICONTROL Create Activity]**, then select the type of activity you want to create.

   The [!UICONTROL Form-Based Experience Composer] is available for [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization], and [!UICONTROL Recommendations] activities.

1. Select **[!UICONTROL Form]** from the [!UICONTROL Create Activity] dialog box.

1. (Conditional) Choose a workspace and property.

1. Click **[!UICONTROL Next]**.

   The [!UICONTROL Form-Based Experience Composer] opens.

   ![location_refinements image](assets/location_refinements.png)

   This screen is different if you are creating a [!UICONTROL Recommendations] activity. [!UICONTROL Recommendations] activities do not include experiences.

1. Name the activity by clicking "[!UICONTROL Untitled Activity]."
1. Select a location.

   When you click in the [!UICONTROL Select Location] box, a list of available locations appears. Select one of those locations.

   You can also enter a location that is not listed here. This can be useful if the mbox has not yet been created or viewed on a page. Type the name of the location. Be careful when entering a location that does not yet exist. If the spelling or capitalization does not match the spelling and capitalization when the mbox call is made, the activity will not deliver. Manually entered locations are saved to the list of available locations. The next time you try to select a manually entered location, it will be available from the [!UICONTROL Select Location] drop-down list for that activity.

   >[!NOTE]
   >
   >Creating a manually entered location during activity creation does not automatically create a new location. The location name is saved only in the context of the activity. The location is created when there is a content delivery call. Subsequent to the location being created, it will be available for use in other activities, for creating audiences, etc. from the drop-down list of available locations.
   
1. Click **[!UICONTROL Add Audience Refinements]**, choose one or more [audience](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) for this activity, then click **[!UICONTROL Done]**.

   ![location_refinements_2 image](assets/location_refinements_2.png)

   In the [!UICONTROL Form-based Experience Composer], refinements have been replaced with full audience functionality. Refinements for existing activities have been migrated to [activity-only audiences](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Select the type of content you want to appear in that location.

   ![form_content image](assets/form_content.png)

1. For the content type you selected, specify the content.

   **Change HTML Offer:** Choose an HTML offer.

   **Change Image Offer:** Choose an image saved in the content library in Target.

   You can also add a link to an image (click-through, destination, landing, and so forth.)

      1. Click [!UICONTROL Change Image Offer].
      1. Select the desired image, then click [!UICONTROL Edit Links].
      1. Specify the desired URL or page on your site, then click [!UICONTROL Update].

   **Change JSON offer:** Choose a json offer.

   **Change Experience Fragment:** Choose an Experience Fragment. For more information, see [Experience Fragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Change Redirect Offer:** Choose a redirect offer. For more information, see [Create redirect offers](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Change Remote Offer:** Choose a remote offer. For more information, see [Create remote offers](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Create HTML Offer:**

      1. Click [!UICONTROL Offers], then select the [!UICONTROL Code Offers] tab.
      1. Click [!UICONTROL Create] > [!UICONTROL HTML Offer].
      1. Type an offer name.
      1. Type or paste your HTML code in the Code box.
      1. Click [!UICONTROL Save].

   **Create JSON Offer:**

      1. Click [!UICONTROL Offers], then select the [!UICONTROL Code Offers] tab.
      1. Click [!UICONTROL Create] > [!UICONTROL JSON Offer].
      1. Type an offer name.
      1. Type or paste your JSON code in the Code box.
      1. Click [!UICONTROL Save].

   **Add Recommendation:**
   
   For a Recommendations activity, the Content drop-down gives you the [!UICONTROL Add Recommendation] option. Click **[!UICONTROL Add Recommendation]**, then select the page type. Then follow the usual steps as defined in the interface to [create a Recommendations activity](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   While selecting Recommendations criteria in the Form-Based Experience Composer, there is now a direct link to the selected Criteria card so you can quickly and easily edit the criteria.

   ![change_criteria image](assets/change_criteria.png)

   From the Targeting page of the Target three-step guided workflow:

   ![change_criteria_2 image](assets/change_criteria_2.png)

   **Add Offer Decision:**

   Add an offer created in [!DNL Adobe Journey Optimizer] (AJO) to an [!DNL Adobe Target] activity to present the best dynamic offer and experience to your visitors on your website or mobile site using offer decisioning. This option is available for manual [!UICONTROL A/B Test] and [!UICONTROL Experience Targeting] (XT) activities only. 
   
   For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Optional, for [!UICONTROL A/B Test], [!UICONTROL Automated Personalization], and [!UICONTROL Experience Targeting] activiites) To repeat this process for additional locations, click **[!UICONTROL Add Location]** and configure the location and content.
1. Click **[!UICONTROL Next]**, then complete the activity creation steps as usual for your activity type.

* [Create an A/B Test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) 
* [Create an Experience Targeting Activity](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765) 
* [Create a Recommendations Activity](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Training video: Form-based Composer ![Tutorial badge](/help/main/assets/tutorial.png)

This video provides a demo of the form-based composer.

* Create an activity using the Form-Based Experience Composer 
* Understand when to use Form-Based Experience Composer vs. the Visual Experience Composer 
* Use refinements to target a location

>[!VIDEO](https://video.tv.adobe.com/v/17390)
