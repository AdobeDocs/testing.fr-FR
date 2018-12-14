---
description: Information about implementing Adobe Target without using a tag manager
  (Adobe Launch or Dynamic Tag Management).
keywords: order confirmation;orderConfirmPage
seo-description: Information about implementing Adobe Target without using a tag manager
  (Adobe Launch or Dynamic Tag Management).
seo-title: Implement Target without a tag manager
solution: Target
subtopic: Getting Started
title: Implement Target without a tag manager
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Implement Target without a tag manager{#implement-target-without-a-tag-manager}

Information about implementing Adobe Target without using a tag manager (Adobe Launch or Dynamic Tag Management).

## Implement Target without a tag manager {#topic_397FFA3D6918456BBE02A9FBE9537894}

Information about implementing Adobe Target without using a tag manager (Adobe Launch or Dynamic Tag Management).

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) is the preferred method for implementing Target and the at.js library. The following information is not applicable when using Adobe Launch to implement Target.

## at.js Configurations {#concept_2FA0456607D04F82B0539C5BF5309812}

Information to help you set several settings on the `at.js` Settings page.

<!-- 

ov2/c_target-atjs-advanced-settings.xml

 -->

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) is the preferred method for implementing Target and the at.js library. The following information is not applicable when using Adobe Launch to implement Target.

>[!NOTE]
>
>You can override settings in the `at.js` library, rather than configuring the settings in the Target Standard/Premium UI or by using REST APIs. For more information, see [targetGlobalSettings()](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#concept_8DACBC47ABDE4279BB102B42609FE506).

To open the [!UICONTROL Settings] page:

1. Click **[!UICONTROL Setup]** > **[!UICONTROL Implementation]**.
1. Select **[!UICONTROL at.js]** > **[!UICONTROL Edit at.js Settings]**.

## Content Delivery Settings {#section_118D290DFC444509AD8E4AE86C9D92C0}

Please consult with Client Care before changing these settings. These settings are required for most implementations.

<table id="table_51A0B36B374A4F2FA36ADCFE05E4F28C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Autocreate global mbox </td> 
   <td colname="col2"> <p>Select whether to embed the global mbox call in the <span class="filepath"> at.js </span> file to automatically fire on each page load. </p> <p>Changing this setting affects both <span class="filepath"> at.js </span> and <span class="filepath"> mbox.js </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Global mbox name </td> 
   <td colname="col2"> <p>Select a name for the global mbox. By default, this name is <span class="codeph"> target-global-mbox </span>. </p> <p> Special characters, including ampersands (&amp;), can be used in mbox names with <span class="codeph"> at.js </span>. </p> <p>Changing this setting affects both <span class="filepath"> at.js </span> and <span class="filepath"> mbox.js </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Advanced Settings {#section_33B697B77BA64A01B5939D7EC75231F2}

<table id="table_AFA97284FD5B4495A0CBE7B9A1C0EBE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Client Code </td> 
   <td colname="col2"> <p>The client code is a client-specific sequence of characters often required when using the <span class="keyword"> Target </span> APIs. </p> <p>This setting cannot be changed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IMS Organization ID </td> 
   <td colname="col2"> <p> This ID ties your implementation to your <span class="keyword"> Adobe Experience Cloud </span> account. </p> <p>This setting cannot be changed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profile Lifetime </td> 
   <td colname="col2"> <p>This setting determines how long visitor profiles are stored. By default, profiles are stored for two weeks. This can be increased up to 90 days. </p> <p>To change the <span class="wintitle"> Profile Lifetime </span> setting, contact <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="http" scope="external"> Client Care </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> X-Domain </td> 
   <td colname="col2"> <p>Determines whether the browser sets cookies in your own domain (1st party cookies), Target's domain, or both. </p> <p>Changing this setting affects both <span class="filepath"> at.js </span> and <span class="filepath"> mbox.js </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout </td> 
   <td colname="col2"> <p>If <span class="keyword"> Target </span> does not respond with content within the defined period, the server call times out and default content is displayed. Additional calls continue to be attempted during the visitor's session. The default is 5 seconds. </p> <p>Changing this setting affects both <span class="filepath"> at.js </span> and <span class="filepath"> mbox.js </span>. </p> <p>The <span class="filepath"> at.js </span> library uses the timeout setting in <span class="codeph"> XMLHttpRequest </span>. The timeout starts when the request is fired and stops when <span class="keyword"> Target </span> gets a response from the server. For more information, see <span class="codeph"> <a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout" format="https" scope="external"> XMLHttpRequest.timeout </a> </span> on the Mozilla Developer Network. </p> <p>If the specified timeout occurs before receiving the response, default content is shown and the visitor might be counted as a participant in an activity because all data collection happens on the <span class="keyword"> Target </span> edge. If the request reaches the <span class="keyword"> Target </span> edge, the visitor is counted. </p> <p>Consider the following when configuring the timeout setting: </p> <p> 
     <ul id="ul_F9154E3EC6BF41ECA49216BF4373AF6C"> 
      <li id="li_C26553FD85B94850944F623CA94CD370"> <p>If the value is too low, users might see default content most of the time, although the visitor could be counted as a participant in the activity. </p> </li> 
      <li id="li_6BDF05026AA747D2A494BE5E5A199717"> <p>If the value is too high, visitors might see blank regions on your web page or blank pages if you use body hiding for extended periods of time. </p> </li> 
     </ul> </p> <p>To get a better understanding of mbox response times, look at the Network tab in your browser's Developer Tools. You can also use third-party web performance monitoring tools, such as Catchpoint. </p> <p> <p>Note:  The <a href="../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#concept_8DACBC47ABDE4279BB102B42609FE506" format="dita" scope="local"> visitorApiTimeout setting </a> ensures that <span class="keyword"> Target </span> doesn't wait for the Visitor API response for too long. This setting and the <span class="wintitle"> Timeout </span> setting for <span class="codeph"> at.js </span> described here do not affect each other. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Legacy Browser Support </td> 
   <td colname="col2"> <p> <p>Note:  The <span class="wintitle"> Legacy Browser Support </span> option is available in <span class="codeph"> at.js </span> version 0.9.3 and earlier. This option was removed in <span class="codeph"> at.js </span> version 0.9.4. For a list of browsers supported by <span class="codeph"> at.js </span>, see <a href="../../../c-implementing-target/c-considerations-before-you-implement-target/r-supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100" format="dita" scope="local"> Supported Browsers </a>. </p> </p> <p> Legacy browsers are older browsers that do not fully support CORS (Cross Origin Resource Sharing). These browsers include: Internet Explorer browsers earlier than version 11 and Safari versions 6 and below. If Legacy Browser Support is disabled, Target does not deliver content or count visitors in reports on these browsers. If this option is enabled, it is recommended to do quality assurance across older browsers to ensure a good customer experience. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Code Settings {#section_D41C905D0F8149949F525C85F2CCFF7F}

<table id="table_05B4524D0E204B6390FF6192A846ABA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Library Header </td> 
   <td colname="col2"> <p>Add any custom JavaScript to include at the top of the library. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Library Footer </td> 
   <td colname="col2"> <p>Add any custom JavaScript to include at the bottom of the library. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Download at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instructions to download the  library using the Target interface or the Download API.

<!-- 

ov2/c_target-configure-atjs.xml

 -->

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) is the preferred method for implementing Target and the at.js library. The following information is not applicable when using Adobe Launch to implement Target.

>[!IMPORTANT]
>
>The Target team maintains only two versions of [!DNL at.js]—the current version and the second-latest version. Please upgrade [!DNL at.js] as necessary to ensure that you are running a supported version. For more information about what's in each version, see [at.js Version Details](../../../c-implementing-target/c-implementing-target-for-client-side-web/r-target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

## Download at.js Using the Target Interface {#section_1F5EE401C2314338910FC57F9592894E}

To download [!DNL at.js] from the [!DNL Target] interface:

1. Click **[!UICONTROL Setup]** > **[!UICONTROL Implementation]**.
1. Select **[!UICONTROL at.js]**.
1. Click **[!UICONTROL Download at.js]**.

## Download at.js Using the Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}

To download [!DNL at.js] using the API.

1. Get your client code.

   Your client code is available at the top of the **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** page of the [!DNL Target] interface.

1. Get your admin number.

   Load this URL:

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Replace ` < *`client code`*>` with the client code from Step 1.

   The result of loading this URL should look similar to the following example:

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   In this example, "6" is the admin number.

1. Download [!DNL at.js].

   Load this URL with the following structure:

   ```
   https://admin<varname>admin number</varname>>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code </varname>version=<version number>
   ```

   * Replace ` < *`admin number`*>` with your admin number.
   * Replace ` < *`client code`*>` with the client code from Step 1.
   * Replace ` < *`version number`*>` with the desired [ [!DNL at.js] version number ](../../../c-implementing-target/c-implementing-target-for-client-side-web/r-target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) (for example, 1.6.2).
   >[!IMPORTANT]
>
>The Target team maintains only two versions of [!DNL at.js]—the current version and the second-latest version. Please upgrade [!DNL at.js] as necessary to ensure that you are running a supported version. For more information about what's in each version, see [at.js Version Details](../../../c-implementing-target/c-implementing-target-for-client-side-web/r-target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

   Loading this URL starts the download of your customized [!DNL at.js] file.

## at.js Implementation {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js should be implemented in the `<head>` element of every page of your website.

A typical implementation of Target not using a tag manager like [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) or [Dynamic Tag Management](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96) looks like this:

```
<!doctype html> 
<html> 
 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head> 
 
<body> 
    The default content of the page 
</body> 
 
</html>
```

Consider the following important notes:

* The HTML5 Doctype (e.g., `<!doctype html>`) should be used. Unsupported or older doctypes could result in Target not being able to make a request.
* Preconnect and Prefetch are options that might help your web pages load faster. If you use these configurations, ensure that you replace `<client code>` with your own client code, which you can obtain from the **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** page.
* If you have a data layer, it is optimal to define as much of it as possible in the `<head>` of your pages before at.js loads. This placement provides the maximum ability to leverage this information in Target for personalization.
* Special Target functions, such as `targetPageParams()`, `targetPageParamsAll()`, Data Providers, and `targetGlobalSettings()` should be defined after your data layer and before at.js loads. Alternatively, these could be saved in the [!UICONTROL Library Header] section of the [!UICONTROL Edit at.js Settings] page and saved as part of the at.js library itself. For more information on these functions, see [at.js functions](../../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#topic_8E33F5CDAB774AB891304DE2090AF80E).
* If you use JavaScript helper libraries, such as jQuery, include them before Target so you can leverage their syntax and methods when building Target experiences.
* Include at.js in the `<head>` of your pages.

## Track Conversions {#task_E85D2F64FEB84201A594F2288FABF053}

The Order Confirmation mbox records details about orders on your site and allows reporting based on revenue and orders. The Order Confirmation mbox can also drive recommendation algorithms, such as "People who bought product x also bought product y."

<!-- 

ov/t_create_orderconfirm-page-mbox-atjs.xml

 -->

>[!NOTE]
>
>If users make purchases on your website, we recommend implementing an Order Confirmation mbox even if you use Analytics for Target (A4T) for your reporting.

1. In your order details page, insert the mbox script following the model below.
1. Replace the WORDS IN CAPITAL LETTERS with either dynamic or static values from your catalog.

   >[!NOTE]
>
>Use comma delimiting to separate multiple product IDs.

   **Tip:** You can also pass order information in any mbox (it does not need to be named `orderConfirmPage`). You can also pass order information in multiple mboxes within the same campaign.

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

The Order Confirmation mbox uses the following parameters:

<table id="table_CEB2E2F2265142D89672E124CB4C880B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> orderId </span> </p> </td> 
   <td colname="col2"> <p> Unique value to identify an order for conversion counting. </p> <p>The <span class="codeph"> orderId </span> must be unique. Duplicate orders are ignored in reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> orderTotal </span> </p> </td> 
   <td colname="col2"> <p> Monetary value of the purchase. </p> <p>Do not pass the currency symbol. Use a decimal point (not a comma) to indicate decimal values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> productPurchasedId </span> (Optional) </p> </td> 
   <td colname="col2"> <p> Comma-separated list of product IDs purchased in the order. </p> <p> These product IDs display in the audit report to support additional reporting analysis. </p> </td> 
  </tr> 
 </tbody> 
</table>

