---
description: Use entity attributes to pass product or content information to Recommendations.
keywords: entity attributes;pass information to Recommendations;behavioral data;data
  counter;define relative URL;display inventory level;define price;define profit margin;custom
  attributes
seo-description: Use entity attributes to pass product or content information to Recommendations.
seo-title: Entity attributes
solution: Target
title: Entity attributes
title-outputclass: premium
topic: Premium
uuid: 27672881-a79c-4271-9a61-defddb9a5249
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Entity attributes{#entity-attributes}

Use entity attributes to pass product or content information to Recommendations.

The following table describes the available variables.

<table id="table_2F24AB9862FE4D94BFD91F910F436BA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Entity Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.id </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>This required parameter identifies the product. This alphanumeric ID must be the same across all Adobe Experience Cloud products that are used, including Analytics, for the various products to recognize the item and share data about it. </p> <p> <span class="codeph"> entity.id </span> values must not contain slashes, ampersands, question marks, percentage symbols, or punctuation characters that requiring URL encoding. Hyphens and underscores are permitted. Including invalid punctuation in an <span class="codeph"> entity.id </span> value causes some Recommendations functionality to fail. </p> <p>Example: </p> <p> 
     <code>
       'entity.id=67833' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.name </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>The product name that is displayed on the Web site when the product is recommended. </p> <p>Example: </p> <p> 
     <code>
       'entity.name=Giants&amp; vs&amp; Rockies&amp; 5/12' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.categoryId </span> </p> <p>Supports multi-value (comma-delimited list). </p> </td> 
   <td colname="col2"> <p>Category of the current page. This can include multiple categories, such as a cardigans sub-subsection (i.e. <span class="codeph"> womens </span>, <span class="codeph"> womens:sweaters </span>, <span class="codeph"> womens:sweaters:cardigans </span>). Multiple categories should be separated by commas. </p> <p> <span class="codeph"> categoryId </span>is limited to 250 characters. </p> <p> <p>Note:  To show a recommendation based on a category in a Category page, only one <span class="codeph"> categoryId </span> can be passed into the mbox used to display that particular recommendation. The value of the <span class="codeph"> categoryId </span> must match exactly the value of <span class="codeph"> entity.cateogryId </span> passed on the Product Detail page. </p> </p> <p>Example Product Detail Page: <span class="codeph"> womens, womens:sweaters, womens:sweaters:cardigans </span> </p> <p>Example Category Page Sweaters: <span class="codeph"> womens:sweaters </span> </p> <p>Example Category Page Cardigans: <span class="codeph"> womens:sweaters:cardigans </span> </p> <p>For category-based Recommendations, a comma is used to separate category value. Any values separated by commas become categories. You can also define subcategories by using a different separator, such as a colon (:), to separate subcategories within the category value. </p> <p>For example, in the following code the Womens category is divided into several subcategories: </p> <p> 
     <code>
       mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', ); 
     </code> </p> <p>For the mbox delivery, the longest attribute name is used for the key. If there is a tie, the last attribute is used. In the example above, the category key is <span class="codeph"> Womens:Outerwear:Jackets:Caban </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.brand </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>Displays an item's brand name. </p> <p>Example: </p> <p> 
     <code>
       'entity.brand=brandxyz' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.pageURL </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>Defines the relative URL of the page where the item can be purchased. </p> <p>Example: </p> <p> 
     <code> 
'entity.pageURL=baseball/giants-tix/giantsvrockies5.12.2000-67833' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.thumbnailURL </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>Defines the relative URL to the thumbnail image that displays with the item. </p> <p>Example: </p> <p> 
     <code>
       'entity.thumbnailURL=baseball/giants-tix/giants-136px.gif' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.message </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p> A message about the product that is displayed in the recommendation, such as "on sale" or "clearance." The message is typically more verbose than the product name. Use to define additional information to display with the product in the template </p> <p>Example: </p> <p> 
     <code>
       'entity.message=Family&amp;nbsp;special' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.inventory </span> </p> <p>Single-value only. Requires an integer or long value. </p> </td> 
   <td colname="col2"> <p>Displays the inventory level of the item. </p> <p>Example: </p> <p> 
     <code>
       'entity.inventory=1' 
     </code> </p> <p><b>Empty Inventory Attribute Handling</b> </p> <p>For delivery, if you have an inclusion rule, collection rule, or criteria setting with <span class="codeph"> entity.inventory > 0 </span> or <span class="codeph"> entity.inventory = 0 </span> and the product has inventory not set, Target evaluates this to TRUE and includes products where the inventory is not set. This was done by default so that products with inventory that is not set show up in recommendation results. </p> <p>Similarly, if you have a global exclusion rule with <span class="codeph"> entity.inventory = 0 </span> and <span class="codeph"> entity.inventory </span> is not set, Target evaluates this rule to be TRUE and excludes the product. </p> <p>Known issue: Product Search is inconsistent with delivery for not set inventory value attributes. For example for a rule with <span class="codeph"> entity.inventory = 0 </span>, Product Search will not display products where the inventory value is not set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.value </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>Defines the price or value of the item. </p> <p>Example: </p> <p> 
     <code>
       'entity.value=15.99' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.margin </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>The profit margin or other value of the item. </p> <p>Example: </p> <p> 
     <code>
       'entity.margin=1.00' 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity. </span> <span class="varname"> &lt;custom> </span> </p> <p>Supports multi-value (JSON array). </p> </td> 
   <td colname="col2"> <p>Define up to 100 custom variables that provide additional information about the item. You can specify any unused attribute name for each custom attribute. For example, you might create a custom attribute called <span class="codeph"> entity.genre </span> to define a book or movie. Or, a ticket vendor might create attributes for an event venue for a secondary performer, such as a visiting team in a sporting event or an opening act in a concert. </p> <p><b>Restrictions</b>: </p> 
    <ul id="ul_F0F102908B0142669AF3B74636C828F1"> 
     <li id="li_9271366EC1C34315B01D5BD919F5432A">You cannot use predefined entity attribute names for custom entity attributes. </li> 
     <li id="li_C765DE30512C4E99927E9810EAA822CF">The attribute <span class="codeph"> entity.environment </span> is reserved by the system and cannot be used for custom entity attributes. Attempts to pass <span class="codeph"> entity.environment </span> using <span class="codeph"> targetPageParams </span>, feed, or API will be ignored. </li> 
    </ul> <p>Examples: </p> <p> 
     <code>
       'entity.venue=AT&amp;T&amp;nbsp;Park' 
     </code> </p> <p> 
     <code>
       'entity.secondary=Rockies' 
     </code> </p> <p>Custom entity attributes support multiple values. A multi-value entity attribute can include up to 100 values. Each value can be up to 100 characters. Values that exceed 100 characters are ignored. </p> <p>Example: </p> <p> 
     <code>
       'entity.secondary=["band1",&amp;nbsp;"band2"]' 
     </code> </p> <p> <p>Note:  Multi-value custom entity attributes require valid JSON arrays. For correct syntax information, see <a href="../../c-recommendations/c-products/c-custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322" format="dita" scope="local"> Custom Entity Attributes </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> entity.event.detailsOnly </span> </p> <p>Single-value only. </p> </td> 
   <td colname="col2"> <p>Used to prevent an mbox call from incrementing behavioral data counters for an algorithm. </p> <p>Example: </p> <p> 
     <code>
       'entity.event.detailsOnly=true' 
     </code> </p> <p>In the examples below, the first mbox call will update the catalog and behavioral data. The second mbox call will update only the catalog. </p> <p> 
     <code>
       mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' ) 
     </code> </p> <p> 
     <code>
       mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' ) 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Recommendations sends the `productId` or `productPurchasedId` (referred to as `entity.id` in the code) that is used in the algorithms.

>[!NOTE]
>
>`entity.id` must match the `productPurchasedId` sent to the order confirmation page and the `productId` used in Adobe Analytics product reports).

Most predefined parameters accept only a single value, with new values overwriting old values. The `categoryId` parameter can accept a comma-delimited list of values for each category containing that product. New `categoryId` values do not overwrite existing values but instead are appended during entity update (250-character limit).

In general, the display information mbox might look like the following example. Change the details in bold to refer to your products.

>[!NOTE]
>
>All entity parameter attributes are case sensitive.

```
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id= 
<b>67833</b>', 
 
'entity.name= 
<b>GIANTS VS ROCKIES 5/12</b>', 
 
'entity.categoryId= 
<b>BASEBALL, GIANTS, SF BAY AREA</b>', 
 
'entity.pageURL= 
<b>../baseball/giants-tix/giantsvrockies5.12.2000-67833</b>', 
 
'entity.venue= 
<b>AT&T PARK</b>', 
 
'entity.secondary= 
<b>ROCKIES</b>', 
 
'entity.thumbnailURL= 
<b>../baseball/giants-tix/giants-136px.gif</b>', 
 
'entity.message= 
<b>FAMILY SPECIAL</b>', 
 
'entity.value= 
<b>15.99</b>', 
 
'entity.inventory= 
<b>1</b>' 
 
); 
 
</script>
```

>[!NOTE]
>
>Relative URLs are preferred for `pageURL` and `thumbnailURL` rather than absolute URLs because recommendations receive data being sent from all environments on your site. Using relative URLs avoids hardcoded links to a staging or development server.

If the mbox is on a product page, you can include both the product ID and category ID. The selected algorithm determines which displays. The product ID is used for affinity algorithms and the category ID is used for category algorithms.

>[!MORE_LIKE_THIS]
>
>* [Custom Entity Attributes](../../c-recommendations/c-products/c-custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)

