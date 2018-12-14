---
description: If you use a page template to provide structure to your pages, or if
  your pages contain similar elements, this feature makes it possible to test variations
  in similarly structured page elements.
keywords: template testing;template;same experience on similar pages;template test
seo-description: If you use a page template to provide structure to your pages, or
  if your pages contain similar elements, this feature makes it possible to test variations
  in similarly structured page elements.
seo-title: Include the Same Experience on Similar Pages
solution: Target
title: Include the Same Experience on Similar Pages
topic: Premium
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Include the Same Experience on Similar Pages{#include-the-same-experience-on-similar-pages}

If you use a page template to provide structure to your pages, or if your pages contain similar elements, this feature makes it possible to test variations in similarly structured page elements.

To work correctly, this feature must be used on pages that have a very similar structure. or contain template elements that are structured the same on all pages.

>[!IMPORTANT]
>
>Using this feature to change elements across dissimilar pages will likely cause unexpected results.

For example, you might use this feature to do one of the following:

* Test a global navigation bar by rearranging or removing elements
* Remove an item from all product pages that use a particular page template
* Add a banner to all product pages
* Change the layout of article template

The following demo video includes information about using a template:

**Visual Experience Composer (2 of 2) (7:29)**

* Rename and duplicate an experience
* Create a redirect experience
* Target an activity to a single URL or a group of URLs
* Create a multi-page activity
* Preview and build experience for responsive websites
* Use overlays to highlight types of elements

>[!VIDEO](https://www.youtube.com/watch?v=qwUKEp8en_k)

You can specify pages that include the change elements, or apply the change across your site.

1. Create an activity as described in [Activities](../../c-activities/c-activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).
1. To specify the pages where the experience will appear, in the Visual Experience Composer click the gear icon, then select **[!UICONTROL URL]**.
1. Click **[!UICONTROL Add Rule]**, then specify the criteria for the pages you want to add the experience to.

1. Specify the page range. The page range can be one of the following:

   * URL
   * Domain
   * Path
   * Hash (#) Fragment (Target the part of a URL that follows the # symbol.)
   * Query
   * Mbox parameter

1. Choose an operator.

   The operator specifies how the items after the operator relate to the page range. Available operators are:

   * Contains
   * Does not contain
   * Is
   * Is not

1. Type the strings that define where the experience is added, such as the domain or the strings contained in the page name.

   For example, if you select **[!UICONTROL Domain]** and **[!UICONTROL Is]**, type the domain where you want the experience added to all pages.

   You can include multiple items.

   >[!IMPORTANT]
>
>Multiple items use `OR` logic, meaning that any single item in the list makes the condition true.

1. If desired, enter additional criteria by clicking **[!UICONTROL Add Criteria]** and repeating the procedure in the previous step.

   Multiple criteria are joined with AND logic. Adobe Target adds the experience to all pages that match the specified criteria.

>[!IMPORTANT]
>
> Target cannot check the pages to make sure they appear as expected, so it is always an important practice when using this feature to test affected pages before making them public.