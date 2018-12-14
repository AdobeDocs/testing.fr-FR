---
description: Target's new SDK Library allows developers to do a one-time setup on
  their iOS mobile apps and enable marketers to use the capabilities of the Mobile
  Visual Experience Composer (VEC).
keywords: mobile vec;mobile visual experience composer;mobile experience composer
  options;setting up;ios;apple
seo-description: Target's new SDK Library allows developers to do a one-time setup
  on their iOS mobile apps and enable marketers to use the capabilities of the Mobile
  Visual Experience Composer (VEC).
seo-title: iOS - set up the mobile app
solution: Target
title: iOS - set up the mobile app
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# iOS - set up the mobile app{#ios-set-up-the-mobile-app}

Target's new SDK Library allows developers to do a one-time setup on their iOS mobile apps and enable marketers to use the capabilities of the Mobile Visual Experience Composer (VEC).

>[!NOTE]
>
>The Visual Experience Composer for Native Mobile Apps is currently offered as a Beta feature available to select customers to obtain feedback to help us improve the feature before making it available to all customers. Please talk to your Customer Success Manager or Adobe Client Care to participate in this Beta program.

The Mobile VEC can now be used along with the recently released Adobe Experience Cloud SDK. To do this, customers must use the Adobe Launch integration, the recommended method for using SDKs. For more information, see [Adobe Experience Platform SDKs](https://aep-sdks.gitbook.io/docs).

To set up the Target VEC extension from Launch, see [Use Adobe Launch to set up the Mobile App VEC...](../../c-target-mobile-app/c-mobile-visual-experience-composer/c-use-adobe-launch-to-set-up-the-mobile-app-vec.md#concept_630A05151EF1487193BAE670B59F8CAC).

## Include the Mobile SDK & the Target Library {#section_FD969A63C4F74603B2F31B82881422A4}

1. Add the library to your project via your Cocoapods [!DNL Podfile] by adding pod 'ACPTargetVEC'.
1. Open your Objective-C application project in XCode.
1. Go to your project build settings and set 'Always Embed swift Standard Libraries' to yes if already not set.
1. For objective-C only project - Create a swift file to create the bridging header. It will set up your application environment for Swift.
1. Add the deeplink handler:

   1. In your application project settings, click **[!UICONTROL Info]**.
   1. Under **[!UICONTROL URL Types]**, click the triangle to open it, then click on the Plus Sign to add a new field.
   1. Add the following information:

      * Identifier: <span class="codeph"> com.adobe.sdktest
      * URL Schemes: <span class="codeph"> vectester
      * Role: <span class="codeph"> Editor
   1. Click away from your application project settings > **[!UICONTROL General]**.
   1. Click back on your application project settings > **[!UICONTROL Info]** to ensure your settings were saved.

      With the example URL type, the URL scheme for your app will be:

      ```
      vectester://com.adobe.sdktest
      ```


1. In XCode, open your [!DNL AppDelegate] file.
1. At the top of the file, add the following line at the end of your imports:

   `#import <ACPTargetVEC_iOS/ACPTargetVEC_iOS.h>`

   If you are using Swift, add the following line:

   `import ACPTargetVEC_iOS`

1. In your [!DNL AppDelegate] file, add the following line to `AppDelegate::application:didFinishLaunchingWithOptions:`. If the delegate function is not defined, create it and add the following line for Objective-C or Swift application, respectively:

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY (Skip any framework which is not applicable for you): 
   [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
   [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
   [ACPLifecycle registerExtension]; 
   [ACPIdentity registerExtension]; 
   [ACPUserProfile registerExtension]; 
   [ACPTarget registerExtension];
   
   [ACPTargetVEC registerExtension]; 
   [ACPTargetVEC allowDebugLogging:YES]; //To see debug logs for target VEC 
   
   [ACPCore start:nil]; 
   [ACPCore lifecycleStart:nil]; 
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
   ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
   ACPLifecycle.registerExtension() 
   ACPIdentity.registerExtension() 
   ACPUserProfile.registerExtension() 
   ACPTarget.registerExtension() 
   
   ACPTargetVEC.registerExtension() 
   ACPTargetVEC.allowDebugLogging(true) //To see debug logs for Target VEC 
   
   ACPCore.start(nil) 
   ACPCore.lifecycleStart(nil)
   ```

   As a example, the method should resemble the following sample:

   ```
      // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
        // Override point for customization after application launch. 
       [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
       [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
       [ACPLifecycle registerExtension]; 
       [ACPIdentity registerExtension]; 
       [ACPUserProfile registerExtension]; 
       [ACPTarget registerExtension]; 
   
       [ACPTargetVEC registerExtension]; 
   
       [ACPCore start:nil]; 
       [ACPCore lifecycleStart:nil]; 
   
      return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) 
   { 
       ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
       ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
       ACPLifecycle.registerExtension() 
       ACPIdentity.registerExtension() 
       ACPUserProfile.registerExtension() 
       ACPTarget.registerExtension() 
   
       ACPTargetVEC.registerExtension() 
   
       ACPCore.start(nil) 
       ACPCore.lifecycleStart(nil)
   
       return true 
   
   }
   ```

1. Add the following line to the beginning of `AppDelegate:application:openURL`. If the delegate function is not defined, create it and add the following line.

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   [ACPTargetVEC handleDeepLink:url];
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   ACPTargetVEC.handleDeepLink(url)
   ```

   As a example, the method should resemble the following sample:

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options { 
       [ACPTargetVEC handleDeepLink:url]; 
       return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func open(_ url: URL, options: [UIApplication.OpenExternalURLOptionsKey : Any] = [:], completionHandler completion: ((Bool) -> Void)? = nil) { 
       ACPTargetVEC.handleDeepLink(url) 
   }
   ```

1. Build and run your application and use it to test Mobile VEC capabilities.

## Set Up Target Views on Your Mobile App {#section_78600DB29862478E8DF2A5EC3CAC1CB0}

In this section, we will first demonstrate how to properly insert these calls with two different demonstration applications and discuss general guidelines on how to properly insert the Target View API calls for any iOS app. In iOS, all the Target Views are defined relative to the `UIViewController` in which they appear. So, unlike Android, the insertion of `TargetViews` are limited to the following calls.

The Adobe Mobile VEC Extension auto-generates names for your `UIViewControllers` to interact within the Mobile VEC framework, based upon the class name of the subclassed `UIViewController`. If you want to override these names, you can call following method in `viewWillAppear` of the `ViewController`.

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

The Adobe Mobile SDK also exposes an alternate method for developers to target custom views during runtime. As a developer, you must ensure that the views are named uniquely. Call following method before adding view to the `superview`:

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## Setting Up Profile Parameters and Other Global Parameters {#section_F87E14F9DF3348698EE006F569EB5B8A}

We now support setting global parameters that will be passed in each and every API call as well as passing mbox/view parameters to corresponding views.

Parameters include:

* mbox/view parameters
* profile parameters
* Product parameters
* Order parameters

Global parameter support:

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
TargetProduct *product = [[TargetProduct alloc] initWithProductId:@"1234" categoryId:@"furniture"]; 
TargetOrder *order = [[TargetOrder alloc] initWithOrderId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
TargetParameters *targetParams = [[TargetParameters alloc] initWithParameters:mboxParams 
                                                            profileParameters:profileParams 
                                                                      product:product 
                                                                        order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : TargetProduct = TargetProduct.init(productId: "1234", categoryId: "furniture") 
var order : TargetOrder = TargetOrder.init(orderId: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : TargetParameters = TargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setGlobalRequest(targetParams)
```

**Passing parameters for next view trigger:**

We have provided some automatic views that are created by default, such as "AUTO_&lt;viewControllerName&gt;" for each view controller present in your app. If you want to pass these parameters, you can call the following API:

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
TargetProduct *product = [[TargetProduct alloc] initWithProductId:@"1234" categoryId:@"furniture"]; 
TargetOrder *order = [[TargetOrder alloc] initWithOrderId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
TargetParameters *targetParams = [[TargetParameters alloc] initWithParameters:mboxParams 
                                                            profileParameters:profileParams 
                                                                      product:product 
                                                                        order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : TargetProduct = TargetProduct.init(productId: "1234", categoryId: "furniture") 
var order : TargetOrder = TargetOrder.init(orderId: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : TargetParameters = TargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setRequest(targetParams)
```

** Passing parameters to specific view:**

We have seen the API to trigger Views via `TargetVEC.targetView("view_name")`.

.You can also pass parameters that are specific to the particular view, as shown below:

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## Calling the Prefetch API Explicitly {#section_373DB4527FC649C58FBA3DF0C18C9836}

There might be certain scenarios when you might want to call the prefetch API again to refresh the offers stored in cache. The following APIs are exposed, which are described as :

** Prefetch Offers:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI 
 */ 
+ (void) prefetchOffers;
```

** Prefetch Offers in background:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI 
 */ 
+ (void) prefetchOffersBackground;
```

