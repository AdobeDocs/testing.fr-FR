---
description: Information to help your technical staff understand the mbox.js implementation
  and how it might affect your site.
keywords: implementation;mbox.js;dom manipulation library;target.js;visual experience
  composer;iframe;angular sites;single page applications;single page app;SPA
seo-description: Information to help your technical staff understand the mbox.js implementation
  and how it might affect your site.
seo-title: What mbox.js does
solution: Target
subtopic: Getting Started
title: What mbox.js does
topic: Standard
uuid: 5529d620-4a33-479c-871f-18dcd59abb07
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# What mbox.js does{#what-mbox-js-does}

Information to help your technical staff understand the mbox.js implementation and how it might affect your site.

Target Standard requires [!DNL mbox.js] version 58 or later. For instructions on how to download and update [!DNL mbox.js], see [Mbox Implementation](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/t-mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).

For Target Standard, [!DNL mbox.js] calls another JavaScript file, [!DNL target.js]. [!DNL Target.js] is hosted by Adobe and is automatically updated by Adobe. There is nothing you need to do to update [!DNL target.js], and there are no client-specific customizations.

[!DNL Target.js] creates an mbox called `target-global-mbox` in the `<head>` section of your page.

[!DNL Target.js] is called from [!DNL mbox.js] by a line of JavaScript code added to the [!UICONTROL Extra JavaScript] field in [!DNL mbox.js]. The only way to disable [!DNL target.js] is not to include this line of code, thus also disabling [!DNL Target].

[!DNL Target.js] has two functions in [!DNL Target]:

* DOM manipulation
* Enables visual elements of the [!UICONTROL Visual Experience Composer]

## DOM Manipulation {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] controls the DOM manipulation library used by Standard. To display the content of a website, [!DNL target.js] references [!DNL sizzle.js] (version1.10.8-pre). [!DNL Sizzle.js] enables the HTML element selectors. Other than [!DNL sizzle.js], only native JavaScript is used. No jquery is required.

In addition, the following snippet is used for polling the DOM:
`https://github.com/dperini/ContentLoaded`

## Target.js and the Visual Experience Composer {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

When you use the [!UICONTROL Visual Experience Composer] to set up an experience for an activity, your web page is opened in an iFrame. When the iFrame is loaded, Standard sends an HTML5 `postMessage` API call. [!DNL Target.js] detects any `postMessage` calls and includes the following JavaScript libraries on the website:

* For thumbnail generation: [!DNL https://html2canvas.hertzen.com/]
* For cross-domain query: [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css], used to send messages across the iFrames. These scripts allow Adobe to send data between the pages.

## Considerations for Angular Sites and Single-Page Applications {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

If you are implementing Target in an Angular site or in any Single-Page Application (SPA), you should use the `at.js` library instead of `mbox.js`.

For more information, see [at.js Implementation](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/c-target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).
