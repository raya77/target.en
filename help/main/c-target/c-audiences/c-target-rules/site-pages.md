---
keywords: site pages;target site pages;targeting;current page;target current page;previous page;target previous page;landing page;target landing page;http header
description: Learn how to target visitors using [!DNL Adobe Target] who are on a specific page on your site.
title: Can I Target Visitors Based on Site Pages?
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
---
# Site Pages

You can target visitors using [!DNL Adobe Target] who access a specific page on your site.

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**. 
1. Name the audience and add an optional description. 
1. Drag and drop **[!UICONTROL Site Pages]** into the audience builder pane.

   ![Site Pages audience](assets/target_site_pages.png)

1. Click the **[!UICONTROL Select]** drop-down list, select one of the following options, then configure the rule as desired.

    The available options and evaluators in subsequent drop-down lists in the rule vary depending on which option you choose. The following illustration shows the available options if you choose [!UICONTROL Current Page]:

    ![Current Page](assets/current-page.png) 

    The following options are available in the initial drop-down list when you choose [!UICONTROL Select].

    * **[!UICONTROL Current Page]:** The page the user is viewing.

      The following options are available in the second drop-down list if you choose this option:

      * [!UICONTROL URL] (For more information about how [!DNL Target] evaluates URLs, see [Targets and audiences FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

    * **[!UICONTROL Previous Page]:** The page the user was viewed before clicking to the current page. The user must click from the previous page to the current page for the page to be tracked. The previous page is not tracked if the user types a new URL in the browser. The actual content of this page depends on the design of your site. For example, if the current page displays information about a specific product, the previous page might be a category page where the visitor selects the specific item. For example, a page displaying several cameras of a certain type, or it might be the home page that leads to the final page.

      The following options are available in the second drop-down list if you choose this option:

      * [!UICONTROL URL] (For more information about how Target evaluates URLs, see [Targets and audiences FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]

    * **[!UICONTROL Landing Page]:** The landing page is the first page the visitor sees when accessing your site. For example, if the visitor clicks a link on Google that leads to a category page, then the category page is the landing page. If the link leads to your home page, then the home page is the landing page. The landing page is remembered for the visitor's session. You can target deeper in the site based on what the visitor's landing page was in this session.

      The following options are available in the second drop-down list if you choose this option:

      * [!UICONTROL URL] (For more information about how Target evaluates URLs, see [Targets and audiences FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

      >[!NOTE]
      >
      >The `landing.url` object is reset on a subdomain change or direct URL replacement. 

    * **[!UICONTROL HTTP Header]:** This option evaluates the information in the HTTP header of the [!DNL Target] request. For example, if the HTTP header contains language information, you could create a rule that contains the `Accept-Language: es` condition to target visitors who access the page in Spanish.

      The following options are available in the second drop-down list if you choose this option:

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Authorization]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL Connection]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Date]
      * [!UICONTROL Expect]
      * [!UICONTROL From]
      * [!UICONTROL Host]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Proxy-Authorization]
      * [!UICONTROL Range]
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL Upgrade]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL Warning]

   If you chose [!UICONTROL Current Page], [!UICONTROL Previous Page], or [!UICONTROL Landing Page], the [!UICONTROL Domain] and [!UICONTROL Query] options are available. Consider the following when choosing these options:

    * **Domain:** The full domain of the page. When specifying a domain, best practice is to use "contains." For example, "Domain equals facebook.com" does not accept `m.facebook.com` or `www.facebook.com`. "Domain contains facebook.com" accepts any variant of facebook.com. 
    * **Query:** The content of the URL after the first question mark (?).

      `foo.html?e0a72cb2a2c7`

1. (Optional) Set up additional rules for the audience. 
1. Click **[!UICONTROL Done]**.

You can also create site pages audiences using you own "user-defined query parameter" or "user-defined header."

Use a:

* Query parameter if the rule selected by the user is [!UICONTROL Current Page], [!UICONTROL Landing Page], or [!UICONTROL Previous Page] 
* Header if the rule selected by the user is an HTTP header

## Troubleshooting {#ts}

* For landing page audiences to function properly, requests must have the `mboxReferrer` parameter set (for the Delivery API the `context.address.referringUrl` parameter) that the at.js JavaScript library takes from the page using the `document.referrer` attribute. This `HTMLDocument` attribute returns the URI of the page the user has navigated from. The value of this attribute is an empty string when the user navigates to the page directly (not through a link, but, for example, via a bookmark).

  If this behavior does not match your requirements, consider performing one of the following actions:

  * Pass [mbox parameters](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/){target=_blank} to [!DNL Target] to be used for targeting purposes.
  * Use an [A/B Test activity](/help/main/c-activities/t-test-ab/test-ab.md) instead of a landing page activity. A/B Test activities do not switch experiences for the same visitor.
  * Use a [visitor profile](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) instead.
  
* When using "starts/ends with" evaluators on strings containing commas, these strings are evaluated as an array of values, in which each value separated by comma is evaluated. For example if you have the value for a header: `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` it qualifies for conditions like:
  * starts with zh,
  * starts with en,
  * ends with 0.7,
  * ends with 0.8.

## Training video: Creating Audiences

This video includes information about using audience categories.

* Create audiences 
* Define audience categories

>[!VIDEO](https://video.tv.adobe.com/v/17392)
