---
keywords: Implementation;Mbox;mbox.js;download mbox.js;configure mbox.js
description: Learn about the legacy mbox.js implementation of Adobe Target. Migrate to the Adobe Experience Platform Web SDK (AEP Web SDK) or to the latest version of at.js.
title: How Do I Download the [!DNL Target] mbox.js library?
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
---
# Download mbox.js

Target Standard and Premium use a modified version of the Adobe Target mbox.js file.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>We recommend that all customers migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library before this date to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

To use the [!DNL Adobe Target] [!UICONTROL Visual Experience Editor], you must include an additional line of JavaScript as part of your [!DNL mbox.js] file. 

1. Click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** in [!DNL Target Standard].
1. Click **[!UICONTROL Download mbox.js]** and follow the prompts to save the file.
1. (Conditional) If you use [!DNL mbox.js] version 60 or later, you can configure the library to automatically hide page content by default until mboxes load to reduce flicker on responsive sites.

1. Create the [!DNL mbox.js] reference on the website.

   Beginning with [!DNL mbox.js] version 57, the [!DNL mbox.js] reference can be placed anywhere within the `<head>` section of the page.

   >[!IMPORTANT]
   >
   >If you use a version of [!DNL mbox.js] prior to version 57, the reference must be the last item in the `<head>` section of your pages. If the reference is not the last item, serious display or performance issues could result.

1. Upload the saved [!DNL mbox.js] file to the location in your hosting environment that you specified in the code.
