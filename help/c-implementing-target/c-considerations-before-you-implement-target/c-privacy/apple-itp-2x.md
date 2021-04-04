---
keywords: apple;ITP;intelligent tracking prevention;experience cloud id;ecid
description: Learn about Adobe Target and the impact of the Apple Intelligent Tracking Prevention (ITP) initiative that seeks to protect Safari users' privacy.
title: How Does Target Handle Apple ITP Support?
feature: Privacy & Security
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
---
# Apple Intelligent Tracking Prevention (ITP) 2.x

Information about [!DNL Adobe Target] support for Apple’s ITP 2.x via the Experience Cloud ID (ECID) library 4.3.

Intelligent Tracking Prevention (ITP), is Apple’s initiative to protect Safari users’ privacy. The first release of ITP, which was in 2017, targeted the usage of third-party cookies. In fact, Apple blocked third-party cookies entirety, which in turn, caused a severe headache for ad tech and mar tech companies because third-party cookies are generally used for tracking visitors and collecting visitor data. Now, Apple is on the move to place limitations and restrictions on how first-party cookies are used within Safari.

These versions of ITP include the following restrictions:

|Version|Details|
| --- | --- |
[ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)|Capped client-side cookies that are placed on the browser using the `document.cookie` API to a seven-day expiry.<br>Released February 21, 2019.|
|[ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/)|Drastically reduced the seven-day expiry cap to one day.<br>Released April 24, 2019.|
|[ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/)|Eliminated several workarounds, such as employing localStorage or using the JavaScript `Document.referrer property`.<br>Released September 23, 2019.|

## What is the impact to me as an Adobe Target customer? {#impact}

[!DNL Target] provides JavaScript libraries for you to deploy on your pages so that [!DNL Target] can deliver real-time personalization to your visitors. There are three Target JavaScript libraries ([at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors' browsers via the `document.cookie` API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.x and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2 and ITP 2.3).

Apple ITP 2.x impacts [!DNL Target] in the following areas:

|Impact|Details|
| --- | --- |
|Potential increase of unique visitor counts|Due to the expiration window being set to seven days (with ITP 2.1) and one day (with ITP 2.2 and ITP 2.3), you might see an increase of unique visitors coming from Safari browsers. If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2 and ITP 2.3), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same.|
|Decreased lookback periods for [!DNL Target] activities|Visitor profiles for [!DNL Target] activities might have a decreased lookback period for decisioning. [!DNL Target] cookies are leveraged to identity a visitor and store user profile attributes for personalization. Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2 and 2.3), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning.|
|Profile scripts based on 3rdPartyID|Due to the expiration window being set to seven days (with ITP 2.1) and one day (with ITP 2.2 and ITP 2.3), [profile scripts](/help/c-target/c-visitor-profile/profile-parameters.md) based on the 3rdPartyID cookie will stop functioning upon expiration.|
|QA/Preview URLs in iOS devices|Due to the expiration window being set to seven days (with ITP 2.1) and one day (with ITP 2.2 and ITP 2.3), [QA/Preview URLs](/help/c-activities/c-activity-qa/activity-qa.md) will stop functioning upon expiration because the URLs are based on the 3rdPartyID cookie.|

## Is my current implementation of [!DNL Target] impacted?

In a Safari browser, navigate to your website on which you have a [!DNL Target] JavaScript library. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.  

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## How can I mitigate the impact of future ITP 2.x releases to Target?

To mitigate the impact of future ITP 2.x releases to Target, complete the following tasks:

1. Deploy the Experience Cloud ID (ECID) library to your pages.

   The ECID library enables the people identification framework for Experience Cloud Core solutions. The ECID library allows you to identify same site visitors and their data in different Experience Cloud solutions by assigning persistent and unique identifiers. The ECID library will be updated frequently to help you mitigate any ITP-related changes that impact your implementation. 

   For ITP 2.x, [ECID library 4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html) must be utilized for mitigation.

1. Use Adobe’s CNAME and Enroll in Adobe Analytics' Managed Certificate Program.

   After installing the ECID library 4.3.0+, you can leverage Adobe Analytics' CNAME and Managed Certificate Program. This program lets you implement a first-party certificate for first-party cookies at no charge. Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.x. 

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

After you deploy a Target JavaScript library in conjunction with the ECID library v4.3.0+ and enroll in the Adobe Managed Certificate Program to leverage CNAME, you will have a robust and long-term mitigation plan for ITP-related changes.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] has already announced support for [Google’s SameSite Chrome Policies](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) in addition to support for Apple’s ITP 2.x. 

As policies continue to evolve to protect our consumers, [!DNL Adobe] will also continue to support these initiatives in [!DNL Target], while helping our customers provide the best-in-class personalized experiences.
