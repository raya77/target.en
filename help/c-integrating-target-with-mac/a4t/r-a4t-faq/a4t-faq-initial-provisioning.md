---
keywords: faq;frequently asked questions;analytics for target;a4t;provisioning;provisioning;adobe Experience Cloud
description: Find answers to questions that are frequently asked about provisioning Analytics for Target (A4T), which lets you use Analytics reporting for Target activities.
title: Where Can I Find Information about A4T Initial Provisioning?
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
---
# Initial provisioning - A4T FAQ{#initial-provisioning-a-t-faq}

This topic contains answers to questions that are frequently asked about provisioning [!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T).

## How can I set up a multi-page A4T activity?

To implement a basic multi-page A4T use-case:

* Implement the JavaScript libraries for both Target (at.js or mbox.js) and Analytics on the activity landing URL/page. Implementing both solutions stitches the Target data with the Analytics data for each visitor. This data remains in Analytics until it expires with the default expiration set to 90 days.

* For the remaining pages on the site, where just the Analytics metrics are to be tracked, implement Analytics on those pages. It is not necessary to implement Target on those pages. The Analytics metrics captured across those pages are automatically stitched to the Target activity the user initially qualified for, based on the Target information attached to that visitor from the preceding bullet.

## How can I tell whether A4T is enabled on my Target account? {#section_4437D284448F4313BF953D4B6EDBACA6}

Before a report suite can be selected when defining an Analytics activity, you need both an Analytics user account and a Target user account. Your user accounts must be configured as described in the documentation. See [User Permission Requirements](/help/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

After you are a member of one or more Experience Cloud groups that have access to Analytics and Target and you have access to all report suites, you should see the option to create an A/B test using Analytics under **[!UICONTROL Create Activity]**.

If provisioning issues occur, check whether A4T is provisioned correctly.

## Why are my report suites not loading? {#section_6CC8B2B3568A46C499895EB9811FDC2E}

Check the following if any of these problems occur:

* Make sure that your Analytics and Target accounts are linked in the Experience Cloud. 
* Some customers use multiple Analytics company logins in the same Experience Cloud company. If you use multiple logins, make sure that the last Analytics company you logged in to is the one that is tied to the Target account for the integration. 
* If you have been logged in to the Experience Cloud for several hours, sometimes the Analytics session can expire. Log out and log back in to try again.

## Why don't I see Analytics options in Target? {#section_EDD996AFB08B4DB196DD934BE55BF48D}

See "Why are my report suites not loading?" Above. The root cause of this problem is the same.

## Why don't I see A4T reports in Analytics? {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

See "Why are my report suites not loading?" above. The root cause of this problem is the same.

## Why are my reports in Target empty? {#section_3837104757464CB488C5A83014A669A1}

See "Why are my report suites not loading?" above. The root cause of this problem is the same.
