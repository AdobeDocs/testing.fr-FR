---
description: learn about new features and fixes in the adobe marketing cloud.
keywords: release notes
seo-description: learn about new features and fixes in the adobe marketing cloud.
seo-title: release notes - may 2015
title: release notes - may 2015
index: y
internal: n
snippet: y
translate: y
matt: lawrence
translation-type: tm+mt
source-git-commit: 46db681c02a7f84047de486d99b1054fe5a931cc
Translated: 'false'

---

# Table Tests

## Experience Manager Code in Tables

<table> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/models</span></td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/workflow/models</span></p> <p><span class="code">/conf/global/settings/workflow/models</span></p> <p><span class="code">/var/workflow/models</span></p> </td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Workflow Models must be migrated to /conf/global/workflow/models.</p> 
    <ol> 
     <li>Deploy the modified Workflow Models into a local AEM 6.4 development instance, such that they exist in the Previous location.</li> 
     <li>Edit the Workflow Model using AEM's Workflow Model Editor at AEM > Tools > Workflow > Models.</li> 
     <li>When migrating modified AEM-provided Workflow Models
      <ol> 
       <li>With the Workflow Model Editor open, modify the browser's address URL, and replace the path segment /libs/settings/workflow/models with /etc/workflow/models.
        <ul> 
         <li>For example, change: <em>http://localhost:4502/editor.html<strong>/libs/settings/workflow/models</strong>/dam/update_asset.html</em> to <em>http://localhost:4502/editor.html<strong>/etc/workflow/models</strong>/dam/update_asset.html</em></li> 
        </ul> </li> 
      </ol> </li> 
     <li>Enable Edit mode in the Workflow Model Editor which will copy the Workflow Model definition to /conf/global/workflow/models.</li> 
     <li>Tap the Sync button to sync the changes to the Runtime Workflow Model under /var/workflow/models.</li> 
     <li>Export both the Workflow Model (/conf/global/workflow/models/&lt;workflow-model>) and Runtime Workflow Model (/var/workflow/models/&lt;workflow-model>) and integrate into the AEM project.
      <ol> 
       <li>For example, export:
        <ul> 
         <li><span class="code">/config/settings/workflow/models/dam/my_workflow_model</span><br /> and </li> 
         <li><span class="code">/var/workflow/models/dam/my_workflow_model</span></li> 
        </ul> </li> 
      </ol> </li> 
    </ol> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td><p>Workflow Model resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/conf/global/settings/workflow/models</span></li> 
     <li><span class="code">/libs/settings/workflow/models</span></li> 
     <li><span class="code">/etc/workflow/models</span></li> 
    </ol> <p>Thus, any customizations of AEM-provided Workflow Models persisted in the Previous location must be moved to /conf/global/settings/workflow/models if they are to be retained, otherwise they will be superseded by the AEM-provided Workflow Model definition in /libs/settings/workflow/models.</p> </td> 
  </tr>
 </tbody>
</table>


## Sign in and manage your profile settings

>[!NOTE]
>
>You must encode any URL before passing it to the `destURL` parameter. (Encoder sites like [URL Decoder / Encoder](https://meyerweb.com/eric/tools/dencoder/) are available.)


## Core Services Table With URL and one long cell

| Parameter | Description | Example | Required / Optional |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|------------------------------------|
| tenantId | Name of the tenant the user should log into. | aem62tenant | Optional |
| destURL | The complete URL to the place where the user should be taken to. | https://sc.omniture.com/x/1_7xxzf | Optional |
| solutionname | Name of the MAC Solution that is the owner of destURL parameter. It is used to verify that the user has access to the solution which is the owner of the URL.  It is the responsibility of the solutions to make sure that the solutionname is in Sync with the destURL parameter.  For example : If the URL contains solutionname as social and the destURL provided is an analytics url, then the user would be redirected to the url even if he doesn't have access to analytics. MAC does NOT verify weather the owner of the destURL is in sync with the solution name. | analytics | Required if destURL param is used. |


## Big Table  with many cols

| Product Name & Help Link | Analysis Workspace | Reports & Analytics | Ad Hoc Analysis | Report Builder | Data Warehouse | Data Workbench |
|------------------------|------------------|-------------------|---------------|--------------|--------------|--------------|
| Access Method | Browser solution for building robust,custom analysis projects, and democratizing insights. | Browser solution for digital analysis. | Java based tool for advanced digital analysis. | Excel add-in that lets you build customized requests from R&A data, and visualize using Microsoft Excel. | Browser solution that generates reports in .csv format. Can generate Tableau format files. | Multi-channel analytics tool for advanced analysis, such as custom attribution modeling, predictive analytics, and 360 customer analysis. |
| Report Breakdowns | Unlimited | Up to 2 correlations | Unlimited | Up to 2 correlations | Performs fully expanded, unlimited breakdowns, break down by segment. | Unlimited |
| Segment Comparisons | Unlimited | Up to 2 segments | Unlimited | Unlimited (data request stacking) | 1 segment. Supports multiple (stacked) segments. | Unlimited |
| Row Output Limit | 400 | 200 | 50,000 | 50,000 | Unlimited | Customizable |
| Unique Value Limits (within eVar/ prop reports) | 500K-2MM | 500K-2MM | 500K-2MM | 500K-2MM | Unlimited | Customizable |
| Funnel/Pathing | Yes Fallout Flow | Yes | Yes | Yes | No | Yes |
| Advanced Customer Journey Analysis | Planned | No | Yes | No | No | Yes |
| Cohort Analysis | Yes | No | No | No | No | Yes |
| Advanced Attribution | Limited currently - first/last/linear | Limited - first/last/linear | Limited - first/last/linear | Limited - first/last/linear | Limited - first/last/linear | Yes |
Learn about new features and fixes in the Adobe Marketing Cloud.

>[!NOTE]
>
>To receive release notes one week prior to the monthly product update, subscribe to the[Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html). Release information in the Priority Product Update comes one week in advance of the release date and is subject to change. Please check back at release time for updates.

<!-- <p>This file is the template for the monthly RNs. To update all links, open this file in notepad++, search for <span class="filepath"> 05212015 </span> and replace all occurrences with the current file name (usually release date). When adding content, edit only the tables and Fixes ULs. Do not overwrite Concepts, Sections, or the topic maps ULs. </p> -->
May 2015

## Sample Markdown Table with small cols

| Hello | There |
|---|---|
| a | b |


## Markdown Table with embedded lists and breaks

| Feature | Description |
| --- | --- |
| Something goes here... | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions.  Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. |


## Markdown Table with Images and three cols almost identical to test balancing

| Feature | Description | Description2 | Description 3 |
| --- | --- | --- | --- |
| Something goes here... | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. ![Warning](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. <br>![Warning](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) <br> Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. | The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. ![Warning](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) Notable changes include: <ol> <li>The Audience Library and Customer Attributes menu selections are now located under Audiences . </li> <li>The  Exchange menu selection was moved from the Help drop-down menu to the left navigation rail. </li><li> Solutions has been removed. You can launch all solutions from the bottom half of the navigation rail. </li></ol><br>See [About Core Services and Solutions](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) for descriptions of the selections in the lefthand navigation menu. |


## Simple HTML Table

<table>
<tr>
<td>
hello
</td>
<td>
there
</td>
</tr>
<tr>
<td>
</td>
<td>
This<br>is<br>a<br>test
</td>
</tr>
</table>

## HTML Table Feature/Description

<table id="table_14E7B35E06C84A258A21D09691B58354"> 
 <thead> 
  <tr> 
   <th colname="col1" > Feature </th> 
   <th colname="col2" > Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Something goes here...</p> </td> 
   <td colname="col2"> <p>The left navigation menus have been updated and arranged to provide access to all of the core services and solutions. Notable changes include: </p> 
    <ul id="ul_5BEBAB86B9234A239C4E2DAF8826D8E3"> 
     <li id="li_7FA9F64CE69144B8A8A92746BF40E5A1">The <span class="term"> Audience Library </span> and <span class="term"> Customer Attributes </span> menu selections are now located under <span class="term"> Audiences </span>. </li> 
     <li id="li_95D62A43AE6243DBB2A65EDB830D05C4">The <span class="term"> Exchange </span> menu selection was moved from the Help drop-down menu to the left navigation rail. </li> 
     <li id="li_0443FD50C78446CD8AA27A4F272CAD31"> <span class="term"> Solutions </span> has been removed. You can launch all solutions from the bottom half of the navigation rail. </li> 
    </ul> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names" format="https" scope="external"> About Core Services and Solutions </a> for descriptions of the selections in the lefthand navigation menu. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* Fixed an issue preventing customer attributes from syncing for some customers.
* Fixed an issue preventing [Adobe Target Product Documentation](https://marketing.adobe.com/resources/help/ja_JP/target/a4t/) page from displaying in Japanese.
* Fixed an issue preventing the use of Japanese text in comments between the [!DNL  Creative Cloud] and the [!DNL  Marketing Cloud].

See [Marketing Cloud Product Documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/) for product help.


