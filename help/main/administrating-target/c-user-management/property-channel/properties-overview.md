---
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
description: Learn how to add users to Adobe Target; create workspaces, user groups, and properties; update your implementation; and specify roles and permissions.
title: How Do I Configure Enterprise Permissions?
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
---
# ![PREMIUM](/help/main/assets/premium.png) Configure enterprise permissions

Information about the tasks required to add users to your [!DNL Target] implementation; create workspaces, user groups, and properties; update your [!DNL Target] implementation to include the `at_property` parameter; and specify roles and permissions.

>[!NOTE]
>
>Properties and Permissions functionality is available as part of the [Target Premium](/help/main/c-intro/intro.md#premium) solution. They are not available in [!DNL Target Standard] without a [!DNL Target Premium] license.

The following table lists the tasks you should perform to create properties and assign user roles and permissions. Refer to the sections below for more information about each task.

| Task | Performed In |
|--- |--- |
|1. Add users (optional)|[!DNL Adobe Admin Console for Enterprise]|
|2. Create a workspace (product profile)|[!DNL Adobe Admin Console for Enterprise]|
|3. Create user groups (Optional)|[!DNL Adobe Admin Console for Enterprise]|
|4. Create properties|[!DNL Target] UI|
|5: Update your implementation to include the `at_property` parameter|[!DNL Target] UI, at.js functions, or tags in [!DNL Adobe Experience Platform]|
|6: Specify Roles and Permissions|[!DNL Adobe Admin Console for Enterprise]|

For those tasks performed in the [!DNL Adobe Admin Console for Enterprise], access the console by following these steps:

1. In Adobe Target, click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** > **[!UICONTROL Assign Properties to Workspaces]**.

   Or

   Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.


1. (Conditional) If you have access to the [!DNL Admin Console for Enterprise] for more than one organization, click the user avatar in the right corner or the top navigation bar, then select the desired organization.

## Step 1. Add users (Optional) {#section_A92AF0F921B743FEB9E9033433BD816A}

When you start using the new [!UICONTROL Properties] functionality, all user management must be performed in the [!DNL Adobe Admin Console for Enterprise]. However, all of your existing users in [!DNL Target] will be migrated from [!DNL Target] to the [!DNL Admin Console for Enterprise].

1. [In the Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), click the **[!UICONTROL Users]** tab at the top of the page > **[!UICONTROL Add Users]** to create new users or to edit existing users. 
1. Follow the instructions in [Manage Users and Groups in the Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) in the *Enterprise User Guide*.

## Step 2. Create a workspace (product profile) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

A workspace (product profile) lets an organization assign a specific set of users to a specific set of properties. In many ways, a workspace is similar to a report suite in [!DNL Analytics].

Organizations can begin taking advantage of Enterprise permissions functionality by creating new workspaces within [!DNL Admin Console], assigning [!DNL Target] properties to these workspaces, and moving users from the "Default Workspace" configuration to these newer, limited-access workspaces.

Customers can use these workspaces to separate access to different teams by region, by business unit, by site section, or via any other method they choose.

Users can be part of multiple workspaces and can even have different roles within each workspace.

1. In the [!DNL Admin Console], click **[!UICONTROL Products]**, then select the name of the desired product.

   ![workspace](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Create the desired workspace (Product Profile):

    * **Default Access:** All existing activities will be merged into a single project called "Default Access." This will have no impact on customers. All user roles and functionality will remain exactly the same as they are prior to this change.

      All activities created via [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services], and [!DNL Target Classic] will also be part of the "Default Access" workspace. You cannot currently move projects from "Default Access" to another project. 
    
    * **New workspaces (Product Profiles):** You can begin taking advantage of the new permissions functionality by doing the following:

        * Creating new workspaces within the [!DNL Admin Console for Enterprise]. 
        * Assigning Target properties to the workspaces.

   You can use these workspaces to divide access to different teams by region, business unit, site section, or via any other method you choose. Users can be part of multiple workspaces and can have different roles within each workspace.

1. Follow the instructions in [Create and Manage Product Configurations](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) in the *Enterprise User Guide*.

>[!NOTE]
>See the training video below for more information about configuring workspaces.

### Obtain your workspace ID {#workspace-id}

You'll need to pass the workspace ID to leverage Enterprise Permissions in [Target APIs](https://developer.adobe.com/target/implement/server-side/){target=_blank}.

1. In the [Adobe Admin Console](https://adminconsole.adobe.com), click the [!UICONTROL Products] tab, then click the product in the left menu to display the PLC(workspace) list.
1. Click the desired PLC(workspace), then locate the "profiles" ID in the URL, as shown below.

   ![workspaceID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Step 3. Create user groups (Optional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

You can create user groups, such as Developers, Analysts, Marketers, Executives, etc., and then assign privileges across multiple Adobe products and workspaces. Assigning a new team member all the appropriate privileges across different Adobe products can be as easy as adding them to a specific user group.

1. In the Admin Console, click the **[!UICONTROL Users]** tab at the top of the page > **[!UICONTROL User Groups]** to create new user groups or to edit existing groups. 
1. Follow the instructions in [Manage Users and Groups of a Product Configuration](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) in the *Enterprise User Guide*.

## Step 4. Create properties {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Properties are enabled by adding a specific name/value pair as a parameter with any call (Target call, api call, etc.) to Target.

Properties belong to specific channels (Web, Mobile, Email, and API/Other).

**Tip**: See the training video below for more information about how to create properties.

1. In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list. 
1. Click **Create Property**.

   Fill in the fields:

    * **Property Name (Required):** Specify a descriptive name for the property.
    * **Description:** Specify an optional description for the property.
    * **Channel:** Select the desired channel for the property: Web, Mobile App, Email, or Other/API (for example a set-top box or PlayStation console). 

1. Click **[!UICONTROL Copy]** to copy the code to your clipboard that you'll use while performing the steps in [5: Update Your Implementation to Include the at_property Parameter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Click **[!UICONTROL Save]** when done.

>[!NOTE]
>See the training video below for more information about creating properties.

## Step 5: Update your implementation to include the at_property parameter {#section_9B17A59807A94712BE642942442EBBC8}

To use the [!DNL Target] user-permissions functionality, you must add the `at_property` parameter to any call that is hitting [!DNL Target] (Target call, api call, etc.).

**To obtain the `at_property` parameter code:**

1. (Conditional) Use the implementation code you generated and saved to your clipboard while performing the steps in [4. Create Properties](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) and proceed to Step 2.

   Or

   In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.

    1. Hover your mouse pointer over the [!UICONTROL Last Updated] column for the desired property to display and click the [!UICONTROL Code] icon.

       ![Property hover code](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

    1. Right-click the highlighted implementation code to copy it to your clipboard.

1. Update your [!DNL Target] implementation with the implementation code obtained in the previous step.

   There are several ways to update your [!DNL Target] implementation. For example, the following methods can be used for web pages:

    * **Via a “Custom Parameter” in tags within [!DNL Adobe Experience Platform]:**

      For more information, see [Add Mbox Params](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=en#add-mbox-params) in the *Tags overview* documentation.
    
    * **Via the targetPageParamsAll() function:** Place the following code in the `<head>` tags, above the at.js reference.

      ```javascript
      <script>
       function targetPageParamsAll() {
        return {
         "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
        };
       }
      </script>
      ```

      For more information about how to do this with at.js, see [targetPageParamsAll](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/){target=_blank}. 

## Step 6: Specify roles and permissions {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. In the Admin Console, click **[!UICONTROL Products]**, then select the name of the desired product.

   ![Workspace](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Click the name of the desired profile (for example, Default Workspace).

   ![Default Workspace](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Click **[!UICONTROL Users]**.

   The [!UICONTROL Users] tab displays all of the users in that workspace.

   ![configuration users](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Select the desired permissions role (Approver, Editor, Observer, or Publisher) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   ![Product Role drop-down list](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Role | Description |
   |--- |--- |
   |Approver|Can create, edit, and activate or stop activities.|
   |Editor|Can create and edit activities before they are live, but cannot approve the launch of an activity.|
   |Observer|Can view activities, but cannot create or edit them.|
   |Publisher|Similar to the Observer role (can view activities, but cannot create or edit them). However, the Publisher role has the additional permission to activate activities.|

   For more information, see [Manage Product Permissions and Roles in the Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) in the *Enterprise User Guide*.

## Training videos

The following videos contain more information about the concepts discussed in this article.

>[!NOTE]
>
>The [!DNL Target] [!UICONTROL Administration] menu UI (formerly [!UICONTROL Setup]) has been redesigned to provide improved performance, reduce the maintenance time required when releasing new features, and to improve the user experience across the product. The information in the following videos is generally correct; however, options might be in slightly different locations. Updated videos will be posted soon.

### How to Configure Adobe Target Workspaces (6:55) ![Tutorial badge](/help/main/assets/tutorial.png)

This video explains how to create workspaces.

* Access the Adobe Admin Console from the Adobe Target interface (3 ways) 
* Configure a workspace in Adobe Admin Console

  * Add users to workspaces 
  * Add properties to workspaces

* Understand default workspaces

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### How to Create Properties in Adobe Target (3:05) ![Tutorial badge](/help/main/assets/tutorial.png)

* How to create a property within the [!DNL Adobe Target] interface 
* How to generate a property token to include in your property implementation 
* Familiarize yourself with the three implementation methods:

  * Web 
  * Mobile app 
  * Email, set top box, or API calls

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
