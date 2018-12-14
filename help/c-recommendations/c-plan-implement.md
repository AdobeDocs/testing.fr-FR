---
description: What you need to know before creating a Recommendations activity.
keywords: Recommendations;settings;preferences;industry vertical;filter incompatible
  criteria;default host group;thumb base url;recommendation api token
seo-description: What you need to know before creating a Recommendations activity.
seo-title: Plan and Implement Recommendations
solution: Target
title: Plan and Implement Recommendations
title-outputclass: premium
topic: Premium
uuid: 37be7fb3-3686-4dec-9cca-478d28191985
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Plan and Implement Recommendations{#plan-and-implement-recommendations}

What you need to know before creating a Recommendations activity.

## Plan and Implement Recommendations {#concept_02AA644A4C7D4D5CB1D9CADA208CF8D1}

What you need to know before creating a [!DNL Recommendations] activity.

[!DNL Recommendations] requires that you set up the following hierarchy of information:

<table id="table_53E0DEF7F0204F9F9C8C8928D55B049E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Step </th> 
   <th colname="col2" class="entry"> Information </th> 
   <th colname="col3" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step1_red.png" id="image_079D053A075F427B85266AA9BACE95B8" /> </p> </td> 
   <td colname="col2"> <p>JavaScript library </p> </td> 
   <td colname="col3"> <p> Each page requires a reference to <span class="filepath"> at.js </span> version 0.9.1 (or later) or <span class="filepath"> mbox.js </span> version 55 (or later). This implementation step is required on all pages where a <span class="keyword"> Target </span> activity will be used, and can include keys such as a product or category ID. </p> <p>For information about <span class="filepath"> at.js </span>, see <a href="../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/c-target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17" format="dita" scope="local"> at.js Implementation </a>. </p> <p>For more information about <span class="filepath"> mbox.js </span>, see <a href="../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/t-mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420" format="dita" scope="local"> Mbox.js Implementation </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step2_red.png" id="image_8600F0A878A547F590F14959DE95D0D2" /> </p> </td> 
   <td colname="col2"> <p>Keys </p> </td> 
   <td colname="col3"> <p>The key determines the type of product or content that displays in your recommendations. For example, the key might be a product category. See <a href="../c-recommendations/c-algorithms/t-create-new-algorithm.md#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B" format="dita" scope="local"> Base the Recommendation on a Recommendation Key </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step3_red.png" id="image_9A3BE89D45F84FE09B8F8E7751470F83" /> </p> </td> 
   <td colname="col2"> <p>Attributes </p> </td> 
   <td colname="col3"> <p>Attributes provide more specific information about the products you want to display. For example, you might want to show products within a certain price range, or items that meet an inventory threshold. Attributes can be provided in the mbox or through a <a href="../c-recommendations/c-products/c-feeds.md#concept_1228B31E3D0B483B9DD42C5E2AE436E3" format="dita" scope="local"> feed </a>. </p> <p>See <a href="../c-recommendations/c-algorithms/t-create-new-algorithm.md#task_28DB20F968B1451481D8E51BAF947079" format="dita" scope="local"> Inclusion Rules </a> and <a href="../c-recommendations/c-products/r-entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F" format="dita" scope="local"> Entity Attributes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step4_red.png" id="image_933D0A2340CF423B8970DF4336F9C0C4" /> </p> </td> 
   <td colname="col2"> <p>Exclusions </p> </td> 
   <td colname="col3"> <p>Exclusions determine which specific items do not appear in your recommendations. </p> <p>See <a href="../c-recommendations/c-products/c-feeds.md#task_DD6D2F889E234F8C82B1604A3B315D81" format="dita" scope="local"> Exclusions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step5_red.png" id="image_5E83430D145948BDBB2C17D0F6C2B9A5" /> </p> </td> 
   <td colname="col2"> <p>Purchase deals </p> </td> 
   <td colname="col3"> <p>Purchase details provide information about purchased items and the order when the purchase has been completed. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Base Implementation {#concept_D1154A3FB0FB4467A29AD2BDD21C82D5}

The base implementation requires that you pass parameters to your page that determine which products or services appear in your recommendations.

<!-- 

recs/c_base_implementation.xml

 -->

Before you begin setting up a [!DNL Recommendations] activity, you should understand how product data is provided to [!DNL Recommendations], and decide which method works best for your needs.

There are two methods to provide information about products and services to [!DNL Recommendations]:

<table id="table_FCC3159B51BF43FA92F3658EDF7C7E1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pass parameters directly to the page </p> </td> 
   <td colname="col2"> <p>This method works well for items that change frequently. However, because it requires that changes be made directly to the page, in many organizations, this method requires the involvement of IT and the people who implement the pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pass parameters through a Google or CSV feed </p> </td> 
   <td colname="col2"> <p>This method works well for collections that do not change frequently. It is usually not necessary to change your mbox implementation or other page code to provide product information through a feed. However, the product list remains static, so quick changes are more difficult. For more information, see <a href="../c-recommendations/c-products/c-feeds.md#concept_1228B31E3D0B483B9DD42C5E2AE436E3" format="dita" scope="local"> Feeds </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

These methods can be used separately or together, as in the following examples.

## Example One: Combine Page and Feeds {#section_DF6BAE4BF11548BD9C44D0A426BCF5A7}

One common [!DNL Recommendations] implementation option uses both page parameters and feeds.

This method might be preferred by a retailer who has a relatively set product catalog, but who might want to emphasize specific seasonal items or items that are on sale. Most customers might provide their information primarily through the feed, with only occasional adjustments on the page.

Use a feed to provide information that will remain static. Whether using a CSV file or Google feed, use the following parameters:

* Required parameters

   * `entity.id`

* Helpful parameters

   * `entity.cust1`
   * `entity.cust2`
   * `entity.cust3`
   * All other attributes

Once the feed is set up and passed to [!DNL Recommendations], pass parameters on the page for items that are frequently changing.

* Required parameters

   * `entity.id`
   * `entity.categoryId`

* Helpful parameters

   * `entity.inventory`
   * `entity.value`

Priority is given to whichever set of data runs most recently. If you pass the feed first and then update the page parameters, changes that are made in the page parameters will be shown, replacing item information passed in the feed.

## Example Two: Pass All Parameters on the Product (or Content) Details Page {#section_D5A4F69457604CA7AACFD7BFF79B58A9}

If you pass all parameters on the page, you can quickly make updates by updating the page. In some organizations, this requires the involvement of IT or your Web Design team.

This example might be especially useful for a media company, with content that constantly changes.

* Required parameters

   * `entity.id`
   * `entity.categoryId`
   * All other attributes

## Sample Code {#section_6E8A73376F30468BB549F337C4C220B1}

For example, you can use the following code in the header section of your product or content pages:

```
function targetPageParams() { 
   return { 
      "entity": { 
         "id": " 
<i>32323</i>", 
         "categoryId": " 
<i>My Category</i>", 
         "value": 105.56, 
         "inventory": 329 
      } 
   } 
}
```

For more examples of the code you might use on different types of pages, see [Implementation According to Page Type](../c-recommendations/c-plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC).

## Implementation According to Page Type {#reference_DE38BB07BD3C4511B176CDAB45E126FC}

Page type will influence your [!DNL Recommendations] implementation.

<!-- 

recs/r_implementation_page_type.xml

 -->

For example, the types of recommendations you want to present may be different on a product page than on a category page or your home page. For each page, you can run specific functions prior to the mbox call to display the appropriate recommendations.

For information about the attributes in the examples, see [Entity Attributes](../c-recommendations/c-products/r-entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F).

Valid JSON formatting is required.

The `targetPageParams` function shown below is especially helpful if you are using a tag management solution to implement your pages. [!DNL Adobe Launch] or [!DNL Adobe Dynamic Tag Manager] (DTM) places the at.js/mbox.js reference and the `targetPageParams` function on your page and allows you to configure the values. You should either place that function before your at.js/mbox.js call, or put it in the Extra JavaScript section of your at.js/mbox.js.

## All Pages {#section_A22061788BAB42BB82BA087DEC3AA4AD}

All pages that contain recommendations require either an [!DNL at.js] or [!DNL mbox.js] reference on the page. Add one of the following references to all pages with recommendations:

```
<script src="../at.js /></script>
```

```
<script src="../mbox.js /></script>
```

This implementation requires:

* [!DNL at.js] version 0.9.2 (or later) or [!DNL mbox.js] version 55 (or later)

* [!DNL mbox.js] must include the reference to [!DNL target.js] ( [!DNL at.js] does not require a reference to [!DNL target.js])

For more information about implementing [!DNL at.js], see [How to Deploy at.js](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md#topic_ECF2D3D1F3384E2386593A582A978556).

For more information about implementing [!DNL mbox.js], see [Mbox.js Implementation](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/t-mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).

For more information about the differences between the two Target Javascript libraries, see [Understanding the Target JavaScript Libraries](../c-implementing-target/c-considerations-before-you-implement-target/c-target-implement.md#concept_60B748DE4293488F917E8F1FA4C7E9EB).

## Category Page {#section_F51A1AAEAC0E4B788582BBE1FEC3ABDC}

On a category page, you probably want to restrict your recommendations to products or content within that category. To set up a category page, you set up the keys used by the page. For more information about keys, see [Base the Recommendation on a Recommendation Key](../c-recommendations/c-algorithms/t-create-new-algorithm.md#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B).

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": " 
<i>My Category</i>" 
      } 
   } 
}
```

## Product Page {#section_205B3953C9664125A17CA8574FA6B2A3}

On a product page, you might want to recommend specific items, or items with a particular price or inventory level. For a product page, you might need to set up frequently changing attributes (such as value and inventory), in addition to the keys required for a category page.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "id": " 
<i>32323</i>", 
         "categoryId": " 
<i>My Category</i>", 
         "value": 105.56, 
         "inventory": 329 
      } 
   } 
}
```

## Cart Page {#section_D37E48700F074556B925D0CA0291405E}

On a cart page, you likely want to exclude some items from your recommendations, such as the items that are already in the cart.

```
<script type="text/javascript"> 
function targetPageParams() { 
   return { 
      "excludedIds": [352, 223, 23432, 432, 553] 
      } 
} 
</script>
```

## Thank You Page {#section_C6126A4517A1478693AB7EC2A1D4ACCA}

On the Thank You page, you might want to show the order total, and the order ID, and show the products that were purchased, without recommending additional items. You can implement a second mbox to capture the order information.

* If you are using at.js, see [Track Conversions](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
* If you are using mbox.js, see [Create an Order Confirmation mbox - mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/t-orderconfirm-create.md#task_0036D5F6C062442788BB55E872816D82).

## Settings {#concept_C1E1E2351413468692D6C21145EF0B84}

Use settings to manage your [!DNL Recommendations] implementation.

<!-- 

recs/c_setup.xml

 -->

To access the [!UICONTROL Recommendations Settings] options, open [!DNL Target] in the [!DNL Adobe Experience Cloud], then click **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

![](assets/recs_settings.png)

The following options are available:

<table id="table_64B65F53C8904026BD4031E749AA3625"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Custom Global Mbox </p> </td> 
   <td colname="col2"> <p>(Optional) Specify the custom global mbox used to serve <span class="keyword"> Target </span> activities. By default, the global mbox used by <span class="keyword"> Target </span> is used for <span class="keyword"> Recommendations </span>. </p> <p> <p>Note:  This option is set on the <span class="wintitle"> Target Setup </span> page. Open <span class="keyword"> Target </span>, then click <span class="uicontrol"> Setup </span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Industry Vertical </p> </td> 
   <td colname="col2"> <p>The industry vertical is used to help categorize your recommendations criteria. This helps members of your team find criteria that make sense for a particular page, such as criteria that are best for the shopping cart page or for a media page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filter Incompatible Criteria </p> </td> 
   <td colname="col2"> <p>Enable this option to show only those criteria where the selected page passes the required data. Not every criteria will run correctly on every page. The page or mbox needs to pass in <span class="codeph"> entity.id </span> or <span class="codeph"> entity.categoryId </span> for the current item/current category recommendations to be compatible. In general, it is best to show only compatible criteria. However, if you want incompatible criteria to be available for the activity, uncheck this option. </p> <p> It is recommended that you disable this option if using a tag management solution. </p> <p>For more information about this option, see <a href="../c-recommendations/c-recommendations-faq/c-recommendations-faq.md#concept_EF272DE4AC6C47B19026BFBE816F5DB8" format="dita" scope="local"> Recommendations FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Host Group </p> </td> 
   <td colname="col2"> <p>Select your default host group. None means that your <span class="wintitle"> Default Host Group for Reporting </span> setting in <span class="keyword"> Target Classic </span> is used for your default host group. </p> <p>The host group provides the environment where the products are hosted. You can only preview from one given host group at a time. The numbers and update information that show in the Collection list all come from that host group. Likewise, the delivery depends on your host group. </p> <p>If you don't see your products, make sure that you are using the correct host group. For example, if you set up your recommendation to use a staging environment and you set your host group to Staging, you might need to re-create your collections in the staging environment for the products to show. </p> <p>To see which products are available in each environment, use Catalog Search with each environment. </p> <p>For more information about host groups, see <a href="../administrating-target/c-hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E" format="dita" scope="local"> Hosts </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Thumbnail Base URL </p> </td> 
   <td colname="col2"> <p>Setting a base URL for your product catalog makes it possible to use relative URLs when specifying thumbnails of your products when passing in your thumbnail URL. </p> <p>For example: </p> <p> <span class="codeph"> "entity.thumbnailURL=/Images/Homepage/product1.jpg" </span> </p> <p>sets a URL relative to the thumbnail base URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recommendation API Token </p> </td> 
   <td colname="col2"> <p>Use this token in Recommendations API calls, such as the Download API. </p> </td> 
  </tr> 
 </tbody> 
</table>

