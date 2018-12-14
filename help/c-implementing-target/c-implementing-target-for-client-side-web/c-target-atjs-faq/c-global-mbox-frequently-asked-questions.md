---
description: List of frequently asked questions (FAQs) about global mboxes.
keywords: troubleshooting;frequently asked questions;FAQ;FAQs;global;global mbox
seo-description: List of frequently asked questions (FAQs) about global mboxes.
seo-title: Global mbox Frequently Asked Questions
solution: Target
title: Global mbox Frequently Asked Questions
topic: Standard
uuid: f8eb0331-bc2b-4be9-9b35-c764ac091ef4
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Global mbox Frequently Asked Questions{#global-mbox-frequently-asked-questions}

List of frequently asked questions (FAQs) about global mboxes.

## Can I have more than one global mbox if my Target account is set across multiple domains? {#section_B7252BA6C3BB4EF4AE9E53F47FD58ABD}

Only one global mbox is supported across your account.

You can limit where your activities run by adding URL rules to your activities. For more information, see [Include the Same Experience on Similar Pages](../../../c-experiences/c-visual-experience-composer/t-temtest.md#task_2539D51A18044F82B0D9895636546781).

You could also pass a parameter on the page using ` [targetPageParams()](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_B235C9F6DA79449ABE3E23F914FEABAE)` and then select those parameters in the "configure URL" section in the [!UICONTROL Visual Experience Composer] (VEC) or by adding the parameters as "refinements" in the Form-Based Experience Composer.

## How do I pass revenue data on a Target global mbox? {#section_17AEA933BADA4D169CCEDF5833C41306}

To collect revenue and order information on the target-global-mbox, "mbox parameters" must be sent to Target. These parameters are name/value pairs used to send more information to Target. Target automatically looks for these parameters (reserved names) to populate revenue data.

For the `orderConfirmPage`, you should pass in `orderTotal`, `orderId`, and `productPurchasedId`. For more information, see [Create an Order Confirmation mbox - mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/t-orderconfirm-create.md#task_0036D5F6C062442788BB55E872816D82).

These same parameters must be sent to the target-global-mbox via `targetPageParams()`. For more information, see [Passing Parameters to a Global mbox](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/c-pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).

You'll also want to add targeting to the conversion piece so that Target only counts conversions on the target-global-mbox when the order confirmation page has been viewed, as shown below:

![](assets/revenue1.png)

The Site Pages section illustrated above contains the following selections: Current Page, URL, contains, orderconfirm.

![](assets/revenue2.png)

The options in the above illustration include the following settings:

* **What do you want to measure with this activity:** Revenue
* **Default View for Reporting:** Revenue Per Visitor (RPV)
* **What action was taken by your audience to indicate your goal has been reached?** Viewed an mbox, target-global-mbox

