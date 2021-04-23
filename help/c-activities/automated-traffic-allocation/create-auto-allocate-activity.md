---
keywords: create auto-allocate;A/B test;auto-allocate activity;new a/b activity;auto allocate;auto-allocate to best experience;allocate;auto-allocate
description: Learn how to use the Visual Experience Composer (VEC) in Adobe [!DNL Target] to create an Auto-Allocate A/B Test activity directly on a [!DNL Target]-enabled page.
title: How Do I Create an Auto-Allocate Activity?
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
---
# Create an Auto-Allocate activity

Use the [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] to create your [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] activity directly on a [!DNL Target]-enabled page and to modify portions of the page within [!DNL Target].

>[!NOTE]
>
>In addition to the [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] activity (discussed in this article), [!DNL Target] provides two additional types of [!UICONTROL A/B Test] activities: [!UICONTROL Manual (Default)] and [!UICONTROL Auto-Target].
>
>See [Types of A/B Testing activities](/help/c-activities/t-test-ab/test-ab.md#types) in *A/B Test overview*.

To create an [!UICONTROL Auto-Allocate] activity:

1. From the **[!UICONTROL Activities]** list, click **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Create Activity drop-down list](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >The available activity types depend on your [!DNL Target] account. Some activity types might not appear in your list. For example, [!UICONTROL Recommendations] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For information about the various activity types, see [Activities](/help/c-activities/activities.md) and the [Target activities guide](/help/c-activities/target-activities-guide.md).

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![Create A/B Test Activity](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   If you prefer to use the [!UICONTROL Form-Based Experience Composer], select [!UICONTROL Form]. See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >In addition to the VEC and [!UICONTROL Form-Based Experience Composer], [!DNL Target] offers the Single Page Application VEC. For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >For troubleshooting information about the VEC, should you have problems, see [Troubleshooting the Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [[!UICONTROL Choose Workplace]](/help/administrating-target/c-user-management/property-channel/property-channel.md) option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Your organization has a [!UICONTROL Target Standard] license if you do not see this option.

1. (Conditional) If you are a [Target Premium customer](/help/c-intro/intro.md#premium), choose a [workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Specify your [activity URL](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md), then click **[!UICONTROL Next]**.

   If your account is configured with a default URL, that URL appears by default. You can change from the default to another URL.

   The [!UICONTROL Visual Experience Composer] opens, showing the page specified in the URL.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Type a name for the activity in the space provided.

   ![Name field](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   The activity name cannot begin with any of the following characters:

   | Character | Description |
   |--- |--- |
   |`=`|Equals to|
   |`+`|Plus|
   |`-`|Minus|
   |`@`|At sign|

1. Create any new experiences by changing the elements on the page.

   The [!UICONTROL Visual Experience Composer] displays two tabs on the left side after you create a new activity: Experience A and Experience B. Experience A is the control experience. Your focus will be on the Experience B tab, which you can modify as desired. Experience B is the alternate experience you can add to your test. You can add multiple experiences to the test. You can also delete Experience A from the activity if you don't want to include a default site experience as an option.

   For more information about adding and modifying experiences in the [!UICONTROL Visual Experience Composer], see [Add Experience](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). To modify Experience B, start with Step 3. 

1. Click **[!UICONTROL Targeting]** at the top of the [!UICONTROL Visual Experience Composer] to move to the next step in the three-step guided workflow.

   The flow diagram opens.

   ![A/B Test Targeting step](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   The flow diagram leads you through the steps of choosing the audience for the activity and setting up experiences.

1. In the [!UICONTROL Audience] box, click the edit icon (three vertical ellipses), click **[!UICONTROL Replace Audience]**, then [select the audience](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) for your activity.

   By default, the audience is set to [!UICONTROL All Visitors]. 

1. Choose the percentage of qualifying visitors that you want to enter the activity.

   ![Audience percentage](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   For example, you might limit entries to 50% of all visitors or 45% of your "Californians" audience.

1. Set up your traffic allocation.

   You can show multiple experiences to the same audience. A diagram displays showing your selected audience and the experiences you've added to the activity.

   Choose your desired traffic allocation method. To create an [!UICONTROL Auto-Allocate] activity, select **[!UICONTROL Auto-Allocate to best experience]**.

   The three types of traffic allocation are described below:

   * **[!UICONTROL Manual (Default)]**: Specify the percentage of entrants you want to see each experience. You can split the percentages evenly between all experiences, or specify higher or lower percentages for each experience. The total for all experiences must equal 100%. For more information, see [Create an A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-allocate to best experience]**: Most activity entrants are automatically directed to higher-performing experiences. Some visitors are allocated to all experiences, to maintain exploration of experiences and to recognize changes in performance trends.

   * **[!UICONTROL Auto-target for personalized experiences]**: [!DNL Target] uses advanced machine learning to personalize content and drive conversions by identifying multiple high-performing, marketer-defined experiences, and then serving the most tailored experience to visitors based on their individual customer profiles and past behaviors of similar visitors. For more information, see [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md).

   You can also click **[!UICONTROL Add]** to add another experience to the activity.

1. When you are satisfied with your audience, experience choices, and traffic allocation choices, click **[!UICONTROL Next]** to move to the third step of the three-step guided workflow.

1. Specify the [goals and settings](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) for the activity.

   ![A/B Activity Settings](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

   >[!NOTE]
   >
   >If you want to use [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) with this activity, see important information in [A4T support for Auto-Allocate and Auto-Target activities](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Click **[!UICONTROL Save & Close]** or **[!UICONTROL Save]**.

After you create the activity, the [!UICONTROL Overview] tab shows information about the activity, including a diagram of your activity.

## Training video: Creating A/B Tests (8:36) ![Tutorial badge](/help/assets/tutorial.png)

This video demonstrates how to create an A/B test using the [!DNL Target] three-step guided workflow.

* Create an [!UICONTROL A/B Test] activity in [!DNL Adobe Target] 
* Allocate traffic using a manual split or automatic traffic allocation

>[!VIDEO](https://video.tv.adobe.com/v/17391)
