---
description: The Form-Based Experience Composer provides non-visual experience creation.
keywords: form-based experience composer;form-based composer;refinements
seo-description: The Form-Based Experience Composer provides non-visual experience
  creation.
seo-title: Form-Based Experience Composer
solution: Target
title: Form-Based Experience Composer
topic: Standard
uuid: 6791ed6f-69d0-4ec4-9ea4-47aa92b2a4c9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Form-Based Experience Composer{#form-based-experience-composer}

The Form-Based Experience Composer provides non-visual experience creation.

This feature enables Target Standard A/B tests, Experience Targeting, Automated Personalization, and Recommendations activities to be delivered in emails, mobile apps, kiosks, and other places that don't work with a Visual Experience Composer.

This video provides a demo of the form-based composer.

* Create an activity using the Form-Based Experience Composer
* Understand when to use Form-Based Experience Composer vs. the Visual Experience Composer
* Use refinements to target a location

>[!VIDEO](https://www.youtube.com/watch?v=R9hcD9D1VPY)

If you are creating a Recommendations activity, there are no experiences. Choose your criteria and design. If you choose multiple criteria or designs, Target automatically generates the experiences.

1. Click **[!UICONTROL Create Activity]**, then select the type of activity you want to create.

   The Form-Based Experience Composer is available for A/B tests, Experience Targeting, Automated Personalization, and Recommendations activities.
1. Select **[!UICONTROL Form-Based Experience Composer]** from the [!UICONTROL New Activity]dialog box.

   The Form-Based Experience Composer opens.

   ![](assets/location_refinements.png)

   This screen is different if you are creating a Recommendations activity. Recommendations activities do not include experiences.
1. Name the activity.
1. Select a location.

   When you click in the Select Location box, a list of available locations appears. Select one of those locations. To choose the global location delivered via target.js, choose “target-global-mbox.”

   You can also enter a location that is not listed here. This can be useful if the mbox has not yet been created or viewed on a page. Type the name of the location. Be careful when entering a location that does not yet exist. If the spelling or capitalization does not match the spelling and capitalization when the mbox call is made, the activity will not deliver. Manually entered locations are saved to the list.
1. Click **[!UICONTROL Add Audience Refinements]**, then choose one or more [audience](../c-target/c-target.md#concept_A782F8481A5041EBA75103CB26376522) for this activity.

   ![](assets/location_refinements_2.png)

   In the Form-based Experience Composer, Refinements have been replaced with full audience functionality. Refinements for existing activities have been migrated to [activity-only audiences](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).
1. Select the type of content you want to appear in that location.

   ![](assets/form_content.png)

1. For the content type you selected, specify the content.

   <table id="table_38B1D459A99F4CA695B5D94078402A08"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Content Type Options </th> 
      <th colname="col2" class="entry"> Instructions </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Change Offer </p> </td> 
      <td colname="col2"> <p>Choose an offer saved in the content library in Target. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Change Redirect Offer </p> </td> 
      <td colname="col2"> <p>Choose a redirect offer. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Change Image Offer </p> </td> 
      <td colname="col2"> <p>Choose an image saved in the content library in Target. </p> <p>You can also add a link to an image (click-through, destination, landing, and so forth). </p> <p> 
      <ol id="ol_9DB0607503124884ACB3823E9BF7DB19"> 
         <li id="li_69308FBB39F2479682D3E768555A8F8D">Click <span class="uicontrol"> Change Image Offer</span>. </li> 
         <li id="li_B79C509BF3B6402C835B84C6D30F29CE">Select the desired image, then click <span class="uicontrol"> Edit Links</span>. </li> 
         <li id="li_BEBB94C9F3C94678B196E26CDDBF2425">Specify the desired URL or page on your site, then click <span class="uicontrol"> Update</span>. </li> 
      </ol> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Use Default Content </p> </td> 
      <td colname="col2"> <p>Use the default content. There is no option to select other content. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Create HTML Offer </p> </td> 
      <td colname="col2"> <p>Type or paste the HTML offer source code in the Enter HTML field. </p> <p>For information about using the code editor to create or edit HTML offers, see <a href="../c-experiences/c-visual-experience-composer/c-vec-code-editor/c-vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5" format="dita" scope="local"> Code Editor</a>. </p> </td> 
   </tr> 
   </tbody> 
   </table>

   For a Recommendations activity, the Content drop-down gives you the Add Recommendation option. Click **[!UICONTROL Add Recommendation]**, then select the page type. Then follow the usual steps as defined in the interface to [create a Recommendations activity](https://marketing.adobe.com/resources/help/en_US/target/recs/t_create_recs_activity.html).

   While selecting Recommendations criteria in the Form-Based Experience Composer, there is now a direct link to the selected Criteria card so you can quickly and easily edit the criteria.

   ![](assets/change_criteria.png)

   From the Targeting page of the Target three-step guided workflow:

   ![](assets/change_criteria_2.png)

1. (Optional, for AB activities, Automated Personalization, and Experience Targeting) To repeat this process for additional locations, click `Add Location` and configure the location and content.
1. Click **[!UICONTROL Continue]**, then complete the activity creation steps as usual for your activity type.

* [Create an A/B Test](../c-activities/t-test-ab/t-test-create-ab/t-test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
* [Create an Experience Targeting Activity](../c-activities/t-experience-target/t-xt-create/t-xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Create a Recommendations Activity](../c-recommendations/t-create-recs-activity/t-create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

