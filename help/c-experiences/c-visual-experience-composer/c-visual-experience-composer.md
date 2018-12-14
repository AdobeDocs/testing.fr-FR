---
description: Information about using the Visual Experience Composer (VEC) and the
  Enhanced Experience Composer.
seo-description: Information about using the Visual Experience Composer (VEC) and
  the Enhanced Experience Composer.
seo-title: Visual Experience Composer (VEC)
title: Visual Experience Composer (VEC)
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Visual Experience Composer (VEC){#visual-experience-composer-vec}

Information about using the Visual Experience Composer (VEC) and the Enhanced Experience Composer.

The Visual Experience Composer video (7:17) below provides information about using the Visual Experience Composer options.

* Change the content of a page
* Change the layout of a page

>[!VIDEO](https://www.youtube.com/watch?v=2KUDgu6Mscg)

The following experience composers are available:

## Visual Experience Composer and Enhanced Experience Composer {#section_34265986611B4AB8A0E4D6ACC25EF91D}

The Visual Experience Composer is one of the main features of Adobe Target. The Visual Experience Composer is an editor that enables marketers and designers to create and change content using a visual interface. Many design choices can be made without requiring direct editing of the code. Editing HTML and JavaScript is also possible using the editing options available in the composer.

The videos below provide information about using the Visual Experience Composer.

**Visual Experience Composer (1 of 2) (7:17)**

* Change the content of a page
* Change the layout of a page

>[!VIDEO](https://www.youtube.com/watch?v=2KUDgu6Mscg)

**Visual Experience Composer (2 of 2) (7:29)**

* Rename and duplicate an experience
* Create a redirect experience
* Target an activity to a single URL or a group of URLs
* Create a multi-page activity
* Preview and build experience for responsive websites
* Use overlays to highlight types of elements

>[!VIDEO](https://www.youtube.com/watch?v=qwUKEp8en_k)

This video is a recording of " [Office Hours](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)," an initiative led by the Adobe Customer Care team.

* How the VEC works
* How to avoid common issues with the VEC
* Work-around practices you can use with the VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)

On the Target **[!UICONTROL Setup]** > **[!UICONTROL Preferences]** tab, you can enter the Default Visual Experience Composer URL.

![](assets/pref-default-url.png)

This URL determines where you start when you open the Visual Experience Composer. If you do not enter a default, then you start with a blank page when you open the editor, and specify a URL at that time.

>[!NOTE]
>
>Certain browsers, such as Firefox, might block a page from displaying in the Visual Experience Composer if the page contains mixed content (for example, a non-secure page in a secure site). If your page does not display, click the icon to the left of the URL in the browser address bar and click **[!UICONTROL Disable protection on this page]**. This issue does not affect the display of your pages to site visitors.

Content inside an iframe on the page can't be modified in Visual Experience Composer. To edit content within an iframe, ensure that the iframe document is Target-enabled, then load that iframe URL in the Visual Experience Composer.

You can use the drop-down menus across the top of the page to view your page as it would appear to different audiences or with different experiences. You can provide a name for each experience in the second drop-down list. For example, if you are testing the location of the Home link in your nav bar, you might name an experience where the Home link appears first something like, "Home link" to make it easier to identify the experiences in the list.

>[!NOTE]
>
>Changes to the structure of a page that affect the locations used in an activity created on that page could cause issues with experience editing. If a location has been changed outside the Visual Experience Editor, Target might not be able to find the location where the content was changed.

As you move your mouse around the page, a context-sensitive box follows the cursor, highlighting the elements on the page.

![](assets/vec_highlight.png)

Click the Overlays icon to change the way the highlight displays. For example, you can choose to highlight only images or mboxes or links, and you can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

Click on a highlighted element for a menu of options available for that element type For example, you can click on an image and select **[!UICONTROL Edit Image]** to change the image, or click on a button and change the HTML. You can use the buttons at the top left of the page to toggle the overlays on and off.

You can also click **[!UICONTROL Browse]**, then navigate to a page that is available from the primary page, such as a shipping page or shopping cart, and test changes on that page. You can also access page elements that are available when you hover, such as flyout menus and mini-carts. When you are finished browsing to the page, click **[!UICONTROL Compose]** to edit the experience. For example, you might want to change the design of a shopping cart drop-down or a carousel of images. This functionality is currently available for A/B tests, A/B tests with Analytics, and experience targeting.

>[!NOTE]
>
>If a hover state depends on JavaScript, make sure **[!UICONTROL Disable JavaScript]** is not selected. JavaScript must be enabled to edit JavaScript elements.

For information about the options available in the Visual Experience Composer, see [Visual Experience Composer Options](../../c-experiences/c-visual-experience-composer/r-viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).
