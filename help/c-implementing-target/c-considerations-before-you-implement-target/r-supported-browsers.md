---
description: The Adobe Target application and content delivery has been tested across
  a wide range of browsers and devices.
keywords: Browsers;Prerequisites;Requirements;internet explorer;chrome;firefox;safari;android;surface
seo-description: The Adobe Target application and content delivery has been tested
  across a wide range of browsers and devices.
seo-title: Supported browsers
solution: Target
subtopic: Getting Started
title: Supported browsers
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Supported browsers{#supported-browsers}

The Adobe Target application and content delivery has been tested across a wide range of browsers and devices.

For additional important information about TLS, see [TLS (Transport Layer Security) Encryption Changes](../../c-implementing-target/c-considerations-before-you-implement-target/c-tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## Target Standard/Premium Interface {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

The [!DNL Target Standard/Premium] interface supports the following browsers and devices:

<table id="table_28F120EDC9714B60B315EA1ED0FF6582"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Device Type </th> 
   <th colname="col3" class="entry"> Browser Version </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> Windows </td> 
   <td colname="col3"> <p> 
     <ul id="ul_B6F9F5BC38E249ECA5AA512B94082BF9"> 
      <li id="li_5B63829413D24320AB812546794A7934"> <p>Microsoft Internet Explorer 11 </p> </li> 
      <li id="li_BA7EF5BCBC4648B49839A8B4F31F9FBA"> <p>Microsoft Edge </p> </li> 
      <li id="li_9441697F249C4AB28E96FC1DC8A27B6F"> <p>Google Chrome (Latest, Latest minus 1) </p> </li> 
      <li id="li_BA8F65110C6643ADA40FB334F61EF36F"> <p>Mozilla Firefox (Latest, Latest minus 1) </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Mac </td> 
   <td colname="col3"> <p> 
     <ul id="ul_BE238F7BB80742D98A361A3A9EFA0B05"> 
      <li id="li_B1D1E029963C4DBD8CD05D4E7F3D2395">Firefox (Latest, Latest minus 1) </li> 
      <li id="li_84EA2E024EB34E38AF302974FE7A1CAA">Chrome (Latest, Latest minus 1) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Content Delivery {#section_1045A946056441268D40025529918D3D}

Content delivery has been tested across the following browsers and devices:

<table id="table_ED385191F8BC44549BF263090688840A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Device Type </th> 
   <th colname="col2" class="entry"> Browser Version </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Windows </td> 
   <td colname="col2"> <p> 
     <ul id="ul_86C7D2C185A14DDAA87E0A59B91431B9"> 
      <li id="li_865C65F014044440A800DD2306BD6453"> <p>Internet Explorer 9 and 10. Tested in emulation mode. </p> <p> <p>Note:  at.js 1.3.0 (and later) no longer supports content delivery on Microsoft Internet Explorer 9. </p> </p> </li> 
      <li id="li_409DEA504A4A4894B15EAADC7204B8BB"> <p> Internet Explorer 11 </p> </li> 
      <li id="li_84B7776717464FDDAB534189A85C217D"> <p>Microsoft Edge </p> </li> 
      <li id="li_91B58BFD0B5C491AB27F5D4241545EE7"> <p>Chrome (Latest, Latest minus 1) </p> </li> 
      <li id="li_E8C5BD70AAA449AE81A43D0AD3F62B56"> <p> Firefox (Latest, Latest minus 1) </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mac </td> 
   <td colname="col2"> <p> 
     <ul id="ul_550A4C0C8E384C48ADE8C9E38BB3662F"> 
      <li id="li_442E1CE6507146A795B774B8B28F1F3F"> <p>Apple Safari (Latest) </p> <p>For more information about how Safari handles first- and third-party cookies, see <a href="../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-cookie-behavior.md#concept_4D8107E193B64168A3C0B85B51612991" format="dita" scope="local"> Target Cookie</a>. </p> </li> 
      <li id="li_81347CC1A29946EF9AFC4BBBEFEBBF74"> <p>Firefox (Latest, Latest minus 1) </p> </li> 
      <li id="li_642DBDCAB3F3423488D790C8D368961A"> <p>Chrome (Latest, Latest minus 1) </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile/Tablet </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4747E73A79234E4E9B1AC1BA805475BB"> 
      <li id="li_75B42139B1F44B14800B752135E72181"> <p>Apple iOS (Latest) </p> </li> 
      <li id="li_F0EB81D5CCD14BF2A00ADC384EE7617A"> <p>Android devices and tablets (Android 4 and later) </p> </li> 
      <li id="li_18E1FF948A3D4869942F2E4DA0791B43"> <p>Microsoft Surface (Windows 8.1) </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

For [!DNL at.js] implementations, Target displays default content in earlier versions of Internet Explorer and possibly in earlier versions of the above-listed browsers. For [!DNL mbox.js] implementations, Target tries to render content but might not be successful.

Target displays default content in browsers not listed above and in browsers using [quirks mode](https://en.wikipedia.org/wiki/Quirks_mode). at.js requires a doctype that renders in standard mode, for example: `<!DOCTYPE html>` .

>[!NOTE]
>
>Adobe Delivery infrastructure is being secured to NOT support TLS 1.0 devices and browsers after September 12, 2018. See [TLS (Transport Layer Security) Encryption Changes](../../c-implementing-target/c-considerations-before-you-implement-target/c-tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) to understand the overall impact of this change.
