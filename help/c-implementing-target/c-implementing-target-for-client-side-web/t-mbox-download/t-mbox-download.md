---
description: To use Target Standard or Target Premium, add one line of code to call
  mbox.js.
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
seo-description: To use Target Standard or Target Premium, add one line of code to
  call mbox.js.
seo-title: mbox.js implementation
solution: Target
subtopic: Getting Started
title: mbox.js implementation
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# mbox.js implementation{#mbox-js-implementation}

To use Target Standard or Target Premium, add one line of code to call mbox.js.

You can use either of two library references: [!DNL mbox.js] or [!DNL at.js]. [Understanding the Target JavaScript Libraries](../../../c-implementing-target/c-considerations-before-you-implement-target/c-target-implement.md#concept_60B748DE4293488F917E8F1FA4C7E9EB) explains the differences between the two libraries.

>[!NOTE]
>
>The mbox.js library is still supported, but there will be no feature updates. All customers should migrate to at.js. For more information, see [Migrate to at.js from mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/t-target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

The single reference to [!DNL mbox.js] on each page provides the libraries needed for all of your activities. [!DNL mbox.js] calls [!DNL Target] from every page that references the [!DNL mbox.js] file. This enables [!DNL Target] to do the following:

* Deliver Target activities
* Track clicks
* Track most success metrics

>[!TIP]
>
>To simplify implementation, you could reference [!DNL mbox.js] in your global header.

**mbox.js Implementation Overview (8:52)**

This video explains how to implement [!DNL mbox.js].

* Select the correct settings for your [!DNL mbox.js] file
* Implement [!DNL Target] by adding the [!DNL mbox.js] file to the <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> of your site

>[!VIDEO](https://www.youtube.com/watch?v=f-A1zET6AwE)

You do not need to maintain different activity-specific versions of the file.

1. Reference [!DNL mbox.js] in the `<head>` section of each page on your site.

   `<script src="/ *`directory`*/ *`scripts`*/mbox.js"></script>`

   Where ` *`directory`*/ *`scripts`*` is the directory where you saved your [!DNL mbox.js] file after downloading it.
If you already have mboxes on your page from a legacy implementation, these mboxes can still be used in the new interface. The updated [!DNL mbox.js] file is still required, but these mboxes can be selected for activities and edited using the [!UICONTROL Visual Experience Composer].
