---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: Learn about the legacy mbox.js implementation of Adobe Target. Migrate to the Adobe Experience Platform Web SDK (AEP Web SDK) or to the latest version of at.js.
title: How Do I Implement [!DNL Target] with mbox.js?
feature: at.js
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
---
# mbox.js implementation

To use [!DNL Adobe Target Standard] or [!DNL Target Premium], add one line of code to call mbox.js.

 You can use either of two library references: the [!DNL Adobe Experience Platform Web SDK] or [!DNL at.js].

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>We recommend that all customers migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library before this date to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

The single reference to [!DNL mbox.js] on each page provides the libraries needed for all of your activities. [!DNL mbox.js] calls [!DNL Target] from every page that references the [!DNL mbox.js] file. This enables [!DNL Target] to do the following:

* Deliver Target activities 
* Track clicks 
* Track most success metrics

>[!TIP]
>
>To simplify implementation, you could reference [!DNL mbox.js] in your global header.

You do not need to maintain different activity-specific versions of the file. 

1. Reference [!DNL mbox.js] in the `<head>` section of each page on your site.

   `<script src="/ *`directory`*/ *`scripts`*/mbox.js"></script>`

   Where ` *`directory`*/ *`scripts`*` is the directory where you saved your [!DNL mbox.js] file after downloading it. 
If you already have mboxes on your page from a legacy implementation, these mboxes can still be used in the new interface. The updated [!DNL mbox.js] file is still required, but these mboxes can be selected for activities and edited using the [!UICONTROL Visual Experience Composer].
