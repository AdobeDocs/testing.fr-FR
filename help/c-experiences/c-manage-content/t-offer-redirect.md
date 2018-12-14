---
description: The Redirect Offer causes a browser to redirect to a new page.
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters
  in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going
  to a different domain)
seo-description: The Redirect Offer causes a browser to redirect to a new page.
seo-title: Create redirect offers
solution: Target
title: Create redirect offers
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Create redirect offers{#create-redirect-offers}

The Redirect Offer causes a browser to redirect to a new page.

You might have two completely different pages to test instead of just changing pieces of content within a page. In this case, your A/B test compares page A vs. page B. Set up an A/B test campaign with two experiences: one pointing to the default page A, and the other redirecting to page B. The offer is configured to redirect the visitor to a different page.

>[!NOTE] {class="- topic/note "}
>
>You cannot use redirect offers in ajax mboxes ( `mboxUpdate`).

>[!NOTE]
>
>For redirect offers in activities using A4T, your implementation must meet certain minimum requirements. In addition, there is important information that you need to know. For more information, see [Redirect Offers - A4T FAQ](../../c-integrating-target-with-mac/a4t/r-a4t-faq/c-a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).

For information about setting up an experience that redirects, see [Redirect to a URL](../../c-experiences/c-visual-experience-composer/t-redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

The redirect offer executes JavaScript code to redirect the browser. It uses the `window.location.replace();` method, so the page the visitor is redirected from is not stored in the browser history. This allows the visitor to still use the back button in their browser.

>[!NOTE] {class="- topic/note "}
>
>If you want to pass the referrer value of the landing page, it is recommended that you use an HTML offer rather than a redirect offer.

**To create a Redirect Offer:**

1. Click **[!UICONTROL Offers]**, then select the **[!UICONTROL Code Offers]** tab.
1. Click **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.
1. Type an offer name.
1. Enter the URL for the unique content or destination you want to redirect to. This must be an absolute URL.

   >[!NOTE]
>
>Redirect offers result in an infinite loop if the redirect URL also qualifies the user for the same activity. You should ensure that the user does not re-qualify for the activity after being redirected.

1. Select the desired options to customize your redirect offer:

* **Include all URL parameters:** Check this box if you want all the URL parameters present on the previous page to be propagated to the redirected page.

   For example, you want to redirect people directly from a men's page to a men's shirts category page. You also want the dynamic parameters in the URL to be passed because this is how you track if people reached your site via email, banner ad, search ad, or organically. By checking this box, your redirect offer on page [!DNL `https://www.mycompany.com/mens.html?emailId=123`] will automatically become [!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] when all you entered in the URL box was [!DNL `https://www.mycompany.com/mensShirts.html`].

* **Pass mbox session ID (required to redirect to a different domain):** Check this box if you want the `sessionId` to automatically be included in the redirect. This is only required when you are testing clicks from an email or clicks from one domain to another. The `sessionId` matches the visitor's cookie so the visitor can continue to be tracked and the proper content is shown.

   If you use the 1st & 3rd party cookie setup, you do not need to pass the mbox session ID when crossing domains. It is persistent on the 3rd-party cookie, so it is not necessary in the URL.

>[!NOTE] {class="- topic/note "}
>
>Ask your Implementation Consultant before launching these tests.

This video includes information about managing content. (4:56)

* Connection between the [Experience Cloud Asset Library](https://marketing.adobe.com/resources/help/en_US/mcloud/creative_cloud.html) and the Target Content Library
* Custom HTML Offers
* Custom HTML Offer in the Visual Experience Composer

>[!VIDEO](https://www.youtube.com/watch?v=ZNIGgXOATMY)
