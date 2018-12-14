---
description: The Capture Score engagement metric calculates an aggregated score based
  on the value assigned to pages visited on the site, from the point the visitor first
  sees the campaign's first display mbox.
keywords: capture score;score
seo-description: The Capture Score engagement metric calculates an aggregated score
  based on the value assigned to pages visited on the site, from the point the visitor
  first sees the campaign's first display mbox.
seo-title: Capture Score
solution: Target
subtopic: Getting Started
title: Capture Score
topic: Standard
uuid: 977454ad-da32-449a-a8c9-1f3c75220be6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Capture Score{#capture-score}

The Capture Score engagement metric calculates an aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the campaign's first display mbox.

The following example shows how score engagement is calculated in a campaign that tests two experiences, one with a cat image, and one with a dog image.

![](assets/example_score.png)

In this example, the first visitor experiences the cat experience. Assume that a global mbox passes in a page score based on the value of the page. If the marketer has captured page count engagement on a success metric associated with `**any mbox**`, the visit score accumulates for any mbox request seen after the display mbox around the cat image.

The first page adds 1 to the score, the second page 0.25, the third 0.10, and the fourth 0.10 for a total of 1.45. This could be interpreted as either currency or points. In a separate visit, a visitor experiences the Dog experience, and although the visitor views fewer pages, the score is 2.10, greater than the other visit, because the visitor viewed more valuable pages.

You can take into account acquisition costs and affiliate link revenue by passing adboxes and redirectors, as depicted in the following page flow. Notice that, in this example, both mboxes on the article page pass a score, possibly representing a known CPM.

![](assets/example_score2.png)

**Assigning a Page Score**

You can assign a value to any page on your site based on what the page is worth to you. For example, a cooking site might be able to sell ads for more money on their feature article pages than in their experience section. Thus, the feature articles are more valuable than the experience section. Page score allows you to develop an overall "value" of a visit, so the person who reads more feature articles gets more "points" than someone who just browses the experiences.

There are two methods to assign a score to a page:

* In the mbox code, create an mbox parameter called `mboxPageValue`.

   Example: `('global_mbox', 'mboxPageValue=10');`

   The specified value is added to the score every time the page with that mbox is viewed. If multiple mboxes on the page include score values, the score for the page is the total of all mbox values. `mboxPageValue` is a reserved parameter used for passing values in an mbox to capture an engagement score. Positive and negative values can be passed. The sum is calculated at the end of each visitor's visit to calculate the total score for the visit.

* Pass the `?mboxPageValue=n` parameter in the URL for the page.

   Example: `https://www.mydomain.com?mboxPageValue=5`

   Using this method, the specified value is added to the score for each mbox on the page. For example, if you pass the parameter `?mboxPageValue=10`and there are three mboxes on the page, the score for the page is 30.

>[!NOTE] {class="- topic/note "}
>
>Mboxes located above the campaign's first display mbox will not be included in the score.

Best practice is to assign values in the mbox code. This allows you to be precise in the values you measure, depending on the content of each mbox.

>[!NOTE] {class="- topic/note "}
>
>For easier maintenance, you can configure your site's page score value assignments in the [!DNL at.js] or [!DNL mbox.js] file with some conditional JavaScript logic. This eliminates the need to add more code to your pages. Contact your account consultant for assistance.

You can combine the two methods, but this might result in a higher score than expected. For example, if you assign a value of 10 to each of three mboxes and no score to a fourth mbox, then pass the URL parameter `?mboxPageValue=5`, your page score will be 50, 30 for the three mboxes with assigned values, and then 5 for each of the four mboxes on the page.

The counter starts with the first display mbox, not the entry mbox. For example, if you enter the campaign on the homepage which doesn't have a display mbox, then link to catalog page containing a display mbox, the counter begins when you move to the catalog page.

You can also pass in negative values on certain pages that cost you money or are not good for a visitor to see. The negative values affect the overall score as well. This technique can be used on a page that visitors reach from an advertisement, so you know how much the CPC was. Or, for example, it can be used for a support or contact page, where you know that visitors might call or request assistance from this page.
