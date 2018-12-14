---
description: Display problems sometimes occur in the Visual Experience Composer (VEC)
  under certain conditions.
keywords: Targeting;visual experience composer;whitelist;white list;vec;troubleshoot
  visual experience composer;troubleshooting;tls;tls 1.2
seo-description: Display problems sometimes occur in the Visual Experience Composer
  (VEC) under certain conditions.
seo-title: Troubleshooting Issues Related to the Visual Experience Composer
solution: Target
title: Troubleshooting Issues Related to the Visual Experience Composer
uuid: 95126e92-75ce-4052-b061-7ca4ebb3136b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Troubleshooting Issues Related to the Visual Experience Composer{#troubleshooting-issues-related-to-the-visual-experience-composer}

Display problems sometimes occur in the Visual Experience Composer (VEC) under certain conditions.

## When I open my website in the Visual Experience Composer, the Target libraries do not load. (VEC only) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

Target adds two parameters ( `mboxEdit=1` and `mboxDisable=1`) while opening the website in the Visual Experience Composer.

If your website (specially Single Page Apps), trims our parameters or actually removes them while navigating from one page to another (without a page reload) the Target functionality breaks and the Target libraries do not load.
To avoid this problem, ensure that you do not trim or remove these two parameters.

## My page won't open in the EEC, or loads slowly. Activities or experiences load slowly in the VEC. (VEC only) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Several issues can affect page performance in the Target experience composers. Some common issues include:

* You do not have an mbox on the page.
* Your site uses proxy blocking, which does not allow the page to be opened in either experience composer.
* Your site doesn't allow itself to be opened in an iFrame.

If issues occur in the Enhanced Experience Composer, try turning off the Enhanced Experience Composer and use the Visual Experience Composer instead.

To disable the Enhanced Experience Composer, go to **[!UICONTROL Setup]** > **[!UICONTROL Preferences]** and turn off the **[!UICONTROL Enable Enhanced Experience Composer]** option.

Some users see the following error message in the console:

![](assets/error_message.jpg)

If neither the Visual Experience Composer nor the Enhanced Experience Composer works, use a browser extension like Requestly (Chrome or Firefox) or Modify Response Headers (Firefox) that can overwrite the X-Frames header options for your site and allow them to be loaded in iFrames, enabling the VEC. If you are unable to use browser extensions, use the Form Composer.

<table id="table_24793D197093447C94DA4E766B052A77"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>These plugins should be used only in the context of VEC editing. </p> <p>For the Requestly extension, whenever there is a need to remove headers, you should do either of following: </p> <p> 
     <ul id="ul_C903A746005D43B681FA0F5862387424"> 
      <li id="li_C58081214B1242AC8E6471A313AA2295"> <p>Add URL rules for the URL that you want to open in the VEC so that headers are removed for those URLs only. </p> </li> 
      <li id="li_38385DF774B54A9F831852440DFFF1FD"> <p>Enable the rule when you are editing in the VEC and disable the rule when you are not using the VEC. </p> </li> 
     </ul> </p> <p>For the Modify Response Header extension (Firefox), because you can't add a URL rule, you must do the following: </p> <p> 
     <ul id="ul_3D969F8BABBC432CA0744D2E7DD668F8"> 
      <li id="li_CD489672E1D3460392A703A3E873B999"> <p>Enable the rule when you are editing in the VEC and disable the rule when you are not using the VEC. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**To use the Requestly extension on Chrome or Firefox:**

1. Turn off the Enhanced Experienced Composer.
1. Install the Requestly browser extension on Chrome or Firefox.
1. Open the extension and configure it using the following:
1. Select **[!UICONTROL Modify headers]**.
1. Enter the following:

   * Rule name
   * Modification rules

      * Toggle **[!UICONTROL Add]** to **[!UICONTROL Remove]**.
      * Toggle **[!UICONTROL Request]** to **[!UICONTROL Response]**.
      * Enter "X-Frame-Options" as the header name.
      * Repeat previous steps and enter "x-frame-options" as the header name.

         >[!NOTE]
>
>Headers that are manipulated via Requestly are case sensitive.

      * Change **[!UICONTROL Equals]** to **[!UICONTROL Contains]** as the condition for the source URL and enter the URL of the activity that you are trying to load in the VEC.
      ![](assets/chrome_extension.png)


1. Click **[!UICONTROL Save]**.

   ![](assets/requestly.png)

   You should now be able to load the page quickly with the Visual Experience Composer.

**To use the Modify Response Headers extension on Firefox:**

1. Install the Modify Response Headers on Firefox and restart the browser.
1. From your Firefox extensions, select the Modify Response Headers extension.
1. Click **[!UICONTROL Preferences]**.
1. Select **[!UICONTROL Filter]** from the Action drop down.
1. In the Header Name field, enter: **[!UICONTROL X-Frame-Options]**.
1. Repeat Steps 4 and 5 to add a filter with **[!UICONTROL x-frame-options]**.
1. Click **[!UICONTROL Add]**.
1. Click **[!UICONTROL Start]**.

![](assets/firefox_extension.png)

After setting up an extension, open Target. Your pages should now load in the Visual Experience Composer, even if the Enhanced Experience Composer is disabled.

## My page does not display in the VEC (VEC only) {#section_87B3BEA4B6174CFDA6C9A69A1A051FA1}

* The browser is not supported.
* The browser is blocking a non-secure page on a secure site.

   Click the icon to the left of the URL in the browser address bar and click **[!UICONTROL Disable protection on this page]**
* You entered an invalid URL.
* You have not entered a default URL in your account setup page.

## When launching a URL for a VEC activity, the console displays the following error message: "Uncaught ReferenceError:_AT is not defined." (VEC only) {#section_BB5B9B629AC4452496A82943EFF72B85}

This error occurs if you try to deliver Visual Experience Composer (VEC) campaigns and you have not updated `mbox.js` downloaded from the Target user interface with the [!UICONTROL Support Visual Experience Composer Activities] option enabled ( [!UICONTROL Setup] > [!UICONTROL Implementation] > [!UICONTROL mbox.js] > [!UICONTROL Edit mbox.js Settings]).

Ensure that this setting is enabled, then download and update `mbox.js` on your website.

## The VEC appears broken when I use browse mode. (VEC only) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

While using browse mode, if you access a URL that does not have target.js or contains a frame-buster header, the Visual Experience Composer appears broken. Due to browser security concerns, Target cannot access the URL you navigated to.
