---
description: List of functions that can be used with at.js.
keywords: adobe.target.notification;element;selector;notification;extension
seo-description: List of functions that can be used with at.js.
seo-title: at.js functions
solution: Target
subtopic: Getting Started
title: at.js functions
topic: Standard
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# at.js functions{#at-js-functions}

List of functions that can be used with at.js.

## adobe.target.getOffer(options) {#reference_C81525D1598A4A1199740DCAB81A7FDF}

This function fires a request to get a Target offer.

<!-- 

ov2/r_target-atjs-getoffer.xml

 -->

Use with `adobe.target.applyOffer()` to process the response or use your own success handling. The options parameter is mandatory and has the following structure:

<table id="table_53113151402049689D0401DF9C7857D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Required </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mbox </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> Yes </td> 
   <td colname="col4"> Mbox name </td> 
  </tr> 
  <tr> 
   <td colname="col1"> params </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>Mbox parameters. An object of key-value pairs that has the following structure: </p> <p> <span class="codeph"> { "param1": "value1", "param2": "value2"} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> success </td> 
   <td colname="col2"> Function </td> 
   <td colname="col3"> Yes </td> 
   <td colname="col4"> <p> Callback to be executed when we got a response from the server. The success callback function will receive a single parameter that represents an array of offer objects. Here is a success callback, example: </p> <p> <span class="codeph"> function handleSuccess(response){......} </span> </p> <p>See Responses below for details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> error </td> 
   <td colname="col2"> Function </td> 
   <td colname="col3"> Yes </td> 
   <td colname="col4"> <p>Callback to be executed when we got an error. There are a couple of cases that are considered erroneous: </p> <p> 
     <ul id="ul_824F701E2C5B4B0391C97315CC73C89D"> 
      <li id="li_24547266DAA94DBCA9C1F0C702ED30D8">HTTP status code different from 200 OK </li> 
      <li id="li_B373A506F5E644F6AE7D41E811E5BCDF">Response can not be parsed. For example we poorly constructed JSON or HTML instead of JSON. </li> 
      <li id="li_D71425FFA2C34E278E18D4F96DA5C679">Response contains the "error" key. For example an exception was thrown on the edge a request could not be properly processed. We could get an error when an mbox is blocked and we could not retrieve any content for it etc. </li> 
     </ul> </p> <p>The error callback function will receive two parameters: status and error. Here is an error callback example: </p> <p> <span class="codeph"> function handleError(status, error){......} </span> </p>See Error Responses below for details. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> timeout </td> 
   <td colname="col2"> Number </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>Timeout in milliseconds. If not specified, the default timeout in <span class="filepath"> at.js </span>will be used. The default timeout can be set from the Target UI under <span class="uicontrol"> Setup </span> > <span class="uicontrol"> Implementation </span> > <span class="uicontrol"> Edit Mbox.js Settings </span> > <span class="uicontrol"> Timeout </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Examples {#section_97C2D2E03E6549BEA7F4873E3F5E4A0D}

Adding parameters with getOffer() and using applyOffer() for success-handling:

```
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Adding parameters and profile parameters with getOffer() and using applyOffer() for success-handling:

```
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2, 
     "profile.age": 27, 
     "profile.gender": "male" 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Using custom timeout and custom success-handling with getOffer():

"YOUR_OWN_CUSTOM_HANDLING_FUNCTION" is a placeholder for a function the customer would define.

```
adobe.target.getOffer({     
  "mbox": "target-global-mbox",   
  "success": function(offer) { 
    YOUR_OWN_CUSTOM_HANDLING_FUNCTION(offer);   
  }, 
  "error": function(status, error) {                 
    console.log('Error', status, error);   
  },   
  "timeout": 2000 
});
```

## Responses {#section_CF9FD236EF794620BCBF84EB80160183}

The response parameter passed to the success callback will be an array of actions. An action is an object that usually has the following format:

<table id="table_07840C5C381C4FE191ACA7F833C74EEB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> action </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Type of action to be applied to the identified element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> selector </td> 
   <td colname="col2"> Sting </td> 
   <td colname="col3"> <p>Represents a Sizzle selector. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cssSelector </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>DOM native selector, used for element pre-hiding. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> content </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>The content to be applied to the identified element. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Example**

```
{ 
    "sessionId": "1444512212156-384616", 
    "tntId": "1444512212156-384616.17_35", 
    "offers": [{ 
        "plugins": ["<script type=\"text/javascript\">\r\n/*mboxHighlight+ (1of2) v1 ==> Response Plugin*/\r\nwindow.ttMETA=(typeof(window.ttMETA)!='undefined')?window.ttMETA:[];window.ttMETA.push({'mbox':'target-global-mbox','campaign':'at: redirect ootb','experience':'Experience B','offer':'/at_redirect_ootb/experiences/1/pages/0/1442082890250'});window.ttMBX=function(x){var mbxList=[];for(i=0;i<ttMETA.length;i++){if(ttMETA[i].mbox==x.getName()){mbxList.push(ttMETA[i])}}return mbxList[x.getId()]}\r\n</script>"], 
        "actions": { 
            "content": [{ 
                "passMboxSession": false, 
                "selector": "body", 
                "action": "redirect", 
                "url": "https://example.com/04.html", 
                "includeAllUrlParameters": true 
            }] 
        } 
    }] 
}
```

## Error Responses {#section_1ACCE79AF2CB4FA2AD1371EA06AF129F}

The "status" and "error" parameters passed to the error callback will have the following format:

<table id="table_D201E1639CAA454FAA2F9D8F131B7A8C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> status </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Represents the error status. This parameter can have the following values: </p> <p> 
     <ul id="ul_708148E9CA5F435C914CF247C1D9E0E3"> 
      <li id="li_D74FB1FCB39542E78AB348D92195C850">timeout <p> Indicates that the request timed out </p> </li> 
      <li id="li_D87CC491BDD84B2B88FD365CA7C74F49">parseerror <p> Indicates that the response could not be parsed, for example if we receive HTML or plain text instead of JSON </p> </li> 
      <li id="li_F19E6178AD8F45238B5264225555881C">error <p>Indicates a general error like we received HTTP status different from 200 OK </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> error </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Contains additional data like exception message or anything else that might be useful for troubleshooting. </p> </td> 
  </tr> 
 </tbody> 
</table>

## adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

This function is for applying the response content.

<!-- 

ov2/r_target-atjs-applyoffer.xml

 -->

>[!NOTE]
>
>`applyOffer` requires the `mbox` parameter. If no mbox name is specified, an error occurs.

The options parameter is mandatory and has the following structure:

<table id="table_FE131775E30240C89BF02369FF48AC6F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Required </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>mbox </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>Mbox name </p> <p>With at.js 1.3.0 (and later) Target enforces that the mbox key is used. This key has been required in the past, but Target now enforces its use to ensure that Target has proper validation and customers are using the function correctly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>selector </p> </td> 
   <td colname="col2"> <p>String or DOM Element </p> </td> 
   <td colname="col3"> <p>No </p> </td> 
   <td colname="col4"> <p>HTML element or CSS selector used to identify the HTML element where Target should place the offer content. If selector is not provided, Target assumes that the HTML element we should use is HTML HEAD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offer </p> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>An array actions that should be applied to the element. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Example {#section_D8D6A17B73DE4542937CDB687193A5CC}

The following example shows how to use `getOffer` and `applyOffer` together:

```
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```

## adobe.target.trackEvent(options) {#reference_7E0F19368F9C4BC38F1E5DC5E717E487}

This function fires a request to report user actions, such as clicks and conversions. It does not deliver activities in the response.

<!-- 

ov2/r_target-atjs-trackevent.xml

 -->

These event-tracking mbox calls can then be used to define metrics in activities. For more information, see [Success Metrics](../../c-activities/r-success-metrics/r-success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) and [Track Conversions](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

Here are the API details:

<table id="table_F9A0292CB561413F8039E045F8B05E6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Required </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mbox </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> Yes </td> 
   <td colname="col4"> <p>Mbox name </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> selector </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>CSS selectors used to find the HTML elements. The event listeners will be attached to found elements. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> type </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>Represents a registered event type. It can be both HTML known events like: click, mousedown ,etc., as well as custom HTML events. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> preventDefault </td> 
   <td colname="col2"> Boolean </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>Indicates whether to use <span class="codeph"> event.preventDefault() </span> in the event listener callback. Defaults to false. </p> <p> <p>Note:  Only <span class="codeph"> form[submit] </span>, <span class="codeph"> a[click] </span> are supported. Other scenarios are not supported due to complexity and huge amount of scenarios to support. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> params </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>Mbox parameters. An object of key-value pairs that has the following structure: </p> <p> <span class="codeph"> { "param1": "value1", "param2": "value2"} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> timeout </td> 
   <td colname="col2"> Number </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>Timeout in milliseconds. </p> <p>If not specified, default value is used: </p> <p> <span class="codeph"> {...timeoutInSeconds: 0.15...} </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> success </td> 
   <td colname="col2"> Function </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>A callback function used to signal that event has been reported. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> error </td> 
   <td colname="col2"> Function </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> <p>A callback function used to signal that event could not be reported. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Example**

```
<a href="https://asite.com">click me!</a> 
```

plus javaScript code to assign `trackEvent`:

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

Or:

```
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>In case the mandatory fields are not set, no request is executed, and an error is thrown.

## mboxCreate(mbox,params) {#reference_E68805FE86C64792B2066DB17B253D74}

Executes a request and applies the offer to the closest DIV with mboxDefault class name.

<!-- 

ov2/r_target-atjs-mboxcreate.xml

 -->

This function is built into [!DNL at.js] mostly to ease the transition from [!DNL mbox.js] to [!DNL at.js]. A newer alternative to `mboxCreate()` is `adobe.target.getOffer()`/ `adobe.target.applyOffer()` or the Angular directive.

**Example**

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

**Notes**

`mboxCreate()` now uses the "json" endpoint instead of the "standard" endpoint and fires asynchronously. Because of this:

* [Debugging](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/c-target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) is a little different.
* Avoid offer code requiring synchronous, blocking calls.

   For example, offers that set JavaScript variables that are used by site code or other mboxes that come later on the page.
* Be sure to have a `<div class="mboxDefault"></div>`before invoking `mboxCreate()`, because [!DNL at.js] will not add one for you.

* Empty, top-of-page `mboxCreate()` functions are not recommended as a global mbox.

   The auto-created global mbox in [!DNL at.js] is a better option because it fires from the `<head>` and can return content earlier.

## mboxDefine() and mboxUpdate() {#reference_61B2B9F351344CF5B0915D5AFD21C5FE}

Define and update an mbox.

<!-- 

ov2/r_target-atjs-mboxdefine-mboxupdate.

 -->

>[!NOTE]
>
>`mboxDefine()` and `mboxCreate()` are tied to HTML DIV elements where the offer should be displayed. These HTML DIV elements should have the `mboxDefault` class. If the HTML elements won't have this class attached, you could see some noticeable flicker.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Creates an internal mapping between a nodeId and an mbox name, but does not execute the request. Used in conjunction with `mboxUpdate()`. Built into [!DNL at.js]mostly to ease the transition from [!DNL mbox.js]to [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Executes the request and applies the offer to the element identified by the `nodeId` in the `mboxDefine()`. Can also be used to update an mbox initiated by `mboxCreate`. Built into [!DNL at.js] mostly to ease the transition from [!DNL mbox.js] to [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` could be replaced by [ `adobe.target.getOffer()` ](../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_C81525D1598A4A1199740DCAB81A7FDF)and [ `adobe.target.applyOffer()` ](../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#reference_BBE83F513B5B4E03BBC3F50D90864245) using the selector option.

## Example {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```

## targetGlobalSettings() {#concept_8DACBC47ABDE4279BB102B42609FE506}

You can override settings in the `at.js` library using `targetGlobalSettings()`, rather than configuring the settings in the [!DNL Target] Standard/Premium UI or by using REST APIs.

<!-- 

ov2/c_atjs-settings-override.xml

 -->

There are use cases, especially when `at.js` is delivered via [!DNL Dynamic Tag Management] (DTM) when you would like to override some of the settings.

## Settings {#section_42C759AE9B524A43B8659018677224B8}

You can override the following settings:

<table id="table_8819BEE90E8244AEB6EDB3E5C8693FA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Settings </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Default Value </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>clientCode </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Value set via UI </p> </td> 
   <td colname="col4"> <p>Represents client code </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>serverDomain </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Value set via UI </p> </td> 
   <td colname="col4"> <p>Represents Target edge server </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookieDomain </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>If possible set to top level domain </p> </td> 
   <td colname="col4"> <p>Represents the domain used when saving cookies </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>crossDomain </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Value set via UI </p> </td> 
   <td colname="col4"> <p>Indicates whether cross-domain tracking is enabled or not. </p> <p>The allowed values are: </p> <p> 
     <ul id="ul_3D197DC987354C9A80C15FB76654FE61"> 
      <li id="li_7EAAB587A34441ECA337AEB511278684"> <p>disabled </p> </li> 
      <li id="li_FE98D6B22A604D2691222681E3BAEE08"> <p>enabled </p> </li> 
      <li id="li_EA29FC67438646F9B5EFE6288DF2EEBB"> <p>x-only </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timeout </p> </td> 
   <td colname="col2"> <p>Number </p> </td> 
   <td colname="col3"> <p>Value set via UI </p> </td> 
   <td colname="col4"> <p>Represents Target edge request timeout </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>globalMboxAutoCreate </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>Value set via UI </p> </td> 
   <td colname="col4"> <p>Indicates whether the global mbox request should be fired or not </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorApiTimeout </p> </td> 
   <td colname="col2"> <p>Number </p> </td> 
   <td colname="col3"> <p>2000 ms = 2 s </p> </td> 
   <td colname="col4"> <p>Represents the Visitor API request timeout </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>enabled </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>true </p> </td> 
   <td colname="col4"> <p>Indicates whether <span class="codeph"> at.js </span> as library is enabled, meaning if it should execute anything or not. The main use case for this setting being opt-out cookies or other custom decisions that would disable <span class="codeph"> at.js </span> functionality </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>defaultContentHiddenStyle </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>visibility: hidden </p> </td> 
   <td colname="col4"> <p>Used only for wrapping mboxes that use DIV with class name "mboxDefault" and are executed via <span class="codeph"> mboxCreate() </span>, <span class="codeph"> mboxUpdate() </span>, or <span class="codeph"> mboxDefine() </span> to hide default content </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>defaultContentVisibleStyle </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>visibility: visible </p> </td> 
   <td colname="col4"> <p>Used only for wrapping mboxes that use DIV with class name "mboxDefault" and are executed via <span class="codeph"> mboxCreate() </span>, <span class="codeph"> mboxUpdate() </span>, or <span class="codeph"> mboxDefine() </span> to reveal applied offer if any or default content </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bodyHiddenStyle </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>body { opacity: 0 } </p> </td> 
   <td colname="col4"> <p>Used only when <span class="codeph"> globalMboxAutocreate === true </span> to minimize the chance of flicker </p> <p>For more information, see <a href="../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/c-manage-flicker-with-atjs.md#concept_AA168574397D4474B993EEAB90865EBA" format="dita" scope="local"> How at.js Manages Flicker </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bodyHidingEnabled </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>true </p> </td> 
   <td colname="col4"> <p>Used to control flicker when <span class="codeph"> target-global-mbox </span> is used to deliver offers created in the <span class="wintitle"> Visual Experience Composer </span>, also known as visual offers </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>imsOrgId </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>IMS ORG ID </p> </td> 
   <td colname="col4"> <p>Represents the IMS ORG ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>secureOnly </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>false </p> </td> 
   <td colname="col4"> <p>Indicates whether <span class="codeph"> at.js </span> should use HTTPS only or be allowed to switch between HTTP and HTTPS based on the page protocol. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>overrideMboxEdgeServer </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>true (true beginning with at.js version 1.6.2)</p> </td> 
   <td colname="col4"> <p>Indicates if we should use <span class="codeph"> &lt;clientCode>.tt.omtrdc.net </span> domain or <span class="codeph"> mboxedge&lt;clusterNumber>.tt.omtrdc.net </span> domain. If this value is true, <span class="codeph"> mboxedge&lt;clusterNumber>.tt.omtrdc.net </span> domain will be saved to a cookie </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>overrideMboxEdgeServerTimeout </p> </td> 
   <td colname="col2"> <p>Number </p> </td> 
   <td colname="col3"> <p>1860000 => 31 minutes </p> </td> 
   <td colname="col4"> <p>Indicates the cookie lifetime that contains the <span class="codeph"> mboxedge&lt;clusterNumber>.tt.omtrdc.net </span> value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>optoutEnabled </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>false </p> </td> 
   <td colname="col4"> <p>Indicates whether Target should call the Visitor API <span class="codeph"> isOptedOut() </span> function. This is part of Device Graph enablement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>selectorsPollingTimeout </p> </td> 
   <td colname="col2"> <p>Number </p> </td> 
   <td colname="col3"> <p>5000 ms = 5 s </p> </td> 
   <td colname="col4"> <p>In <span class="codeph"> at.js </span> 0.9.6, Target introduced this new setting that can be overridden via <span class="codeph"> targetGlobalSettings </span>, </p> <p> <span class="codeph"> selectorsPollingTimeout </span> represents how long the client is willing to wait for all the elements identified by selectors to appear on the page. </p> <p>Activities created via the Visual Experience Composer (VEC) have offers that contain selectors. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>dataProviders </p> </td> 
   <td colname="col2"> <p>See <a href="../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Data Providers </a> below. </p> </td> 
   <td colname="col3"> <p>See <a href="../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Data Providers </a> below. </p> </td> 
   <td colname="col4"> <p>See <a href="../../c-implementing-target/c-implementing-target-for-client-side-web/cmp-at.js-functions.md#section_42725F3C837247D58AE1831EA330E44D" format="dita" scope="local"> Data Providers </a> below. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Usage {#section_9AD6FA3690364F7480C872CB55567FB0}

This function can be defined before `at.js` is loaded or in **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

The Library Header field allows you to enter free-form JavaScript. The customization code should look something similar to the following example:

```
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## Data Providers {#section_42725F3C837247D58AE1831EA330E44D}

This setting lets customers gather data from third-party data providers, such as Demandbase, BlueKai, and custom services, and pass the data to Target as mbox parameters in the global mbox request. It supports the collection of data from multiple providers via async and sync requests. Using this approach makes it easy to manage flicker of default page content, while including independent timeouts for each provider to limit the impact on page performance

>[!NOTE]
>
>Data Providers requires [!DNL at.js] 1.3 or later.

The following videos contain more information:

<table id="table_5E4FE06C62D54FF994901ABB584BF97C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Video </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html" format="html" scope="external"> Using Data Providers in Adobe Target </a> </p> </td> 
   <td colname="col2"> <p>Data Providers is a capability that allows you to easily pass data from third parties to Target. A third party could be a weather service, a DMP, or even your own web service. You can then use this data to build audiences, target content, and enrich the visitor profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html" format="html" scope="external"> Implement Data Providers in Adobe Target </a> </p> </td> 
   <td colname="col2"> <p>Implementation details and examples of how to use Adobe Target's dataProviders feature to retrieve data from third-party data providers and pass it in the Target request. </p> </td> 
  </tr> 
 </tbody> 
</table>

The `window.targetGlobalSettings.dataProviders` setting is an array of data providers.

Each data provider has the following structure:

<table id="table_7678397D7CCF48758F4A99D8586357C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Name of provider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>version </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Provider version. This key will be used for provider evolution. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timeout </p> </td> 
   <td colname="col2"> <p>Number </p> </td> 
   <td colname="col3"> <p>Represents the provider timeout if this is a network request. </p> <p>This key is optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>provider </p> </td> 
   <td colname="col2"> <p>Function </p> </td> 
   <td colname="col3"> <p>The function that contains the provider data fetching logic. </p> <p>The function has a single required parameter: <span class="codeph"> callback </span>. The callback parameter is a function that should be invoked only when the data has been successfully fetched or there is an error. </p> <p>The callback expects two parameters: </p> <p> 
     <ul id="ul_6A44AA96F3AA4A66A2ABA85A0E5E7944"> 
      <li id="li_64A4153E255E4DF987C298E711849284"> <p>error: Indicates if an error occurred. If everything is OK, then this parameter should be set to null. </p> </li> 
      <li id="li_1C42B122E91C4965A6695D8496B1976E"> <p>params: A JSON object, representing the parameters that will be sent in a Target request. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

The following example shows where the data provider is using sync execution:

```
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

After `at.js` processes `window.targetGlobalSettings.dataProviders`, the Target request will contain a new parameter: `t1=1`.

The following is an example if the parameters that you want to add to the Target request are fetched from a third-party service, such as Bluekai, Demandbase, and so forth:

```
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

After `at.js` processes `window.targetGlobalSettings.dataProviders`, the Target request will contain additional parameters: `t1=1`, `t2=2` and `t3=3`.

The following example uses data providers to collect weather API data and send it as parameters in a Target request. The Target request will have additional params, such as `country` and `weatherCondition`.

```
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

Consider the following when working with the `dataProviders` setting:

* If the data providers added to `window.targetGlobalSettings.dataProviders` are async, they will be executed in parallel. The Visitor API request will be executed in parallel with functions added to `window.targetGlobalSettings.dataProviders` to allow a minimum wait time.
* `at.js` won't try to cache the data. If the data provider fetches data only once, the data provider should make sure that data is cached and, when the provider function is invoked, serve the cache data for the second invocation.

## targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

This method allows you to attach parameters to the global mbox from outside of the request code.

<!-- 

ov2/r_target-atjs-targetpageparams.xml

 -->

This function is very useful for including the same set of parameters on multiple mbox calls. The function needs to be defined by the customer. It should return an array of parameters that will be passed only to the global mbox request. This function can be defined before `at.js` is loaded or in **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

You can pass in parameters to target-global-mbox using the `targetPageParams()` function in any of the following ways:

* An ampersand-delimited list
* An array
* A JSON object

**Examples**

Ampersand-delimited list (values must be URL encoded):

```
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Array (values do not need to be URL encoded):

```
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (values do not need to be URL encoded):

```
targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```

## targetPageParamsAll() {#reference_97E77FCDD793403685ECCA5A44305F93}

This method allows you to attach parameters to all mboxes from outside of the request code.

<!-- 

ov2/r_target-atjs-targetpageparamsall.xml

 -->

This is very useful for including the same set of parameters on multiple mbox calls. The function needs to be defined by the customer. It should return an array of parameters that will be passed to all mbox requests on the page. This function can be defined before `at.js` is loaded or in **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

You can pass in parameters to target-global-mbox using the targetPageParamsAll() function in any of the following ways:

* An ampersand-delimited list
* An array
* A JSON object

**Examples**

Ampersand-delimited list (values must be URL encoded):

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Array (values do not need to be URL encoded):

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (values do not need to be URL encoded):

```
targetPageParamsAll = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```

## registerExtension() {#reference_B3ACC004D45E460C8DD94C1476D2625C}

Provides a standard way to register a specific extension.

<!-- 

ov2/r_target-atjs-registerextension.xml

 -->

The options parameter is mandatory and has the following structure:

<table id="table_46A93D7071DE4A3F84D6E05FFC849EAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Required </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>Extension name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>modules </p> </td> 
   <td colname="col2"> <p>Array[String] </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>An array of strings representing requested module names. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>register </p> </td> 
   <td colname="col2"> <p>Function </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>A function used to initialize and build the extension. This function receives arguments based on modules array. </p> </td> 
  </tr> 
 </tbody> 
</table>

Notes:

* If one of the parameters is not provided, an exception is thrown.
* If the modules array is empty, an exception is thrown.

For more information and examples of how to use `registerExtension`, see the [Adobe Experience Cloud Target atjs Extensions](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions) page on GitHub.

## Settings Module Methods {#section_8501CDD4B0624FA2B10532C98C5F4328}

<table id="table_8A5991797599470C87EBB022783087D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>clientCode </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Client code </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>serverDomain </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Edge server domain </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>globalMboxName </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Target global mbox name </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>globalMboxAutoCreate </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p>Indicates if auto-create is enabled or not </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timeout </p> </td> 
   <td colname="col2"> <p>Number </p> </td> 
   <td colname="col3"> <p>Request timeout </p> </td> 
  </tr> 
 </tbody> 
</table>

## Logger Module Methods {#section_10AF62B49AEF48F981E950D26E176138}

<table id="table_D76DD582EF9A432BB1B5B7F1DD2D853E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>log </p> </td> 
   <td colname="col2"> <p>Function </p> </td> 
   <td colname="col3"> <p>Logs the variable list of arguments to the browser console, if it exists. It is activated only when <span class="codeph"> mboxDebug=true </span> is passed to the URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>error </p> </td> 
   <td colname="col2"> <p>Function </p> </td> 
   <td colname="col3"> <p>Logs the variable list of arguments to the browser console. It is activated only when there are serious errors, such as network timeout, HTML node not found, etc. </p> </td> 
  </tr> 
 </tbody> 
</table>

## at.js custom events {#reference_A828E4BA535F4E7692A075F3D70CF6CD}

Information about `at.js custom events`, which lets you know when an mbox request or offer fails or succeeds.

<!-- 

ov2/r_target-atjs-notification.xml

 -->

Historically, `mbox.js` didn't let other JavaScript code that runs on the page know what happens behind the scenes. With the advancement of `at.js`, we had a unique opportunity to fix this issue.

According to our customers there are several scenarios that they would like to be notified of, including:

* An mbox request failed due to timeout, wrong status code, JSON parse error, etc.
* An mbox request succeeded.
* Offer rendering failed due to wrapping mbox element missing, selector can not be found, etc.
* Offer rendering succeeded. DOM changes have been applied.

Pre-defined events have a structure that allows you to extract the required data, based on event type.

To make sure that events can be used in different scenarios, the custom events have a payload object that is assigned to the detail property of the event object (that is passed to the handler). Also to avoid passing strings as event names, the events are exposed as constants using `adobe.target.event` namespace.

## Structure {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

<table id="table_5B00CCB9BA3C4EE491D6460450823680"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Key </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>type </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>There are several scenarios in which you would like to be notified to help in tracing, debugging, and customizing interaction with at.js. </p> <p> Each custom event listed below has two formats: a "constant" and a "string value." </p> <p> 
     <ul id="ul_E15A7766ACB341C69AADA9E605289BE9"> 
      <li id="li_77813A273E824AC58BF2A379E010675A"> <p><b>Constants: </b>Prepended with <span class="codeph"> adobe.target.event. </span>, presented in all caps, and contain underscore characters. To subscribe to custom events <i>after</i> at.js loads but <i>before</i> the mbox response has been received, use the constant. </p> </li> 
      <li id="li_59A765E14BC4461D8DC3BB16D28C4D9A"><b>String Values:</b> Lowercase and contain dashes. To subscribe to custom events <i>before</i> at.js loads, use the string value. </li> 
     </ul> </p> <p><b>Request Failed</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.REQUEST_FAILED </span> </p> <p>Sting value: <span class="codeph"> at-request-failed </span> </p> <p>Description: An mbox request failed due to timeout, wrong status code, JSON parse error, etc. </p> <p> </p> <p><b>Request Succeeded</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.REQUEST_SUCCEEDED </span> </p> <p>String Value: <span class="codeph"> at-request-succeeded </span> </p> <p>Description: An mbox request was successful. </p> <p> </p> <p><b>Content Rendering Failed</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.CONTENT_RENDERING_FAILED </span> </p> <p>String Value: <span class="codeph"> at-content-rendering-failed </span> </p> <p>Description: Offer rendering failed due to wrapping mbox element missing, selector can not be found, etc. </p> <p><b>Content Rendering Succeeded</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.CONTENT_RENDERING_SUCCEEDED </span> </p> <p>String Value: <span class="codeph"> at-content-rendering-succeeded </span> </p> <p>Description: Offer rendering was successful. DOM changes have been applied. </p> <p><b>Library Loaded</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.LIBRARY_LOADED </span> </p> <p>String Value: <span class="codeph"> at-library-loaded </span> </p> <p>Description: This event is ideal to track when at.js has been fully loaded. You can use this event to customize global mbox execution. You can also use this event to disable the global mbox and then listen for this event to fire the global mbox later. </p> <p><b>Request Start</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.REQUEST_START </span> </p> <p>String Value: <span class="codeph"> at-request-start </span> </p> <p>Description: This event is fired before an HTTP request is executed. You can use this event for performance measurements using the Resource Timing API. </p> <p><b>Content Rendering Start</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.CONTENT_RENDERING_START </span> </p> <p>String Value: <span class="codeph"> at-content-rendering-start </span> </p> <p>Description: This event is fired before selector polling is started and content is rendered to the page. You can use this event to track the content rendering progress. </p> <p><b>Content Rendering No Offers</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.CONTENT_RENDERING_NO_OFFERS </span> </p> <p>String Value: <span class="codeph"> at-content-rendering-no-offers </span> </p> <p>Description: This event is fired when there are no offers returned. </p> <p><b>Content Rendering Redirect</b> </p> <p>Constant: <span class="codeph"> adobe.target.event.CONTENT_RENDERING_REDIRECT </span> </p> <p>String Value: <span class="codeph"> at-content-rendering-redirect </span> </p> <p>Description: This event is fired when an offer is a redirect and Target will redirect to a different URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mbox </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>mbox name </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>message </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Contains human-readable description, such as what happened, the error message, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>tracking </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Contains the <span class="codeph"> sessionId </span> and <span class="codeph"> deviceId </span>. In some cases, <span class="codeph"> deviceId </span> could be missing because <span class="keyword"> Target </span> couldn't retrieve it from edge server. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Usage {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## Training Video {#section_ED304A7137DC42A4BDCD6D57C989F1FA}

Watch the following video to learn how to use Response Tokens and at.js Custom Events to share profile information from Target to third-party systems.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)

