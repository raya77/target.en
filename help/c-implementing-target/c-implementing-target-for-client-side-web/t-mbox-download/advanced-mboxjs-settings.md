---
keywords: advanced mbox.js settings;client;server domain;xdomain;compression level;client session id support;secureOnly;client pc id support;pass page;referring url;traffic level;traffic duration;mboxParameters() function body;mboxSupported() function body;mboxCookieDomain() function body;Extra JavaScript;SiteCatalyst plug-in;Get mbox.js as self-extracting JavaScript;flicker;body hiding;hide body
description: Learn about the legacy mbox.js implementation of Adobe Target. Migrate to the Adobe Experience Platform Web SDK (AEP Web SDK) or to the latest version of at.js.
title: How Do I Configure the [!DNL Target] mbox.js library?
feature: at.js
role: Developer
exl-id: 17821e60-2692-49af-a225-764bd1b6aec1
---
# Configure mbox.js

Information to help you set several settings on the mbox.js Settings page.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: As of March 31, 2021, [!DNL Adobe Target] no longer supports the mbox.js library. Post March 31, 2021, all calls made from mbox.js will gracefully fail and impact your pages that have [!DNL Target] activities running by serving default content.
>
>We recommend that all customers migrate to the most recent version of the new [!DNL Adobe Experience Platform Web SDK] or the at.js JavaScript library before this date to avoid any potential issues with your sites. For more information, see [Overview: implement Target for client-side web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

The default settings of the [!DNL mbox.js] function library serve the needs of most [!DNL Target] customers.

If needed, consult your account representative to change the [!DNL mbox.js] settings.

The following settings are available:

## Client

The client code for your account.

When viewing [!UICONTROL Administration > Implementation], the Client at the top is the client code for your account.

## Timeout

The Target request timeout.

When viewing [!UICONTROL Administration > Implementation], the Timeout (seconds) setting is your Target request timeout. By default this value is set to 15 seconds, but we recommend setting it to a value between 2 seconds and 5 seconds.

## XDomain

Determines whether the browser sets cookies in your own domain (1st party cookies), Target's domain, or both.

Changing this setting affects both mbox.js and at.js.

## Compression Level

Determines how compressed the mbox.js library file is. Increasing the compression level decreases the page-load time.

## mboxParameters() function body

Returns extra parameters to pass to each mbox call.

For example:

return "test=123";

## mboxSupported() function body

Returns false to exclude specific users.

For example:

return !navigator.userAgent.indexOf('Safari') != -1;

The following browsers can be accepted or excluded:

*   IE 5.0 or greater (Windows)
*   Netscape 5.0 or greater (Mac, Windows, Linux)
*   Safari 1.2.4 or greater (Mac)
*   Mozilla Firefox 1.0 or greater (Mac, Windows, Linux)

## mboxCookieDomain() function body

Returns a string describing the domain to set first-party cookies.

For example:

return "YOUR-DOMAIN";

## Extra JavaScript

Includes any additional JavaScript you want to execute on each page.

## SiteCatalyst plug-in

Enables the Analytics Target plug-in.

If enabled, the Analytics plug-in generates plug-in code in mbox.js . This sends Analytics tag information to Target servers as an mbox request on every page tagged with Analytics .

Note that the Analytics plug-in must still be referenced on the page.

## secureOnly

Indicates whether mbox.js should use HTTPS only or be allowed to switch between HTTP and HTTPS based on the page protocol. This is an advanced setting that defaults to False.
