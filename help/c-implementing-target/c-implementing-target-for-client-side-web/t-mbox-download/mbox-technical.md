---
keywords: implementation;mbox.js;dom manipulation library;target.js;visual experience composer;iframe;angular sites;single page applications;single page app;SPA
description: Learn about the legacy mbox.js implementation of Adobe Target. Migrate to the Adobe Experience Platform Web SDK (AEP Web SDK) or to the latest version of at.js.
title: What does the [!DNL Target] mbox.js Library Do?
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
---
# What mbox.js does

Information to help your technical staff understand the mbox.js implementation and how it might affect your site.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>We recommend that all customers migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library before this date to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## DOM Manipulation {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] controls the DOM manipulation library used by Standard. To display the content of a website, [!DNL target.js] references [!DNL sizzle.js] (version1.10.8-pre). [!DNL Sizzle.js] enables the HTML element selectors. Other than [!DNL sizzle.js], only native JavaScript is used. No jquery is required.

In addition, the following snippet is used for polling the DOM: 
`https://github.com/dperini/ContentLoaded`  

## Target.js and the Visual Experience Composer {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

When you use the [!UICONTROL Visual Experience Composer] to set up an experience for an activity, your web page is opened in an iFrame. When the iFrame is loaded, Standard sends an HTML5 `postMessage` API call. [!DNL Target.js] detects any `postMessage` calls and includes the following JavaScript libraries on the website:

* For thumbnail generation: [!DNL https://html2canvas.hertzen.com/] 
* For cross-domain query: [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css], used to send messages across the iFrames. These scripts allow Adobe to send data between the pages.

## Considerations for Angular Sites and Single-Page Applications {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

If you are implementing Target in an Angular site or in any Single-Page Application (SPA), you should use the at.js library instead of mbox.js.
