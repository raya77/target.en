---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: Learn how to use environments in Adobe [!DNL Target] to organize your sites and pre-production environments for easy management and separated reporting.
title: What are Environments and How Do I Use Them?
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
---
# Environments

Organize your sites and pre-production environments for easy management and separated reporting.

Hosts are bundled into environments for ease of management. For example, you might have dozens of hosts grouped in two or three environments. The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. You can add new environments and rename your environments, if desired.

One environment, the default environment, is pre-named [!UICONTROL Production]. This default environment cannot be deleted, even if you rename it. [!DNL Target] assumes that this is where you will serve final, approved activities and tests.

When a [!DNL Target] request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. Host management also lets you easily ensure the quality of new activities and content in your test, staging, and development environments before you activate the activities.

To manage environments, click **[!UICONTROL Administration]** > **[!UICONTROL Environments]**.

![Environments list](/help/administrating-target/assets/environments.png)

## Add an environment {#section_32097D0993724DF3A202D164D3F18674}

1. From the [!UICONTROL Environments] list, click **[!UICONTROL Add Environment]**. 
1. Specify a descriptive name for the environment. 
1. Specify the desired active mode for the environment: [!UICONTROL Active Activities] or [!UICONTROL Active and Inactive Activities]. 

   If you specify [!UICONTROL Active and Inactive Activities], hosts from this environment also display inactive activities.
   
1. Click **[!UICONTROL Save]**.

## Set the default environment for reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

You can select the environment you want to use as the default for all activity reports.

If you use [!UICONTROL Production] as your default, all unknown hosts automatically are added here and report data from there is included in the default report view. Instead, creating a "clean" environment ensures only your core sites/domains are included.

To set the default environment for reporting:

1. From the [!UICONTROL Environments] list, click the Star icon

>[!NOTE]
>
>[!DNL Recommendations] users must rebuild their behavior database and product database if hosts switch host groups.

## Change the name of an environment {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. From the [!UICONTROL Environment] list, click the **[!UICONTROL Edit]** icon. 
1. Change the environment name. 
1. Click **[!UICONTROL Save]**.

## Delete an environment {#section_737F8869612047868D03FC755B1223D3}

You can delete an environment when it is no longer needed.

1. From the [!UICONTROL Environment] list, click the **[!UICONTROL Delete]** icon. 
1. Click **[!UICONTROL Delete]** to confirm the deletion.

>[!NOTE]
>
>You cannot delete the [!UICONTROL Production] environment, but you can rename it.

## Recommendations: filter collections and exclusions by environment (host group)

![Premium badge](/help/assets/premium.png)

You can preview the contents of Recommendations collections and exclusions for a selected environment (host group).

>[!NOTE]
>
>Recommendations activities are available as part of the [!DNL Target] Premium solution. They are not available in [!DNL Target] Standard without a [!DNL Target] Premium license.

An environment can be used to separate the available items in your catalog for different uses. For example, you can use host groups for [!UICONTROL Development] and [!UICONTROL Production] environments, different brands, or different geographies. By default, preview results in Catalog Search, Collections, and Exclusions are based on the default host group. (You can also select a different host group to preview results, by using the Environment filter.) By default, newly added items are available in all host groups unless an environment ID is specified when creating or updating the item. 

>[!NOTE]
>
>Delivered recommendations depend on the host group specified in the request.


If you don't see your products, make sure that you are using the correct host group. For example, if you set up your recommendation to use a staging environment and you set your host group to Staging, you might need to re-create your collections in the staging environment for the products to show. To see which products are available in each environment, use Catalog Search with each environment. You can also preview the contents of Recommendations collections and exclusions for a selected environment (host group).

>[!NOTE]
>After changing the selected environment, you must click Search to update the returned results.

The [!UICONTROL Environment] filter is available from the following places in the Target UI:

* Catalog Search ([!UICONTROL Recommendations > Catalog Search])
* Create Collection dialog box ([!UICONTROL Recommendations > Collections > Create New])
* Update Collection dialog box ([!UICONTROL Recommendations > Collections > Edit])
* Create Exclusion dialog box ([!UICONTROL Recommendations > Exclusions > Create New])
* Update Exclusion dialog box ([!UICONTROL Recommendations > Exclusions > Edit])
