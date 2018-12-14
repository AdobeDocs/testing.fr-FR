---
description: The Order Confirmation mbox records details about orders on your site
  and allows reporting based on revenue and orders. The Order Confirmation mbox can
  also drive recommendation algorithms, such as "People who bought product x also
  bought product y."
keywords: order confirmation;orderConfirmPage
seo-description: The Order Confirmation mbox records details about orders on your
  site and allows reporting based on revenue and orders. The Order Confirmation mbox
  can also drive recommendation algorithms, such as "People who bought product x also
  bought product y."
seo-title: Create an Order Confirmation mbox - mbox.js
solution: Target
subtopic: Getting Started
title: Create an Order Confirmation mbox - mbox.js
uuid: 001da2bd-2ccf-490b-ba84-ac9b9a2a5451
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Create an Order Confirmation mbox - mbox.js{#create-an-order-confirmation-mbox-mbox-js}

The Order Confirmation mbox records details about orders on your site and allows reporting based on revenue and orders. The Order Confirmation mbox can also drive recommendation algorithms, such as "People who bought product x also bought product y."

>[!NOTE]
>
>If users make purchases on your website, we recommend implementing an Order Confirmation mbox even if you use Analytics for Target (A4T) for your reporting.

>[!NOTE]
>
>You can also create an Order Confirmation mbox for `at.js` using the same method; however, the [!DNL at.js] method is preferred. For more information, see [Track Conversions](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

1. In your order details page, insert the mbox script following the model below.
1. Replace the WORDS IN CAPITAL LETTERS with either dynamic or static values from your catalog.

   >[!NOTE]
>
>Use comma delimiting to separate multiple product IDs.

   **Tip:** You can also pass order information in any mbox (it does not need to be named `orderConfirmPage`). You can also pass order information in multiple mboxes within the same campaign.

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

The Order Confirmation mbox uses the following parameters:

<table id="table_CEB2E2F2265142D89672E124CB4C880B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> orderId </span> </p> </td> 
   <td colname="col2"> <p> Unique value to identify an order for conversion counting. </p> <p>The <span class="codeph"> orderId </span> must be unique. Duplicate orders are ignored in reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> orderTotal </span> </p> </td> 
   <td colname="col2"> <p> Monetary value of the purchase. </p> <p>Do not pass the currency symbol. Use a decimal point (not a comma) to indicate decimal values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> productPurchasedId </span> (Optional) </p> </td> 
   <td colname="col2"> <p> Comma-separated list of product IDs purchased in the order. </p> <p> These product IDs display in the audit report to support additional reporting analysis. </p> </td> 
  </tr> 
 </tbody> 
</table>

