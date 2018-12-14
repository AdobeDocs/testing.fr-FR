---
description: The way Target makes and responds to calls from your page depends on
  the version of the Target library you are using, whether the Experience Cloud Visitor
  ID implementation is present, and whether the visitor ID exists.
seo-description: The way Target makes and responds to calls from your page depends
  on the version of the Target library you are using, whether the Experience Cloud
  Visitor ID implementation is present, and whether the visitor ID exists.
seo-title: Target page methods by mbox.js library version
title: Target page methods by mbox.js library version
uuid: 66f7753e-d9c1-4efa-8b10-fd637c8f53f6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Target page methods by mbox.js library version{#target-page-methods-by-mbox-js-library-version}

The way Target makes and responds to calls from your page depends on the version of the Target library you are using, whether the Experience Cloud Visitor ID implementation is present, and whether the visitor ID exists.

>[!NOTE]
>
>If you use [!DNL at.js], all calls are made using JSON. This page provides details about [!DNL mbox.js] library versions. The behaviors described in the scenarios below do not apply to [!DNL at.js].

This section provides information about how each version of the [!DNL Target] library responds to the [!DNL Target] call from your page in each of the following scenarios.

There are several types or endpoints, depending on your implementation and library version. You should be familiar with each type to understand how [!DNL Target] responds to calls in each scenario.

<table id="table_9B6FA7E1F7E5470889FDA9D7C6F66CA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type/Endpoint </th> 
   <th colname="col2" class="entry"> Call Method </th> 
   <th colname="col3" class="entry"> Response Content </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> autocreate global mbox - synchronous </td> 
   <td colname="col2"> document.write to make call </td> 
   <td colname="col3"> JavaScript without document.write() </td> 
  </tr> 
  <tr> 
   <td colname="col1"> autocreate global mbox - asynchronous </td> 
   <td colname="col2"> createElement() to append call to body </td> 
   <td colname="col3"> JavaScript without document.write() </td> 
  </tr> 
  <tr> 
   <td colname="col1"> standard </td> 
   <td colname="col2"> <p>document.write to make call </p> </td> 
   <td colname="col3"> JavaScript with document.write() </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ajax </td> 
   <td colname="col2"> <p>createElement() to append call to body </p> </td> 
   <td colname="col3"> JavaScript without document.write() </td> 
  </tr> 
  <tr> 
   <td colname="col1"> json </td> 
   <td colname="col2"> XMLHTTPrequest() to make call </td> 
   <td colname="col3"> returns JSON response </td> 
  </tr> 
 </tbody> 
</table>

>[!IMPORTANT]
>
>For any type but standard, all custom code and offers should be written to support an ajax environment. For example, if you use a JavaScript that includes `document.write()`, the script will not work as expected.

## No Visitor ID Implementation {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

If you are using [!DNL Target Standard] or [!DNL Premium] with [!DNL mbox.js], and you have enabled [!UICONTROL Create Global Mbox] for your account, the **autocreate global mbox synchronous** type of call and response is made, regardless of [!DNL mbox.js] version.

If you write your own custom code rather than using the [!UICONTROL Visual Experience Composer] actions, make sure your code is appropriate for an ajax environment. For example, if you use a JavaScript that includes `document.write()`, the script will not work as expected.

>[!NOTE]
>
>Multiple ajax mbox calls with the same mbox name but different parameters will not work on the same page. Only the first call will be made.

If you use "auto-create global mbox" but also have `mboxCreate` calls on your page, for example, if you are implementing [!DNL Target Standard] or [!DNL Premium] on a page that previously used in a legacy implementation, the global mbox calls are made using the** autocreate global mbox - standard** endpoint and the `mboxCreate` calls are made using the **standard** endpoint. The **standard** endpoint uses `document.write()` to make the call and to respond. This blocks the page load, including content delivered in the ajax response, until all information is downloaded.

If you use only mboxCreate, for example on pages created using [!DNL Target Classic], the page works as it always has.

| Creation Method | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocreate global mbox | autocreate global mbox - synchronous | autocreate global mbox - synchronous | autocreate global mbox - synchronous | autocreate global mbox - synchronous |
| mboxCreate | standard | standard | standard | standard |

## Visitor ID Implementation Present, but No Visitor ID Set {#section_29888A119C7A4753AD287FC845AA63F4}

If no visitor ID has been set, there is no [!DNL Experience Cloud] visitor cookie for the user. The page calls out to the Visitor ID service to get the visitor ID. Target waits for the response with the ID making the call to [!DNL Target].

>[!NOTE]
>
>[!DNL Mbox.js] v58  is strongly recommended to ensure that the visitor ID returns before the Target call is made.

If you are using [!DNL mbox.js] version 57 in this scenario, everything works as it does if there is no visitor ID implementation, as described in the previous scenario. Beginning with [!DNL mbox.js] version 58, the [!DNL Experience Cloud Visitor ID] service returns with a visitor ID before [!DNL Target] calls are made. This ensures that audience data shared through the Profiles and Audiences core service are available for the first [!DNL Target] call in the visitor's session. To avoid flickering of default content before test content returns, [!DNL Target] hides the `<BODY>` until the visitor ID service returns. In version 58, `display:none` is used to hide the page. This creates some problems with responsive sites, so beginning with version 59, `opacity:0` is used to hide the content.

| Creation Method | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocreate global mbox | autocreate global mbox - synchronous | autocreate global mbox - asynchronous | autocreate global mbox - asynchronous | autocreate global mbox - asynchronous |
| mboxCreate | standard | ajax | ajax | ajax |

## Visitor ID Implementation Present, and Visitor ID Exists {#section_9CD4AE4C8186425D886398BC3CE6C46D}

If the visitor ID cookie exists, [!DNL Target] does not need to make a call to the Visitor ID service. In this case, there is no need to wait for the Visitor ID service before displaying content. For versions 57 to 59, the **autocreate global mbox - synchronous** type is used, so the page waits for the call to [!DNL Target] to return before continuing to load. This ensures no flicker of default content is seen. For v60, the **global mbox-asynchronous type** is used to ensure [!DNL Target] waits for the [!DNL Experience Cloud] opt-out service to respond. The opt-out service is part of the Data Co-op releasing in the fall of 2016. Because all calls are returned using ajax , `document.write()` should not be used with [!DNL mbox.js] version 60.

| Creation Method | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocreate global mbox | autocreate global mbox - synchronous | autocreate global mbox - synchronous | autocreate global mbox - synchronous | autocreate global mbox - asynchronous (to support development of the Data Co-op, which will be released later in 2016) |
| mboxCreate | standard | standard | standard | ajax |

