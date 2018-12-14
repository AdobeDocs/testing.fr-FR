---
description: Custom parameters are mbox parameters. If you pass any mbox parameters
  to mboxes, or use the targetPageParams function, those parameters appear here for
  use in audiences.
keywords: custom parameters;target custom parameters;targetpageparams;targeting mbox
  parameters
seo-description: Custom parameters are mbox parameters. If you pass any mbox parameters
  to mboxes, or use the targetPageParams function, those parameters appear here for
  use in audiences.
seo-title: Custom parameters
solution: Target
title: Custom parameters
topic: Standard
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Custom parameters{#custom-parameters}

Custom parameters are mbox parameters. If you pass any mbox parameters to mboxes, or use the targetPageParams function, those parameters appear here for use in audiences.

For more information, see [Passing Parameters to a Global Mbox](https://marketing.adobe.com/resources/help/en_US/target/ov/c_pass_parameters_to_global_mbox.html).

**Creating Audiences (9:58)**

This video includes information about using audience categories.

* Create audiences
* Define audience categories

>[!VIDEO](https://www.youtube.com/watch?v=wV9lVTSOxMk)

When creating a custom audience based on an mbox parameter, `mboxParameter` no longer prompts you for `mboxName`. mbox name is now optional. This change lets you use parameters from multiple mboxes or reference a parameter that has not yet been recorded on the edge.

To select the desired parameter:

* While creating a new audience, select a parameter name from the list, start typing the first characters of the desired parameter name, or type the full name of the desired parameter name.
* If you remember the mbox name, but not the parameter name, use the checkbox to filter on a known mbox passing the desired parameter.

Using either method, there is no link between the mbox and the parameter. The audience will work on the basis of parameter across all mboxes that pass that parameter.

If you edit an existing audience, the filtering criteria displays with the mbox name that was supplied during creation.

The audience's [definition details pop-up card](../../../c-target/c-audiences/c-audiences.md#section_11B9C4A777E14D36BA1E925021945780) shows the parameter name in the Rules section. There is no reference to the mbox used for filtering.

>[!NOTE]
>
>For custom audiences created before the Target 18.5.1 release (May, 22, 2018), mbox names will not display in the audience's definition pop-up card. You must re-save the custom audience to get the mbox name to be shown in the card.

