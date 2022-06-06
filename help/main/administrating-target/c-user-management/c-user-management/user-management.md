---
keywords: add user;manage user;user permissions
description: Learn how to use the Adobe Admin Console to manage users and their permissions and right in Adobe Target.
title: How Do I Add Users and Manage Permissions?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
---
# Users

Add users and manage their permissions in the [!DNL Adobe Admin Console].

>[!NOTE]
>
>[!UICONTROL Properties] and [!UICONTROL Permissions] functionality is available as part of the [!DNL Target] Premium solution. They are not available in [!DNL Target] Standard without a [!DNL Target] Premium license.
>You can tell whether your organization has a Standard or Premium license by clicking the [!UICONTROL Administration] link at the top of the [!DNL Target] UI.
>
>* **[!DNL Target] Standard Customers**: If you see the [!UICONTROL Users] tab ([!UICONTROL Administration > Users]) (and not the **[!UICONTROL Properties]** tab), your organization has a [!DNL Target] Standard license. [!DNL Target] Standard customers should follow the instructions in this article to add users and assign permissions in the [!DNL Adobe Admin Console].
>
>* **[!DNL Target] Premium Customers**: If you see the [!UICONTROL Users] tab and the [!UICONTROL Properties] tab ([!UICONTROL Administration > Properties]), your organization has a [!DNL Target] Premium license. [!DNL Target] Premium customers should follow the instructions in [Enterprise user permissions](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) and [Configure enterprise permissions](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) to add users and assign permissions in the [!DNL Adobe Admin Console].
>
>For detailed information about how to manage users and permissions, see [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the *Enterprise & Teams User Guide*.

When you get started with [!DNL Adobe Target], you will find IDs (ending in Adobe.com) pre-populated in your [!DNL Adobe Experience Cloud] account. These IDs are for members of [!DNL Adobe] teams so that they can assist you with your new account and with your use of [!DNL Adobe Target], should you need help. To get assistance, reach out to your Adobe teams in the usual way.

You will not see the new user listed on the [!UICONTROL Users] page until the user logs in using his or her [!DNL Adobe Experience Cloud] account and then logs in to [!DNL Target Standard/Premium].

By default all [!DNL Target] users start with observer permissions.

Admin users are identified in the [!UICONTROL Users] list. Contact one of the system admin users if you need your access level changed.

## View user information from within Target

You can view a list of your current users in your Target environment, including their roles per workspace and email addresses directly from inside Target.

To view the Users page, click **[!UICONTROL Administration]** > **[!UICONTROL Users]**.

![User list from within Target](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>To manage existing user or to add new users, you must use the [!UICONTROL Adobe Admin Console], as explained below.

## Access the Adobe Admin Console {#access}

For tasks performed in the Adobe Admin Console, access the console by following these steps:

1. From within [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**.

   Or

   Go to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), then sign in using your Adobe ID, if you have not already logged in.

1. (Conditional) If you have access to the [!DNL Admin Console for Enterprise] for more than one organization, click the user avatar in the right corner or the top navigation bar, then select the desired organization.

## Add users {#add-users}

All user management must be performed in the [!DNL Adobe Admin Console for Enterprise]. However, all of your existing users in [!DNL Target] will be migrated from [!DNL Target] to the [!DNL Admin Console for Enterprise].

1. [In the Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), click **[!UICONTROL Users]** > **[!UICONTROL Users]** to create new users or to edit existing users. 
1. Follow the instructions in [Manage Users and Groups in the Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) in the *Enterprise User Guide*.

## Create user groups {#user-groups}

You can create user groups, such as Developers, Analysts, Marketers, Executives, etc., and then assign privileges across multiple Adobe products and workspaces. Assigning a new team member all the appropriate privileges across different Adobe products can be as easy as adding them to a specific user group.

1. [In the Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), click **[!UICONTROL Users]** > **[!UICONTROL User Groups]** to create new user groups or to edit existing groups. 
1. Follow the instructions in [Manage Users and Groups in the Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) in the *Enterprise User Guide*.

## Specify roles and permissions {#roles-permissions}

Only system admins can set user roles in [!DNL Target]. For example, a Standard approver user cannot change an observer to an approver, without also having [!DNL Experience Cloud] Admin rights.

System admin users must add users to the system. Users are not automatically added. They are invited by email from the [!DNL Experience Cloud] and must confirm their email addresses before their accounts are registered.

1. [In the Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), click **[!UICONTROL Products]**, then select the name of the desired product.

   ![Products tab](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Click the desired workspace (for example, Default Workspace).

   ![Default Workspace](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   The [!UICONTROL Users] tab displays all of the users in that workspace.

   ![configuration users](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Select the desired permissions role (Approver, Editor, or Observer) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   ![Product Role drop-down list](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Role | Description |
   |--- |--- |
   |Approver|Can create, edit, and activate or stop activities.|
   |Editor|Can create and edit activities before they are live, but cannot approve the launch of an activity. Can edit audiences in live activities.|
   |Observer|Can view activities, but cannot create or edit them.|
   |Publisher|Similar to the Observer role (can view activities, but cannot create or edit them). However, the Publisher role has the additional permission to activate activities.|

For more information, see [Manage Product Permissions and Roles in the Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) in the *Enterprise User Guide*.

## Training video: How to Configure Adobe Target Workspaces ![Tutorial badge](/help/main/assets/tutorial.png)

Learning objectives:

* Access the Adobe Admin Console from the Adobe Target interface (three ways)
* Configure a workspace in the Adobe Admin Console
    * Add users to workspaces
    * Add properties to workspaces
* Understand default workspaces

>[!NOTE]
>
>The [!DNL Target] [!UICONTROL Administration] menu UI (formerly [!UICONTROL Setup]) has been redesigned to provide improved performance, reduce the maintenance time required when releasing new features, and to improve the user experience across the product. The information in the following video is generally correct; however, options might be in slightly different locations. Updated videos will be posted soon.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
