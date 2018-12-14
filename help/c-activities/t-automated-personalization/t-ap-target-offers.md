---
description: In an Automated Personalization activity, you can target offers to specific
  audiences.
seo-description: In an Automated Personalization activity, you can target offers to
  specific audiences.
seo-title: Target Automated Personalization offers
solution: Target,Analytics
title: Target Automated Personalization offers
title-outputclass: premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Target Automated Personalization offers{#target-automated-personalization-offers}

In an Automated Personalization activity, you can target offers to specific audiences.

Using this functionality reduces the number of offers a specific visitor is qualified to see. For example consider an Automated Personalization (AP) activity that has three offers. Offer 1 has a targeting rule that limits its exposure only to Audience A. Two visitors saw this AP activity.

<table id="table_0A65E5AFA2FA4561A902E8892092D1D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Visitor 1 </th> 
   <th colname="col3" class="entry"> Visitor 2 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Qualification </p> </td> 
   <td colname="col2"> <p>Audience A </p> </td> 
   <td colname="col3"> <p>Audience B </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Offer 1 Target personalization model score </p> </td> 
   <td colname="col2"> <p>90 </p> </td> 
   <td colname="col3"> <p>90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Offer 2 Target personalization model score </p> </td> 
   <td colname="col2"> <p>50 </p> </td> 
   <td colname="col3"> <p>70 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Offer 3 Target personalization model score </p> </td> 
   <td colname="col2"> <p>80 </p> </td> 
   <td colname="col3"> <p>60 </p> </td> 
  </tr> 
 </tbody> 
</table>

In this scenario, Visitor 1 would see Offer 1 (because he or she qualifies as part of Audience A), which is that visitor's highest score. However, Visitor 2 would see Offer 2 even though his or her highest score is for Offer 1, because Visitor 2 is not part of Audience A. This example demonstrates why targeting rules should be used sparingly to meet business needs. Adding these rules can reduce the effectiveness of Target's personalization models.

**To set up Targeting rules:**

1. Create an Automated Personalization activity containing the offers you want to target.
1. After setting up the offers for the activity in the Visual Experience Composer, click **[!UICONTROL Content]**.

   The Manage Content dialog box opens.

   ![](assets/ap_content.png)

   >[!NOTE]
>
>You can set up 50 locations, and up to 250 offers per location.

1. In the **[!UICONTROL Content]** column, select the offer, then click **[!UICONTROL Targeting]** and choose the audiences you want to qualify to see that offer.

   Only the selected audiences will be presented that offer.

   >[!NOTE]
>
>In addition to selecting an existing audience, you can combine multiple audiences to create ad hoc combined audiences rather than creating a new audience. For more information, see [Combining Multiple Audiences](../../c-target/c-combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Click **[!UICONTROL Done]**.
