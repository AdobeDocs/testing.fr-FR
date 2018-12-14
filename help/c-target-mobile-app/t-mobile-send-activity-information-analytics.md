---
description: This section describes how to send Target mobile app activity information
  to Adobe Analytics for postAhoc segmentation.
seo-description: This section describes how to send Target mobile app activity information
  to Adobe Analytics for postAhoc segmentation.
seo-title: Send activity information to Adobe Analytics
title: Send activity information to Adobe Analytics
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Send activity information to Adobe Analytics{#send-activity-information-to-adobe-analytics}

This section describes how to send Target mobile app activity information to Adobe Analytics for postAhoc segmentation.

**Prerequisites**

* This integration requires that Analytics and Target are implemented using the mobile SDK.
* Ensure that your report suite is enabled to receive Activity information from Target.

   This is usually done by adding the Target client code to the Analytics report suite. This might be enabled already if you are using the SiteCatalyst-Test&Target integration for web activities. Contact Adobe Client Care if you have any questions about this step.

1. Obtain the activity information.

   If you include a string like the following in your experience content, Target returns the campaign information that you can send to Analytics:

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Replace the text in your experience json code with something like the following example:

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   In this example, a node with the variable ' `tntVal`' is added to obtain the Activity information. Add similar code for the other experiences, with an appropriate title and message.

   This string delivers a number (such as 115110:0:0) in the response from Target. This indicates the Activity ID, experience ID, and traffic Type. The following is a smple response from Target:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Parse the JSON object.

   Parse the response that came back from Target in the callback. You can use NSJSONSerialization to parse this response and store it in a dict or an array.

   Refer to the [NSJSONSerialization documentation](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) for more information.
1. Send the data to Analytics.

   Add the parsed activity information (such as `tntVal` in the above response) to your context data object in an analytics call. This Analytics call containing the context data can be fired immediately or it can wait until the next Analytics call is fired.

   For example, this call can be fired in the callback of the `targetLoadRequest` call:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
>
>`&&tnt`is a reserved event key in the mobile SDK. The post-classification of the `tntVal` variable in Analytics works in the same way in the mobile SDK as it does in on the web (JavaScript). Once the information is processed in Analytics, you should see activity and experience names in the Analytics interface.

