---
keywords: at.js plugins;supported plugins;unsupported plugins;ttMeta;ttmeta;mboxTrack
description: Learn about the legacy mbox.js implementation of Adobe Target. Migrate to the Adobe Experience Platform Web SDK (AEP Web SDK) or to the latest version of at.js.
title: What Legacy Plug-ins Are Not Supported in Target at.js?
feature: at.js
role: Developer
exl-id: 1d858f5b-58dc-4181-9cb5-aa6b22011abc
---
# at.js plug-ins

Information about supported and not-supported at.js plug-ins in Adobe Target.

Many people have built customized plugins and response plug-ins for [!DNL mbox.js]. These custom plug-ins might not be supported by [!DNL at.js] without being updated.

If you are using a plug-in that is not listed here and you would like to know the status, please contact your account representative.

Here is the current status of some of the plug-ins that are used by many customers when used with [!DNL at.js]: 

|Plugin|Details|
|--- |--- |
|mboxTrack|Not supported.<br>This is replaced by the [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) function. Update your plug-ins to apply the new function.<br>See the [integrations](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md) page.|
|Persistent Profile Backup Plugin|Not supported.<br>This plug-in was deprecated when the  Target profile lifetime was extended from two weeks to 90 days. Check the expiration date of your mbox cookie to see the profile lifetime setting on your account.<br>Contact ClientCare if you would like to extended the profile lifetime to 90 days.|
|ttMeta|Old SiteCatalyst plugins should be disabled and replaced with [Adobe Analytics as the reporting source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). The ttMeta plugin should be disabled and replaced with the [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj).|
