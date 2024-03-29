---
description: Information about the tasks required to add users to your Target implementation;create
  workspaces, user groups, and properties;update your Target implementation to include
  the at_property parameter;and specify roles and permissions.
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
seo-description: Information about the tasks required to add users to your Target
  implementation;create workspaces, user groups, and properties;update your Target
  implementation to include the at_property parameter;and specify roles and permissions.
seo-title: Configure enterprise permissions
solution: Target
subtopic: Getting Started
title: Configure enterprise permissions
title-outputclass: premium
topic: Premium
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Configure enterprise permissions{#configure-enterprise-permissions}

Information about the tasks required to add users to your Target implementation;create workspaces, user groups, and properties;update your Target implementation to include the at_property parameter;and specify roles and permissions.

>[!NOTE]
>
>Properties and Permissions functionality is available as part of the [!DNL Target Premium] solution. They are not available in [!DNL Target Standard] without a [!DNL Target Premium] license.

The following table lists the tasks you should perform to create properties and assign user roles and permissions:

<table id="table_D3FFB40000DC4CBAA18B1D0E52D40565"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Performed In </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_A92AF0F921B743FEB9E9033433BD816A" format="dita" scope="local"> 1. Add Users (Optional) </a> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Admin Console for Enterprise </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_B82EB409B67C4D9D9D20CE30E48DB1DC" format="dita" scope="local"> 2. Create a Workspace (Product Profile) </a> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Admin Console for Enterprise </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_5F5CB9AA7A9F4D26953E22016DA59605" format="dita" scope="local"> 3. Create User Groups (Optional) </a> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Admin Console for Enterprise </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD" format="dita" scope="local"> 4. Create Properties </a> </p> </td> 
   <td colname="col2"> <p>Target UI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8" format="dita" scope="local"> 5: Update Your Implementation to Include the at_property Parameter </a> </p> </td> 
   <td colname="col2"> <p>Target UI / <span class="codeph"> at.js </span> functions / Dynamic Tag Management </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80" format="dita" scope="local"> 6: Specify Roles and Permissions </a> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Admin Console for Enterprise </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

For those tasks performed in the Adobe Admin Console for Enterprise, access the console by following these steps:

1. Go to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.

   Or

   If you are already logged in to the Experience Cloud, go to [https://www.marketing.adobe.com](https://www.marketing.adobe.com/), then click the [!UICONTROL App] icon in the top navigation bar > click **[!UICONTROL Administration]** on the right side > then click **[!UICONTROL Launch Admin Console]**.

1. (Conditional) If you have access to the [!DNL Admin Console for Enterprise] for more than one organization, click the user avatar in the right corner or the top navigation bar, then select the desired organization.

## Step 1. Add Users (Optional) {#section_A92AF0F921B743FEB9E9033433BD816A}

When you start using the new [!UICONTROL Properties] functionality, all user management must be performed in the [!DNL Adobe Admin Console for Enterprise]. However, all of your existing users in [!DNL Target] will be migrated from [!DNL Target] to the [!DNL Admin Console for Enterprise].

1. [In the Admin Console](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), click the **[!UICONTROL Users]** tab at the top of the page > **[!UICONTROL Users]** to create new users or to edit existing users.
1. Follow the instructions in [Manage Users and Groups in the Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) in the *Enterprise User Guide*.

## Step 2. Create a Workspace (Product Profile) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

A workspace (Product Profile) lets an organization assign a specific set of users to a specific set of properties. In many ways, a workspace is similar to a report suite in [!DNL Analytics].

Organizations can begin taking advantage of Enterprise permissions functionality by creating new workspaces within Admin Console, assigning Target properties to these workspaces, and moving users from the "Default Workspace" configuration to these newer, limited-access workspaces.

Customers can use these workspaces to separate access to different teams by region, by business unit, by sight section, or via any other method they choose.

Users can be part of multiple workspaces and can even have different roles within each workspace.

**How to Configure Target Workspaces (6:55)**

This video explains how to create workspaces.

* Access the Adobe Admin Console from the Adobe Target interface (3 ways)
* Configure a workspace in Adobe Admin Console

   * Add users to workspaces
   * Add properties to workspaces

* Understand default workspaces

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

1. In the Admin Console, click **[!UICONTROL Products]**, then select the name of the desired product.

   ![](assets/workspace.png)

1. Create the desired workspace (Product Profile):

   * **Default Access:** All existing activities will be merged into a single project called "Default Access." This will have no impact on customers. All user roles and functionality will remain exactly the same as they are prior to this change.

      All activities created via [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services], and [!DNL Target Classic] will also be part of the "Default Access" workspace. You cannot currently move projects from "Default Access" to another project.

   * **New workspaces (Product Profiles):** You can begin taking advantage of the new permissions functionality by doing the following:

      * Creating new workspaces within the [!DNL Admin Console for Enterprise].
      * Assigning Target properties to the workspaces.
   You can use these workspaces to divide access to different teams by region, business unit, site section, or via any other method you choose. Users can be part of multiple workspaces and can have different roles within each workspace.

1. Follow the instructions in [Create and Manage Product Configurations](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) in the *Enterprise User Guide*.

## Step 3. Create User Groups (Optional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

You can create user groups, such as Developers, Analysts, Marketers, Executives, etc., and then assign privileges across multiple Adobe products and workspaces. Assigning a new team member all the appropriate privileges across different Adobe products can be as easy as adding them to a specific user group.

1. In the Admin Console, click the **[!UICONTROL Users]** tab at the top of the page > **[!UICONTROL User Groups]** to create new user groups or to edit existing groups.
1. Follow the instructions in [Manage Users and Groups of a Product Configuration](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) in the *Enterprise User Guide*.

## Step 4. Create Properties {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

This video explains how to create properties (3:05).

* How to create a property within the [!DNL Adobe Target] interface
* How to generate a property token to include in your property implementation
* Familiarize yourself with the three implementation methods:

   * Web
   * Mobile app
   * Email, set top box, or API calls

>[!VIDEO](https://video.tv.adobe.com/v/18990/)

Properties are enabled by adding a specific name/value pair as a parameter with any call (mbox, api, etc.) to Target.

Properties belong to specific channels (Web, Mobile, Email, and API/Other).

1. In [!DNL Target], click **[!UICONTROL Setup]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.
1. Click **Create Property**.

   ![](assets/new_property.png)

   Fill in the fields:

   * **Channel:** Specify the desired channel for the property: Web, Mobile App, Email, or Other/API (for example a set-top box or PlayStation console).
   * **Name (Required):** Specify a descriptive name for the property.
   * **Description:** Specify an optional description for the property.

1. Click **[!UICONTROL Generate Code]** to generate the code you'll use while performing the steps in [5: Update Your Implementation to Include the at_property Parameter](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Copy the code to your clipboard.
1. Click **[!UICONTROL Save]** when done.

## Step 5: Update Your Implementation to Include the at_property Parameter {#section_9B17A59807A94712BE642942442EBBC8}

To use the [!DNL Target] user-permissions functionality, you must add the `at_property` parameter to any call that is hitting Target (mbox, api, etc.).

**To obtain the `at_property` parameter code:**

1. (Conditional) Use the implementation code you generated and saved to your clipboard while performing the steps in [4. Create Properties](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) and proceed to Step 2.

   Or

   In [!DNL Target], click **[!UICONTROL Setup]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.

   1. Hover your mouse pointer over the [!UICONTROL Last Updated] column for the desired property to display and click the [!UICONTROL Code] icon.

      ![](assets/code_property.png)

   1. Right-click the highlighted implementation code to copy it to your clipboard.

      ![](assets/code_property_2.png)

1. Update your Target implementation with the implementation code obtained in the previous step.

   There are several ways to update your [!DNL Target] implementation. For example, the following methods can be used for web pages:

   * **Via a "Global Parameter" in [!DNL Dynamic Tag Management] (Adobe Activation):**

      ![](assets/property_token_2.png)

      For more information, see [Global Parameters - Adobe Target](https://marketing.adobe.com/resources/help/en_US/dtm/target_global_params.html) in the *Dynamic Tag Management Product Documentation*.

   * **Via the targetPageParams() function:** Place the following code in the <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> tags, above the at.js or mbox.js reference.

      ![](assets/property_token_1.png)

      For more information about how to do this with at.js, see [targetPageParams()](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_B235C9F6DA79449ABE3E23F914FEABAE).

   * **Via the mboxCreate() function:**

      ![](assets/property_token_3.png)

      For more information about how to do this with at.js, see [targetPageParams()](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_B235C9F6DA79449ABE3E23F914FEABAE). [mboxCreate(mbox,params)](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_E68805FE86C64792B2066DB17B253D74)

## Step 6: Specify Roles and Permissions {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. In the Admin Console, click **[!UICONTROL Products]**, then select the name of the desired product.

   ![](assets/workspace.png)

   >[!NOTE]
>
>The Properties and Permissions functionality applies to [!DNL Target Standard/Premium] only. You cannot use this functionality with [!DNL Target Classic].

1. Click the name of the desired profile.
1. Click **[!UICONTROL Users]**.

   The [!UICONTROL Configuration Users] tab displays all of the users in that workspace.

   ![](assets/configuration_users.png)

1. Select the desired permissions role (Approver, Editor, or Observer) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   | Role | Description |
   |--- |--- |
   | Observer | Can view activities, but cannot create or edit them. |
   | Editor | Can create and edit activities before they are live, but cannot approve the launch of an activity. |
   | Approver | Can create, edit, and activate or stop activities. |

   For more information, see [Manage Product Permissions and Roles in the Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) in the *Enterprise User Guide*.
