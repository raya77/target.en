---
keywords: visitor profile;target visitor profile
description: Learn how to create audiences in [!DNL Adobe Target] to target visitors who meet specific profile parameters such as new or returning visitor, category affinity, and more.
title: Can I Target Visitors Who Meet Specific Profile Parameters?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
---
# Visitor Profile

Create audiences in [!DNL Adobe Target] to target visitors who meet specific profile parameters.

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**. 
1. Name the audience and add an optional description. 
1. Drag and drop **[!UICONTROL Visitor Profile]** into the audience builder pane.

1. Click **[!UICONTROL Select]**, then select one of the following options:

   ![target_visitor_profile image](assets/target_visitor_profile.png)

   Visitor profile parameters are passed via the mbox (profile). You can target either new or returning visitors, or include all users.

    * [!UICONTROL New Visitor] 
    * [!UICONTROL Returning Visitor] 
    * [!UICONTROL In Other Tests] 
    * [!UICONTROL Not In Other Tests] 
    * [!UICONTROL First Page of Session] 
    * [!UICONTROL Not First Page of Session] 
    * [!UICONTROL Category Affinity]

   A visitor profile is created in the local edge memory for each mbox call with new `mboxPC`. After 30 minutes of inactivity, the profile is saved to the [!DNL Target] database and is accessible from other edges.

   When a site visitor logs in mid-session and gets a `3rdpartyId`, all previously loaded profile attributes tied to the `3rdPartyId` are immediately available.

   You can target custom profile parameters and `user.` parameters. Choose the parameter you use want to use to target your activity. If the desired parameter does not display, the parameter has not been fired by an mbox. 

1. (Optional) Set up additional rules for the audience. 
1. Click **[!UICONTROL Done]**.

## Training video: Creating Audiences ![Overview badge](/help/main/assets/overview.png)

This video includes information about using audience categories.

* Create audiences 
* Define audience categories

>[!VIDEO](https://video.tv.adobe.com/v/17392)
