---
description: Information about using enterprise customer data from a customer relationship
  management (CRM) databases for content targeting in Adobe Target by using Customer
  Attributes in the Adobe Profiles & Audiences core service.
keywords: customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting
seo-description: Information about using enterprise customer data from a customer
  relationship management (CRM) databases for content targeting in Adobe Target by
  using Customer Attributes in the Adobe Profiles & Audiences core service.
seo-title: Customer attributes
solution: Target
subtopic: Getting Started
title: Customer attributes
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Customer attributes{#customer-attributes}

Information about using enterprise customer data from a customer relationship management (CRM) databases for content targeting in Adobe Target by using Customer Attributes in the Adobe Profiles & Audiences core service.

Enterprise customer data collected through multiple sources and stored inside a CRM database can be used in [!DNL Target] to strategically deliver the most relevant content to customers, specifically focusing on returning customers. The [!DNL People] core service (formerly Profiles and Audiences) brings together data collection and analysis with testing and optimization, making data and insights actionable.

## Customer Attributes Overview {#section_B4099971FA4B48598294C56EAE86B45A}

The People core service is part of the [!DNL Adobe Experience Cloud] and provides enterprises a tool to push their customer data to the [!DNL Experience Cloud] platform. Data onboarded to the [!DNL Experience Cloud] is available for all [!DNL Experience Cloud] workflows. [!DNL Adobe Target] utilizes this data for targeting returning customer based on attributes. [!DNL Adobe Analytics] consumes these attributes and they can be used for analysis and segmentation.

![](assets/crs.png)

Consider the following information as your work with customer attributes and Target:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer Attributes] feature in the [!DNL People] core service. For more information, see "Prerequisites for Uploading Customer Attributes" in [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) in the *Experience Cloud and Core Services Product Documentation*. Note that [!DNL at.js] (any version) or [!DNL mbox.js] version 58 or later is required.
* Adobe does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the Experience Cloud and thus be available for use for targeting in Target. In our current design, there is a possibility that a small percentage of data might not be onboarded.
* The lifetime of customer attributes data imported from the Experience Cloud to Target depends on the lifetime of the visitor profile, which is 14 days by default. For more information, see [Visitor Profile Lifetime](../../c-target/c-visitor-profile/c-visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* If the `vst.*` parameters are the only thing identifying the user, the existing "authenticated" profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will only come into play if `authState` is changed to UNAUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the user (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won't fetch the profile that might have been created through a Customer Attributes import. If the desired behavior is to fetch the authenticated profile, the `vst.myDataSource.authState` has to have the value of 1 (AUTHENTICATED).

## Customer Attribute Workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Complete the following steps to use CRM data in [!DNL Target], as illustrated below:

![](assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a Customer Attribute Source and Upload the Data File](https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html) in the *Experience Cloud and Core Services Product Documentation*.

1. Create a data file.

   Export customer data from your CRM to CSV format to create a [!DNL .csv] file. Alternately, a zip or gzip file can be created for uploading. Ensure that first row of CSV is the header and all rows (customer data) have the same number of entries.

   ![](assets/CRS_sample.png)

   ![](assets/CRS_CSV_sample.png)

1. Create the attribute source and upload the data file.

   Specify a Name and Description of the data source and the alias Id. The alias Id is a unique ID to be used in your Customer Attribute code in VisitorAPI.js.

   >[!IMPORTANT]
>
>The data source name and the attribute name cannot contain a period.

   Data files up to 100 MB can be uploaded using the HTTP method. Files larger than 100 MB, up to 4 GB can be uploaded through FTP.

   * **HTTPS: **You can drag-and-drop the [!DNL .csv] data file or click [!UICONTROL Browse] to upload from your file system.
   * **FTP: **Click on FTP link to [upload file through FTP](https://marketing.adobe.com/resources/help/en_US/mcloud/t_upload_attributes_ftp.html). First step is to provide a password for the Adobe-provided FTP server. Enter the password, then click [!UICONTROL Done].

      Now transfer your CSV/ZIP/GZIP file to the FTP server. Once this file transfer is successful, create a new file with same name and [!DNL .fin] extension. Transfer this empty file to the server. This indicates a End Of Transfer and the Experience Cloud starts to process data file.

1. Validate the schema.

   The validation process lets you map display names and descriptions to uploaded attributes (strings, integers, numbers, and so on). Map each attribute to its correct data type, display name, and description.

   Click [!UICONTROL Save] after schema validation is complete. The file upload time varies depending on the size.

   ![](assets/SchemaValidate.png)

   ![](assets/upload1.png)

1. Configure subscriptions and activate the attribute source.

   Click **[!UICONTROL Add Subscription]**, then select the solution to subscribe these attributes. [Configuring a subscription](https://marketing.adobe.com/resources/help/en_US/mcloud/subscription.html) sets up the data flow between the Experience Cloud and solutions. Activating the attribute source allows the data to flow to subscribed solutions. The customer records you have uploaded are matched up with incoming ID signals from your website or application.

   ![](assets/solution.png.jpeg)

   ![](assets/activate.PNG)

   While performing this step, be aware of the following limitations:

   * The maximum file size for each upload using the HTTP method is 100 MB.
   * The maximum file size for each upload using the FTP method is 4 GB.
   * The number of attributes allowed to subscribe: 5 for [!DNL Target Standard] and 200 for [!DNL Target Premium].

## Use Customer Attributes in Target {#section_107E3A0F0EC7478E82E6DBD17B30B756}

You can use customer attributes in [!DNL Target] in the following ways:

<table id="table_96AB5A9C2F17437489DF4C42642EB6D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Creating targeting audiences </p> </td> 
   <td colname="col2"> <p>In <span class="keyword"> Target </span>, you can select a customer attribute from the <span class="wintitle"> Visitor Profile </span> section when creating an audience. All customer attributes have the prefix &lt; <span class="varname"> data_source_name </span>> in the list. Combine these attributes as required with other data attributes to build audiences. </p> <p> <img href="assets/TargetAudience.png" id="image_00473D9BBCE843DAB2C1736FE52CB3DE" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creating profile scripts using tokens </p> </td> 
   <td colname="col2"> <p>Customer attributes can be referenced in profile scripts using format <span class="codeph"> crs.get('&lt;Datasource Name>.&lt;Attribute name>') </span>. </p> <p>This profile script can be used directly in offers for delivering attributes that belong to the current visitor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Using <span class="codeph"> mbox3rdPartyID </span> in your website for a successful implementation and usage </p> </td> 
   <td colname="col2"> <p>Pass <span class="codeph"> mbox3rdPartyId </span> as a parameter to the global mbox inside the <span class="codeph"> targetPageParams() </span> method. The value of <span class="codeph"> mbox3rdPartyId </span> should be set to the customer ID that was present in CSV data file. </p> 
    <codeblock>
      &lt;script type="text/javascript">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function&nbsp;targetPageParams()&nbsp;{

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;'mbox3rdPartyId=2000578';

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}

&lt;/script&gt;
</codeblock> </td>
</tr> 
  <tr> 
   <td colname="col1"> <p>Using the Experience Cloud ID Service </p> </td> 
   <td colname="col2"> <p>If you are using the Experience Cloud ID service, you need to set a Customer ID and Authentication State to use customer attributes in targeting. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html" format="html" scope="external"> Customer IDs and Authentication State </a> in the <i>Experience Cloud ID Service Documentation</i>. </p> </td> 
  </tr> 
 </tbody> 
</table>

For more information about using customer attributes in [!DNL Target], see the following resources:

* [Create a Customer Attribute Source and Upload the Data File](https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html) in the *Experience Cloud and Core Services Product Documentation*
* [Customer Attributes: The More You Know, The Better You Connect](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) in the *Digital Marketing Blog*

## Issues Frequently Encountered by Customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

You might encounter the following issues when working with customer attributes and [!DNL Target]:

<table id="table_4635ECDB7D1A4023A889A9CEC639B360"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Issue </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Customer attributes are removed because the profile is too large </p> </td> 
   <td colname="col2"> <p>There is no character limit on a particular field in the user's profile, but if the profile gets larger than 64K, it is truncated by removing the oldest attributes until the profile is below 64K again. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attributes not listing in the Audience Library in <span class="keyword"> Target </span>, even after several days </p> </td> 
   <td colname="col2"> <p>This is usually a Pipeline connection problem. As a resolution, ask your Customer Attributes team to republish the feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Delivery not working based on the attribute </p> </td> 
   <td colname="col2"> <p>The profile has not been updated on the edge yet. As a resolution, ask your Customer Attributes team to republish the feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Implementation issues </p> </td> 
   <td colname="col2"> <p>Be aware of the following implementation issues: </p> <p> 
     <ul id="ul_5CCB01F625D94208AC7F7B57E38DB0A6"> 
      <li id="li_2D2106650BC444328DF526BEB0C69690"> <p>The Visitor Id was not passed correctly. The ID was passed in <span class="codeph"> mboxMCGVID </span> instead of <span class="codeph"> setCustomerId </span>. </p> </li> 
      <li id="li_7B7A1F2F47E641718A8D5C203DF871BB"> <p>The Visitor Id was passed correctly, but the AUTHENTICATION state was not set to Authenticated. </p> </li> 
      <li id="li_C0A232B444274463988DDF977BC651FB"> <p> <span class="codeph"> mbox3rdPartyId </span> was not passed correctly. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> mboxUpdate </span> not performed properly </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> mboxUpdate </span> was not performed properly with <span class="codeph"> mbox3rdPartyId </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer attributes are not being imported into Target. </p> </td> 
   <td colname="col2"> <p>If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last <i>x</i> days where <i>x</i> is the Target <a href="../../c-target/c-visitor-profile/c-visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD" format="dita" scope="local"> Visitor Profile Lifetime </a> value (14 days by default). </p> </td> 
  </tr> 
 </tbody> 
</table>

Issues in rows 1 and 2 above cause approximately 60% of problems in this area. Issues in row 3 cause approximately 30% of problems. The issue in row 4 causes approximately 5% of problems. The remaining 5% are due to miscellaneous issues.

## Video: Upload Offline Data using Customer Attributes (6:52) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

This video shows yo how to import offline CRM, help desk, point-of-sale, and other marketing data into the Experience Cloud People service and associate it with visitors using their known IDs.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
