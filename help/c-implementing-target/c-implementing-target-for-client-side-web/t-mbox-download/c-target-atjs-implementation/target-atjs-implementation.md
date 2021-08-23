---
keywords: Target Standard;at.js;implementation
description: Learn how to migrate to at.js, the new implementation library for Adobe [!DNL Target] designed for both typical web implementations and Single Page Applications (SPAs).
title: How Do I Migrate from mbox.js to at.js?
feature: at.js
role: Developer
exl-id: 1d95faeb-7caa-44d6-b637-a06db393e50e
---
# Migrate from mbox.js to at.js

The at.js library is a new implementation library for [!DNL Adobe Target] designed for both typical web implementations and single-page applications.

Among other benefits, [!DNL at.js] improves page-load times for web implementations and provides better implementation options for single-page applications.

[!DNL at.js] replaces [!DNL mbox.js] for [!DNL Target] implementations. The [!DNL at.js] library also includes the components that were included in [!DNL target.js], so there is no longer a call to [!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 with FP-11577 (or later) supports at.js implementations with its Adobe Target Cloud Services integration. For more information, see [Feature Packs](https://experienceleague.adobe.com/docs/) and [Integrating with Adobe Target](https://experienceleague.adobe.com/docs/) in the *Adobe Experience Manager 6.2 documentation*.

## Implement at.js {#implement}

To use [!DNL at.js], replace the [!DNL mbox.js] reference on pages where you want to implement it. You cannot use both [!DNL mbox.js] and [!DNL at.js] on a single page. However, you can use either on each page on your site.

The [!DNL at.js] library works for existing implementations using the `mboxCreate()`, `mboxDefine()`, and `mboxUpdate()` functions and supports new functionality focused on single-page-app based implementations.

You can use [!DNL at.js] anywhere you currently use [!DNL mbox.js].

The [!DNL at.js] library offers several improvements over the [!DNL mbox.js] library, including:

* Completely asynchronous communication via cross domain AJAX

  >[!IMPORTANT]
  >
  >Although [!DNL at.js] communicates with the [!DNL Target] servers asynchronously, the [!DNL at.js] file itself must load synchronously in the `<head>` section of your page. Ideally, it should be one of the first scripts loaded. Once loaded, [!DNL at.js] executes mbox calls asynchronously through `XMLHttpRequest`, and does not block page rendering.

* No more blocking calls 
* No `document.write()` used 
* No immediate execution of JavaScript in [!DNL Target] responses 
* Better timeout and error handling

    * Customizable [timeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) per call 
    * No reloads on timeouts

* Functions designed specifically for single-page apps/MVC frameworks

## Training video: at.js - Advantages and Implementation Best Practices ![Overview badge](/help/assets/overview.png)

This video is a recording of " [Office Hours](/help/cmp-resources-and-contact-information.md)," an initiative led by the Adobe Customer Care team.

* How the at.js library works 
* The advantages of at.js over mbox.js 
* How at.js manages flicker 
* Error handling in at.js 
* Debugging methodologies 
* Known issues and future roadmap

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
