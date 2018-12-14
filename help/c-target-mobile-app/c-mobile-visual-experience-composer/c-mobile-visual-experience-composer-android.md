---
description: Target's new SDK Library allows developers to do a one-time setup on
  their Android mobile apps and enable marketers to use the capabilities of the Mobile
  Visual Experience Composer (VEC).
keywords: mobile vec;mobile visual experience composer;mobile experience composer
  options;setting up;android
seo-description: Target's new SDK Library allows developers to do a one-time setup
  on their Android mobile apps and enable marketers to use the capabilities of the
  Mobile Visual Experience Composer (VEC).
seo-title: Android - set up the mobile app
solution: Target
title: Android - set up the mobile app
topic: Standard
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Android - set up the mobile app{#android-set-up-the-mobile-app}

Target's new SDK Library allows developers to do a one-time setup on their Android mobile apps and enable marketers to use the capabilities of the Mobile Visual Experience Composer (VEC).

>[!NOTE]
>
>The Visual Experience Composer for Native Mobile Apps is currently offered as a Beta feature available to select customers to obtain feedback to help us improve the feature before making it available to all customers. Please talk to your Customer Success Manager or Adobe Client Care to participate in this Beta program.

The Mobile VEC can now be used along with the recently released [!DNL Adobe Experience Cloud SDK]. To do this, customers must use the [!DNL Adobe Launch] integration, the recommended method for using SDKs. For more information, see [Adobe Experience Platform SDKs](https://aep-sdks.gitbook.io/docs).

To set up the Target VEC extension from Launch, see [Use Adobe Launch to set up the Mobile App VEC...](../../c-target-mobile-app/c-mobile-visual-experience-composer/c-use-adobe-launch-to-set-up-the-mobile-app-vec.md#concept_630A05151EF1487193BAE670B59F8CAC).

## Include the Mobile SDK & the Target Library {#section_481F9644C71B4CB7AE3FC526D281D1D2}

1. For information about SDK V5 initialization, see [Initialize the SDK and Set Up Tracking](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk).
1. Add the following line to the dependencies section:

   ```
   implementation 'com.adobe.marketing.mobile:target-vec:0.+'
   ```

1. Add an intent filter in your [!DNL AndroidManifest.XML] file, choosing a unique deep-link scheme for Mobile VEC authoring (for example, `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`):

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
   
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
   
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. Go to your mobile project and insert the following lines at the end of `Application::onCreate override`:

   ```
   public class SDKTest extends MultiDexApplication { 
   
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("launch-EN13b512d3e5f44948b7055c168ec2407c-development"); 
   
           ... 
           try { 
               TargetVEC.registerExtension(); 
               Target.registerExtension(); 
               UserProfile.registerExtension(); 
               Identity.registerExtension(); 
               Lifecycle.registerExtension(); 
               Signal.registerExtension(); 
           } catch (InvalidInitException e) { 
             .. 
           } 
           TargetVEC.registerExtension(this);  // Single line code to initialize TargetVEC 
           MobileCore.start(null); 
       }
   
   /* Rest of Application test goes here ... */
   ```

1. If your build is not working, review the example projects provided below that should build out-of-the-box and review changes in the following locations:

   1. `Application::OnCreate override`
   1. [!DNL AndroidManifest.XML]
   1. `build.gradle` of the Android Application

## Set Up Target Views on Your Mobile App {#section_93AE7797B603465BBFBEC34E5A0A91E3}

The Adobe Mobile SDK exposes a new method for developers to trigger whenever a new View is rendered. As a developer, you must ensure that the views are named uniquely, and the `targetView` call is on the UI main thread. In this section, we will first demonstrate how to properly insert these calls with two different demonstration applications and discuss general guidelines on how to properly insert the Target View API calls for any Android app.

The integration of the Target Views on your mobile app is straight forward. There's only one call to be made:

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

Our first example project is a mock-up of simple bus schedule application. To set up this application for use in the Mobile VEC:

1. In Android Studio, open the project with the [!DNL build.gradle] file in the package subdirectory [!DNL BusBooking].
1. In the `DemoApplication::OnCreate` method, add `TargetVEC.registerExtension()` to register the Target VEC extension, along with other extensions.
1. Build and run the application.
1. To enter the Mobile VEC authoring mode, use the [!DNL sdkbetabus://com.adobe.sdkbetabus] as its URL scheme, and open the generated deep link on the device (see directions below).

From this simple bus-booking application, we use all the automatically generated Target Views associated with the activity life cycle. Furthermore, we demonstrate the flexibility of the API by calling the Target View API on a custom view element that is dynamically added when a hidden button is clicked (the offer image on the screen). This new Target View is implemented by inserting an API call in the code at `OfferDetailsActivity.java:40`. When the hidden button is clicked, a new Target View event called "SURPRISE_VIEW" is fired, allowing the marketer to more precisely target change on the application experience.

Targeted Dynamic View Insertion:

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause(); 
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume(); 
    } 
}
```

Our second example project is a instrumentation of a well-known, open-source and realistic movie application called MovieGuide ( [https://github.com/esoxjem/MovieGuide](https://github.com/esoxjem/MovieGuide)).

To set up this application for use in the Mobile VEC:

1. In Android Studio, open the project with the [!DNL build.gradle] file in the package subdirectory [!DNL MovieGuide].
1. Follow to directions on [https://github.com/AshishKayastha/Movie-Guide](https://github.com/AshishKayastha/Movie-Guide) to get your API key and enable access to its movie database. Modify the [!DNL local.properties] files as per the instructions.
1. In the `BaseApplication::OnCreate` method, add `TargetVEC.registerExtension()` after following [Launch integration steps](../../c-target-mobile-app/c-mobile-visual-experience-composer/c-use-adobe-launch-to-set-up-the-mobile-app-vec.md#concept_630A05151EF1487193BAE670B59F8CAC).
1. Build and run the application.
1. To enter the Mobile VEC authoring mode, use the [!DNL sdkbeta://com.adobe.sdkbeta] as its URL scheme, and open the generated deep link on the device (see directions below).

All activity starts/resumes are already automatically marked as Target Views by the Target Mobile library extension. Moreover, our first example inserts the `TargetView` call into the application open source movie guide application. In our test application, we insert a Target View directly after a movie listing is about to appear ( `com/esoxjem/movieguide/listing/MovieListingFragment.java:90`) for the first time.

Target View Call Insertion:

```
public class MoviesListingFragment extends Fragment implements MoviesListingView { 
    /* ... */ 
   
    @Override 
    public void onViewCreated(View view, Bundle savedInstanceState) { 
        super.onViewCreated(view, savedInstanceState); 
        if (savedInstanceState != null) { 
            movies = savedInstanceState.getParcelableArrayList(Constants.MOVIE); 
            adapter.notifyDataSetChanged(); 
            moviesListing.setVisibility(View.VISIBLE); 
        } else { 
            TargetVEC.targetView("MOVIE_LISTINGS"); 
            moviesPresenter.setView(this); 
        } 
    } 
   
    /* ... */ 
}
```

Our second example inserts the `TargetView` call onto a unique view element, so that we can directly target a screen associated with that view element ( [!DNL com/esoxjem/movieguide/details/MovieDetailsFragment.java:108]). Because this element is used only once in unique layout inflation, the label can be used to represent the layout as a whole and can target the screen for reviews inside of Android Fragment.

Unique View Tagging:

```
public class MovieDetailsFragment extends Fragment implements MovieDetailsView, View.OnClickListener 
   
{ 
   /* ... */ 
    @Override 
    public View onCreateView(LayoutInflater inflater, ViewGroup container, 
                             Bundle savedInstanceState) 
    { 
        View rootView = inflater.inflate(R.layout.fragment_movie_details, container, false); 
        unbinder = ButterKnife.bind(this, rootView); 
        setToolbar(); 
   
        /* Added TargetVEC Code */ 
        View reviewerLabel =  rootView.findViewById(R.id.reviews_label); 
        if(reviewerLabel != null) { 
            reviewerLabel.addOnAttachStateChangeListener(new View.OnAttachStateChangeListener() { 
                @Override 
                public void onViewAttachedToWindow(View v) { 
                    TargetVEC.targetView("REVIEW_LABEL_SHOWN"); 
                } 
   
                @Override 
                public void onViewDetachedFromWindow(View v) { 
   
                } 
            }); 
        } 
   
        return rootView; 
    } 
   
   /* ... */ 
}
```

## Setting Up Profile Parameters and Other Global Parameters {#section_886332781A4847A78640DCD1005E937F}

We now support setting global parameters that will be passed in each and every API call as well as passing mbox/view parameters to corresponding views.

Parameters include:

* mbox/view parameters
* profile parameters
* Product parameters
* Order parameters

Global parameter support:

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 
                new BigDecimal(123.45).setScale(2, BigDecimal.ROUND_UP), 
                Arrays.asList("100", "200"))) 
        .build());
```

Passing parameters for next view trigger:

We have provided some automatic views that are created by default, such as "AUTO_<activity|fragment name>" for each activity and fragment present in your app. If you want to pass these parameters, you can call the following API:

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("view1param", "view1param"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilekeyforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 
                new BigDecimal(123.45).setScale(2, BigDecimal.ROUND_UP), 
                Arrays.asList("100", "200"))) 
        .build());
```

Passing parameters to specific view:

We have seen the API to trigger Views via `TargetVEC.targetView("view_name")`. You can also pass parameters that are specific to the particular view, as shown below:

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## Calling the Prefetch API Explicitly {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

There might be certain scenarios when you might want to call the prefetch API again to refresh the offers stored in cache. The following APIs are exposed, which are described as :

* prefetchOffers

   ```
   /** 
    * Prefetch Target offers. 
    * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
    * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
    * to call this method inside the containing component's onCreate() lifecycle method 
    */ 
   public static void prefetchOffers();
   ```

* prefetchOffersBackground

   ```
   /** 
    * Prefetch Target offers in the background. 
    * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
    * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
    * be applied as Target Views are being triggered. 
    */ 
   public static void prefetchOffersBackground();
   ```

