---
description: Information about using experience fragments created in Adobe Experience
  Manager (AEM) in Target activities to aid optimization or personalization.
keywords: experience;aem;adobe experience manager;export to adobe target;experience
  fragments;fragments;XF
seo-description: Information about using experience fragments created in Adobe Experience
  Manager (AEM) in Target activities to aid optimization or personalization.
seo-title: AEM experience fragments
solution: Target
title: AEM experience fragments
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# AEM experience fragments{#aem-experience-fragments}

Information about using experience fragments created in Adobe Experience Manager (AEM) in Target activities to aid optimization or personalization.

## AEM experience fragments {#topic_1E1E4EA01F074349B2CF8785387B5FE8}

Information about using experience fragments created in Adobe Experience Manager (AEM) in Target activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an Adobe Experience Manager (AEM) customer. See [Requirements](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A), below, for more information.

## Overview {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in AEM in Target activities lets you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in Target to test and personalize experiences at scale.

AEM brings together all of your content and assets in a central location to fuel your personalization strategy. AEM lets you easily create content for desktops, tablets, and mobile devices in one location without writing code. There’s no need to create pages for every device—AEM automatically adjusts each experience using your content.

Target lets you deliver personalized experiences at scale based on a combination of rules-based and AI-driven machine learning approaches that incorporate behavioral, contextual, and offline variables.&nbsp; With Target you can easily set up and run A/B and Multivariate (MVT) activities to determine the best offers, content, and experiences.

Experience fragments represent a huge step forward to link the content/experience creators and managers to the optimization and personalization professionals who are driving business outcomes using Target.

## Requirements {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within Target. In addition, you must be using AEM 6.3 with the appropriate service pack or AEM 6.4 (or later). Your account representative can help ensure that you meet the requirements to use this feature:

* Adobe Experience Manager 6.4 (or later).
* Adobe Experience Manager 6.3 SP2 (or later).
* Adobe Target Standard or Adobe Target Premium account.
* Contact Adobe Target Customer Care to enable the integration and to provide you with authentication details.

## Creating and Configuring Experience Fragments in AEM {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use AEM experience fragments in Target, you must perform the following steps:

<table id="table_A7836BBD5DEB4A088E30B1B1445F2D15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step1_icon.png" id="image_7928C84A792946B384383AD7E03EB911" /> Integrate AEM with Target </p> </td> 
   <td colname="col2"> <p>For more information, see: </p> <p> 
     <ul id="ul_B0FF2A7AD4694CCF8E7F788F70DDA8F0"> 
      <li id="li_451CDE76FF3F4AB29E08013D8EE3C818"> <p><b>AEM 6.3: </b> <a href="https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html" format="html" scope="external"> Opting into Adobe Analytics and Adobe Target </a> in the <i>Adobe Experience Manager 6.3</i> documentation. </p> </li> 
      <li id="li_6F8C4AF767DE4A7686D9BCD6EFD6049B"> <p><b>AEM 6.4: </b> <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html" format="html" scope="external"> Opting into Adobe Analytics and Adobe Target </a> in the <i>Adobe Experience Manager 6.4</i> documentation. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step2_icon.png" id="image_CF1B3C977051478B8B0ABE3D41429122" /> Create the experience fragment </p> </td> 
   <td colname="col2"> <p>Experience fragments are created in AEM. For more information, see: </p> <p> 
     <ul id="ul_DF0E48720E9F4228A2E396B7BADBC690"> 
      <li id="li_626CB3A93A4A45ADAE34AC009A0A649B"> <p><b>AEM 6.3: </b> <a href="https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html" format="html" scope="external"> Experience Fragments </a> in the <i>Adobe Experience Manager 6.3</i> documentation. </p> </li> 
      <li id="li_42CE0B9F798043CB90AF1EF29E00C8E5"> <p><b>AEM 6.4: </b> <a href="https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html" format="html" scope="external"> Experience Fragments </a> in the <i>Adobe Experience Manager 6.4</i> documentation. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step3_icon.png" id="image_6FBEE3C0B9494944B4AC4960803D6A20" /> Configure AEM to share the experience fragment with Target </p> </td> 
   <td colname="col2"> <p> 
     <ol id="ol_185B3C5984D64ECDB69BEC12CED8B6D9"> 
      <li id="li_832CAA9039EC4C9F81DA7841570C7489"> <p>From within AEM, select the desired experience fragment or its containing folder, then click <span class="uicontrol"> Properties </span>. </p> </li> 
      <li id="li_1B6DECBF48434D6DA61096C343AC91CD"> <p>Click the <span class="uicontrol"> Cloud Services </span> tab, then from the <span class="uicontrol"> Cloud Service Configuration </span> drop-down list, select <span class="uicontrol"> Adobe Target </span>. </p> <p> <p>Note:  The previous step assumes that someone in your organization has created the Adobe Target configuration. </p> </p> </li> 
      <li id="li_73024D20AC934D9591CCEFA558B4AE21"> <p>Click <span class="uicontrol"> Save &amp; Close </span>. </p> </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <img href="assets/step4_icon.png" id="image_ACC43C96B1894B04BFD2A3AAF5C1A45A" /> Publish the experience fragment and export it into Target </p> </td> 
   <td colname="col2"> <p> <b>AEM 6.3:</b> </p> <p> 
     <ol id="ol_7700A6562F514538BBDB24EA542B3D2A"> 
      <li id="li_22D1CC5CDFD24EE29929DC4BDF87EEC9"> <p>From within AEM, select the desired experience fragment, click the <span class="uicontrol"> Publish </span> tab, then click the <span class="uicontrol"> Publish </span> button. </p> </li> 
      <li id="li_F2F2BF28564C422D824DF1E972E7C696"> <p>From within AEM, select the desired experience fragment, click <span class="uicontrol"> Export to Adobe Target </span>, then click <span class="uicontrol"> OK </span>. </p> <p> <img href="assets/experience_fragment_export_to_target.png" id="image_5A03C93F0A7D40B786D77DE24E24C16B" /> </p> </li> 
     </ol> </p> <p><b>AEM 6.4:</b> </p> <p> 
     <ol id="ol_027758DB9ED443EABB85F60519019922"> 
      <li id="li_1E664C716E394516AEC38CC9002426CA"> <p>From within AEM, select the desired experience fragment, click <span class="uicontrol"> Export to Adobe Target </span>. </p> <p> <img href="assets/experience_fragment_export_to_target.png" id="image_FD1DE3B3569E4090B3B37FE3EE190DEE" /> </p> </li> 
      <li id="li_8BC8835395BC44A2965F491C1268E7BA"> <p>In the dialog box that displays, select <span class="uicontrol"> Publish </span> to publish all of the assets within the experience fragment to Target. </p> </li> 
     </ol> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Using Experiment Fragments in Target Activities {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

After performing the preceding tasks, the experience fragment displays on the [!UICONTROL Offers] page in Target.

>[!NOTE]
>
>Target currently looks for experience fragments to import every ten minutes. The imported experience fragment should be available in Target within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into Target as an HTML offer. Note that the experience fragment "master" version remains in AEM. You cannot edit the experience fragment in Target.

You can hover over an experience fragment in the list, then click the View icon (  ![](assets/icon_info.png)

) to see additional information about the experience fragment, including its public offer delivery URL, its AEM path, and a deep link to open the experience fragment inside of AEM.

You can consume Experience Fragments in Target activities using the Visual Experience Composer (VEC) or the Form-Based Experience Composer.

>[!NOTE]
>
>To fully utilize Target's AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Automated Personalization](../../c-activities/t-automated-personalization/t-automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) while creating an A/B Test.

**To consume Experience Fragments using the VEC:**

1. In Target, while creating or editing an experience in the [Visual Experience Composer](../../c-experiences/c-experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), click the location on the page where you want to insert AEM content, then select **[!UICONTROL Swap with Experience Fragment]** to display the [!UICONTROL Choose an Experience Fragment] list.

   >[!NOTE]
>
>The [!UICONTROL Swap with Experience Fragment] option is not available for images. If you want to use this option with an image, click the container element that contains the desired image.

   The [!UICONTROL Experience Fragment] list displays all of the content created in AEM that is now natively available from within Target.

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Save]**.
1. Finish configuring the activity.

   For more information about configuring the various activity types, see the following topics:

   * **A/B Test:** [Create an A/B Test](../../c-activities/t-test-ab/t-test-create-ab/t-test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **Auto-Allocate:** [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Auto-Target:** [Auto-Target For Personalized Experiences](../../c-activities/c-auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **Automated Personalization (AP):** [Creating an Automated Personalization Activity](../../c-activities/t-automated-personalization/t-create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Experience Targeting (XT):** [Create an Experience Targeting Activity](../../c-activities/t-experience-target/t-xt-create/t-xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Multivariate Test (MVT):** [Create a Multivariate Test](../../c-activities/c-multivariate-testing/t-create-multivariate-test/t-create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [Create a Recommendations Activity](../../c-recommendations/t-create-recs-activity/t-create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**To consume Experience Fragments using the Form-based Experience Composer:**

1. In Target, while creating or editing an experience in the [Form-Based Experience Composer](../../c-experiences/t-form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), select the location on the page where you want to insert AEM content, then select **[!UICONTROL Change Experience Fragment]** to display the [!UICONTROL Choose an Experience Fragment] list.

   ![](assets/experience_fragment_list.png)

   The [!UICONTROL Experience Fragment] list displays all of the content created in AEM that is now natively available from within Target.

1. Select the desired experience fragment, then click **[!UICONTROL Save]**.
1. Finish configuring the activity.

## Experience Fragment Training Video {#section_C0EDC54063464F41A182492D2045BC64}

The following video shows you how to set up and use experience fragments: [Using AEM Experience Fragments with Adobe Target](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html).
