---
keywords: Targeting;eec;visual experience composer;troubleshoot enhanced experience composer;troubleshooting
description: Learn how to troubleshoot problems that sometimes occur in the Adobe [!DNL Target] Enhanced Experience Composer (EEC) under certain conditions.
title: How Do I Troubleshoot Issues Related to the Enhanced Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
---
# Troubleshooting issues related to the [!UICONTROL Enhanced Experience Composer]

Display problems sometimes occur in the [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) under certain conditions.

## The EEC won't load an internal QA URL that is not accessible on public IP. {#section_D29E96911D5C401889B5EACE267F13CF}

This can be resolved by allowlisting the following IP addresses. These IP addresses are for Adobe's server used for the EEC proxy. They are only required for activity editing. Visitors to your site do not need these IP addresses allowlisted.

Ask your IT team to allowlist the following IP addresses:

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

You might see the following error message in [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error image](assets/EEC_error.png)

The following are reasons that you might see this error message and remedies to fix the situation:

* **Issue:** Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer].

  **Remedy:** Allowlist the IP addresses listed above. 

* **Issue:** The IP addresses are allowlisted but your website does not support TLS version 1.2. [!DNL Target] currently uses the default configuration of 1.2. Prior to the [!DNL Target] 18.4.1 (April 25, 2018), the default configuration supported TLS 1.0. For more information, see [TLS (Transport Layer Security) Encryption Changes](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank}.

  **Solution:** See the following question (The [!UICONTROL Enhanced Visual Experience Composer] won't load on secure pages on my site that use TLS 1.2).

## The EEC won't load on secure pages on my site that use TLS 1.0. (EEC only) {#section_C5B31E3D32A844F68E5A8153BD17551F}

You might see the error message described above in "The [!UICONTROL Enhanced Visual Experience Composer] won't load on secure pages on my site." if the above IP addresses are allowlisted but your website does not support TLS version 1.2. [!DNL Target] currently uses the default configuration of 1.2. Prior to the [!DNL Target] 18.4.1 (April 25, 2018), the default configuration supported TLS 1.0. For more information, see [TLS (Transport Layer Security) Encryption Changes](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank}.

To check the TLS version on your website using Firefox (other browsers have similar steps):

1. Open the affected website in Firefox. 
1. Click the **[!UICONTROL Show Site Information]** icon on the browser's address bar.

   ![firefox_more_info image](assets/firefox_more_info.png)

1. Click **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![firefox_more_info_2 image](assets/firefox_more_info_2.png)

1. Examine the TLS version information under Technical Details:

   ![firefox_more_info_3 image](assets/firefox_more_info_3.png)

1. If you find that your website is showing TLS 1.0, see [TLS (Transport Layer Security) Encryption Changes](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank} for information about Target's TLS support policy. To remedy the situation for now (valid until September 12, 2018){target=_blank}, reach out to [Customer Care](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for configuration with your TLS version and the domain.

## I'm seeing timeouts or "access denied" errors when loading sites with proxy enabled. (EEC only) {#section_60CBB9022DC449F593606C0E6252302D}

Make sure proxy IPs are not blocked in your environment.
