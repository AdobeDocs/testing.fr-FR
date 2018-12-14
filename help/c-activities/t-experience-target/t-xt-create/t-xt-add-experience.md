---
description: The Experience Composer provides a visual interface for editing the experiences
  on your page.
keywords: create experience;experience create;priority;audience;experience;visual
  experience composer
seo-description: The Experience Composer provides a visual interface for editing the
  experiences on your page.
seo-title: Create Experience
solution: Target
title: Create Experience
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Create Experience{#create-experience}

The Experience Composer provides a visual interface for editing the experiences on your page.

For additional detail about experiences, see [Experiences](../../../c-experiences/c-experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Click **[!UICONTROL Add Experience]**.

   >[!NOTE]
>
>If you are targeting an experience to an audience, you must select the audience before you can add an experience. A message appears to remind you to choose your audience.

1. When prompted, enter the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Continue]**.

   The Experience Composer (see [Experiences](../../../c-experiences/c-experiences.md#concept_1D011219034B492BB03C08B3BB80E3F0)) opens the page that is specified in your Account Preferences. To display a different page, click the Globe icon and enter the URL in the Select URL box in the Experience Composer and click **[!UICONTROL Continue]**. If you entered a URL for a site that does not include the Target Standard JavaScript code, you cannot select page elements.

   By default, the Visual Experience Composer does not allow changes to elements containing JavaScript, such as rotating banners. You can select to disable JavaScript if you want to be able to alter those elements using the Visual Experience Composer.

   >[!NOTE]
>
>If you change the URL after making changes to a page for one or more experiences, the experience is reset using the new page and the changes you made are lost.

1. Select the elements you want to change and make the desired changes.

   As you hover the elements on your page, the elements are highlighted. Any highlighted element can be altered using the Experience Composer.

   **Visual Experience Composer (1 of 2) (7:17)**

   The video below provides information about using the Visual Experience Composer options.

   * Change the content of a page
   * Change the layout of a page
   >[!VIDEO](https://www.youtube.com/watch?v=2KUDgu6Mscg)

   If you created an mbox on the page using Target Classic (formerly Test&Target), that mbox appears as an element that shows the mbox name, and can be modified like any other element.

   The following actions can be performed on an element on the displayed page to change the experience:

   <table class="- topic/table " id="table_83E4672153B54EB582E8EA48C47BF27E"> 
   <thead class="- topic/thead "> 
   <tr class="- topic/row "> 
      <th class="- topic/entry entry" colname="col01"> Menu Item </th> 
      <th class="- topic/entry entry" colname="col1"> Option </th> 
      <th class="- topic/entry entry" colname="col2"> Description </th> 
   </tr>
   </thead>
   <tbody class="- topic/tbody "> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> <p>Edit </p> </td> 
      <td class="- topic/entry " colname="col1"> <p>Text/HTML </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Change the HTML code for the element, such as the text for a text area, button, or link. </p> <p>In addition to HTML code, you can edit and inject custom JavaScript. </p> <p>Several rich text formatting options are available when editing text and HTML for A/B and Experience Targeting activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>Background Color </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent. </p> <p> <p>Note:  This option is not available for an element where a background image is set. </p> </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>CSS Class </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space. </p> <p>Available for A/B, Automated Personalization, and Multivariate test activities. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>Link </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Change the URL in the link. </p> <p>Use <span class="uicontrol"> Edit Link</span> to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the <span class="wintitle"> Visual Experience Composer</span> to apply the action on the other image element. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> <p>Insert After </p> </td> 
      <td class="- topic/entry " colname="col1"> <p>Image </p> <p>HTML </p> <p>Text </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test. </p> <p>Select an element on the page, then click <span class="uicontrol"> Insert After</span> and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element. </p> <p>The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected. </p> <p> <p>Note:  Inserting an image requires that Adobe Scene7 Publishing System is enabled so you have access to the image library. </p> </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> <p>Replace With </p> </td> 
      <td class="- topic/entry " colname="col1"> <p>Image </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target. </p> <p>During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL. </p> <p>For example, the initial URL might look like the following example: </p> <p> 
      <codeblock>
         https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867
      </codeblock> </p> <p>After activity syncing, the delivery URL might look like the following example: </p> <p> 
      <codeblock>
         https://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&amp;fit=constrain&amp;hei=173&amp;wid=300
      </codeblock> </p> <p> <p>Note:  Swapping images requires an Adobe Scene7 Publishing System account. </p> </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>HTML Offer </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Select a different offer from the Content Library. </p> <p> <p>Note:  HTML Offers are stored on Target servers. </p> </p> <p>An HTML offer can be up to 256KB in size. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>Experience Fragment </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Insert experience fragments created in Adobe Experience Manager (AEM) in Target activities to aid optimization or personalization. For more information, see <a format="dita" href="../../../c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8" scope="local"> AEM Experience Fragments</a>. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> <p>Layout </p> </td> 
      <td class="- topic/entry " colname="col1"> <p>Rearrange </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Drag the element to another location inside the same parent element or <span class="filepath"> &lt;div></span>. Other elements shift location to make space for the rearranged element. </p> <p> <p>Note:  Click tracking does not work on rearranged items. </p> </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>Resize </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Resize an element on your page. When you select <span class="uicontrol"> Resize</span>, a handle appears in the bottom right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio. </p> <p> <p>Note:  Inline elements cannot be resized. </p> </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>Move </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Move elements on your page. Unlike the <span class="wintitle"> Rearrange</span> option, <span class="wintitle"> Move</span> does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support for making sure moved elements are not hidden behind other elements.) </p> <p>In some cases, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>Hide </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Hide the element. The white space remains, but the content is removed. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> </td> 
      <td class="- topic/entry " colname="col1"> <p>Remove </p> </td> 
      <td class="- topic/entry " colname="col2"> <p>Remove the element. The white space behind the image is removed and the space where the element was is collapsed. </p> <p> <p>Note: Items within a "classic" mbox (an mbox created within a <span class="keyword"> Target Classic</span> campaign) cannot be removed using this option. </p> </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> <p>Expand Selection </p> </td> 
      <td class="- topic/entry " colname="col1"> N/A </td> 
      <td class="- topic/entry " colname="col2"> <p>Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> <p>Navigate to this Link </p> </td> 
      <td class="- topic/entry " colname="col1"> N/A </td> 
      <td class="- topic/entry " colname="col2"> <p>Open the destination of the link. </p> </td> 
   </tr> 
   <tr class="- topic/row "> 
      <td class="- topic/entry " colname="col01"> <p>Undo/Redo </p> </td> 
      <td class="- topic/entry " colname="col1"> N/A </td> 
      <td class="- topic/entry " colname="col2"> <p>Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone. </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
>
>If you deliver an image from a source other than your main page (such as an image hosted on akamai.net and delivered on dell.com), then that image does not display in the thumbnail of the page shown in the flow diagram.

1. Click the Check Mark button when you are finished designing the experience.

   The activity diagram displays:

   ![](assets/xt_diagram.png)

   If an experience includes cross-domain content, the thumbnail might not display accurately and is replaced by an icon.
1. Create additional experiences, as desired.

   >[!NOTE]
>
>You can drag and drop audience/experience pairs while creating or editing XT activities to arrange the pairs in the desired order. Visitors will be evaluated for experiences in order, from top to bottom.

   ![](assets/move_experiences.jpg)

   Experience Targeting assumes that order matters. If a visitor falls into the first audience/experience pair, the first experience is delivered.

   For example, suppose you were not aware that order matters while creating an XT activity. You later realize during testing that visitors that you think should qualify for experiences B or C are instead qualifying for experience A. This could be because the audiences are not mutually exclusive and are not in the proper order (for example, experience A = United States, experience B = San Francisco, and experience C = California). In this scenario, all users from the United States qualify for experience A, even if they are located in San Francisco or elsewhere in California. You can reorder the audience/experience pairs from most restrictive to least restrictive (San Francisco > California > United States) without re-creating the entire activity.

   Note that you can click the Edit icon (three vertical ellipses) on an experience in an A/B Test or Experience Targeting (XT) activity and choose from the following options, as necessary:

   * Rename
   * Edit
   * Delete
   ![](assets/experience_edit.png)

   Click **[!UICONTROL Continue]** when you are finished with this step.  **Duplicate an Experience:** You can copy an experience in an Experience Targeting (XT) activity so you can make minor changes to it without having to re-create the experience from scratch.

On the **[!UICONTROL Experiences]** page (the first step in the three-step guided workflow), click the three vertical ellipses > **[!UICONTROL Duplicate]**.

![](assets/duplicate_experience.png)

