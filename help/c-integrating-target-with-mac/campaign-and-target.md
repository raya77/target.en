---
keywords: Overview and Reference
description: Learn how to use Adobe [!DNL Target] with Adobe Campaign to optimize email content.
title: How Do I Integrate [!DNL Target] with Adobe Campaign?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
---
# Integrate [!DNL Target] with Adobe Campaign

Use [!DNL Target] with [!DNL Adobe Campaign] to optimize email content.

To optimize your email content, you can create a redirect offer in [!DNL Target], then use [!DNL Adobe Campaign] to manage the email offers. For example, you can display different offers for male and female recipients.

The integration takes place when the email is opened. When the customer opens the email, a call is made to [!DNL Target] and a dynamic version of the content appears. The content consists of a static image supported by all browsers. [!DNL Target] tracks the reaction to the offer at the audience or session level and that data is available in [!DNL Target] reports.

[!DNL Target] can track the following data:

* User agent 
* IP address 
* Geographical location 
* Segment associated with the visitor's ID in [!DNL Target] (subject to legal approval) 
* Data from [!DNL Campaign] Datamart

There are several limitations:

* Because only an image can be used, content cannot be personalized. 
* Tracking is not consolidated in [!DNL Adobe Campaign]. 
* No unified user experience.

Use both [!DNL Target] and [!DNL Campaign] to set up different parts of the integration:

* The raw box and the experience in [!DNL Target]

>[!NOTE]
>
>When using a rawbox and [!DNL Target], see the important security notice under [Create allowlists that specify hosts that are authorized to send mbox calls to Target](/help/administrating-target/hosts.md#allowlist). 

* The delivery in [!DNL Campaign]

## Before you begin {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use [!DNL Adobe Campaign] to set up your targeted email offers, set up the following in [!DNL Target]:

* Two or more [!DNL Target] redirect offers

  See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md). 

* A [!DNL Target] activity with an experience for each offer and the desired [success metric](/help/c-activities/r-success-metrics/success-metrics.md).

  See [Redirect to a URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Start the activity in [!DNL Target] before setting up the [!DNL Campaign] portion of the integration.

## Include a [!DNL Target] offer in an [!DNL Adobe Campaign] email {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in [!DNL Adobe Campaign]. 
1. In the email properties, click **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]**. 
1. Select the default image from the shared assets. 
1. Specify the location (rawbox). 
1. Add any other decisioning parameters, such as the gender of the recipient. 
1. Preview the email, selecting at least one recipient for each offer (in this case, a male and a female). 
1. In [!DNL Campaign], define the [!DNL Target] Edge server you are using to control the activity and the name of the tenant. 
1. Specify the external account used for the [!DNL Adobe Experience Cloud] so you can access the resources in the [!DNL Experience Cloud].

For more information, refer to the [!DNL Adobe Campaign] documentation.

## Video: Integrate [!DNL Target] with [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
