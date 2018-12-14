---
description: Use this option when you want to send the visitor to a different page
  rather than showing content on the same page.
seo-description: Use this option when you want to send the visitor to a different
  page rather than showing content on the same page.
seo-title: Redirect to a URL
solution: Target
subtopic: Multivariate Test
title: Redirect to a URL
topic: Standard
uuid: e6515279-8a6e-4265-aa2d-700ee81eb143
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Redirect to a URL{#redirect-to-a-url}

Use this option when you want to send the visitor to a different page rather than showing content on the same page.

You might have two completely different pages to test instead of just changing pieces of content within a page. In this case, your A/B test compares page A vs. page B. Set up an A/B test campaign with two experiences: one pointing to the default page A, and the other redirecting to page B. In the Experience Action menu, located by clicking the letter label for the experience, choose **[!UICONTROL Redirect to URL]** and specify the URL of page B. The offer is configured to redirect the visitor to a different page.

The redirect offer executes JavaScript code to redirect the browser. It uses the `window.location.replace();`method, so the page the visitor is redirected from does not get stored in the browser history. This allows the visitor to still use the back button in their browser.

Redirect offers have a few limitations:

* For redirect offers in activities using A4T, your implementation must meet certain minimum requirements. In addition, there is important information that you need to know. For more information, see [Redirect Offers - A4T FAQ](../../c-integrating-target-with-mac/a4t/r-a4t-faq/c-a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* When using the form-based Experience Composer, redirect offers should not be used in mboxes that are part of the page. A redirect offer should only be used from a script tag that is part of the HTML `<head>`. You should always use auto-create and set the redirect offer for the global mbox.

>[!NOTE] {class="- topic/note "}
>
>If you want to pass the referrer value of the landing page, it is recommended that you use an HTML offer rather than a redirect offer.

To create a redirect offer:

1. Create an experience.
1. Hover over an experience with your mouse, then click the Redirect to URL icon (![](assets/icon_redirect_url.png)).

   ![](assets/exp_actions.png)

1. Type the URL.
1. If desired, select the option to include current query parameters.

   If this option is selected, anything after the ? in the visitor's URL is appended to the redirect URL at the time of redirect.

   This option is selected by default.
1. (Optional) Create additional rules.

   Additional rules can be based on any of the following:

   * URL
   * Domain
   * Path
   * Hash (#) Fragment
   * Query
   * mbox Parameter
   Additional rules can be joined to the Activity URL with AND or OR. All rules you add are evaluated against each other with AND.
