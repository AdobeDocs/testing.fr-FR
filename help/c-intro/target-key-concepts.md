---
description: Information about key concepts that will help you understand the features
  and capabilities of Adobe Target.
keywords: Overview and Reference;act
seo-description: Information about key concepts that will help you understand the
  features and capabilities of Adobe Target.
seo-title: Target key concepts
solution: Target
subtopic: Getting Started
title: Target key concepts
topic: Standard
uuid: c62ac156-b4cf-494c-979f-33f889abd118
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Target key concepts{#target-key-concepts}

Information about key concepts that will help you understand the features and capabilities of Adobe Target.

## Target key concepts {#topic_547A22434AA047FAB514D7DA9112A48D}

Information about key concepts that will help you understand the features and capabilities of Adobe Target.

## Activities and Tests {#section_BEA0A0C51A8847579B566060206DE7E8}

An activity determines the experiences a site visitor might encounter.

For example, you might design an activity that tests two different landing pages, one that highlights information about women's summer shoes, and one that highlights more general summer apparel. The activity determines the conditions that control when each of these landing pages appears, and the metrics that determine which page is more successful. The activity is configured to start and end when specific conditions are met, such as between specific dates, or to start when the activity is approved and to end when it is deactivated.

When designing an activity, you should plan carefully. Determine when the activity will start and how long it will last. Then, list your offers and assign a target audience to each one.

**Activity Types (9:03)**

This video explains the activity types available in [!DNL Target Standard/Premium].

* Describe the types of activities included in [!DNL Adobe Target]
* Select the appropriate activity type to achieve your goals
* Describe the three-step guided workflow that applies to all activity types

>[!VIDEO](https://www.youtube.com/watch?v=vtHg1pPFJp8)

There are several types of activities:

<table id="table_B1D68605447642F29CC02157582B921B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Activity Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> <a href="../c-activities/t-test-ab/t-test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977" format="dita" scope="local"> A/B Test</a> </p> </td> 
   <td colname="col2"> <p class="- topic/p ">A/B Testing compares two or more versions of your Web site content to see which version best improves your conversions during a pre-specified test period. </p> <p>The following are two types of A/B tests you can use: </p> 
    <ul id="ul_1A94061695D74ABEADE7C579B1349F09"> 
     <li id="li_97B7AB009C86403AA6ABEECE03B15659"> <p><a href="../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4" format="dita" scope="local"> Auto-Allocate</a> </p> <p>Auto Allocate identifies a winner among two or more experiences and automatically reallocates more traffic to the winner to increase conversions while the test continues to run and learn. </p> </li> 
     <li id="li_69D72AECB5524DC0B2C80AE332B5A178"> <p><a href="../c-activities/c-auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3" format="dita" scope="local"> Auto-Target</a> </p> <p>Auto Target uses advanced machine learning to identify multiple high performing marketer-defined experiences, and serves the most tailored experience to each visitor based on their individual customer profile and the behavior of previous visitors with similar profiles, in order to personalize content and drive conversions. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../c-activities/t-test-ab/t-test-create-ab/t-create-a4t.md#task_FE48F7B077C44A5BA015B087428412EF" format="dita" scope="local"> Using Analytics Data</a> </p> </td> 
   <td colname="col2"> <p>You can configure an activity to use <span class="keyword"> Adobe Analytics</span> as the reporting source. This activity type requires that you link your <span class="keyword"> Adobe Experience Cloud</span> account with both <span class="keyword"> Analytics</span> and <span class="keyword"> Target</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> <a href="../c-activities/c-multivariate-testing/c-multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499" format="dita" scope="local"> Multivariate Test</a> </p> </td> 
   <td colname="col2"> <p class="- topic/p ">Multivariate Testing (MVT) compares combinations of offers in elements on a page to determine which combination performs the best for a specific audience, and identifies which element most impacts the activity's success. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p class="- topic/p "> <a href="../c-activities/t-experience-target/t-experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4" format="dita" scope="local"> Experience Targeting</a> </p> </td> 
   <td colname="col2"> <p class="- topic/p ">Experience Targeting (XT) delivers content to a specific audience based on a set of marketer-defined rules and criteria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" class="premium"> <p> <a href="../c-activities/t-automated-personalization/t-automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9" format="dita" scope="local"> Automated Personalization</a> </p> </td> 
   <td colname="col2"> <p>Automated Personalization (AP) combines offers or messages, and uses advanced machine learning to match different variations to each visitor based on their individual customer profile, in order to personalize content and drive conversions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" class="premium"> <p> <a href="../c-recommendations/c-recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0" format="dita" scope="local"> Recommendations</a> </p> </td> 
   <td colname="col2"> <p>A recommendation determines how a product is suggested to a website user, depending on that user's activities on the site. </p> <p>For example, you might want to encourage people who purchase a backpack to consider buying hiking shoes and trekking poles. You could create a recommendation that shows items that are often purchased together, using the "People who bought this also bought that" algorithm. Or, you might want to encourage visitors to spend more time on your media site by recommending similar video to the one they are watching, using the "People who viewed this viewed that" algorithm. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Locations {#section_F18FBF1ED23340ED9F39C51971A4E874}

Primarily, a location is a page on your website. It could also refer to a place in a mobile app, an email, or any other place where you run an optimization.

Locations are essential to activities and experiences. You decide whether any location can do one, both, or none of the following:

* Display and swap content for visitors.
* Log visitor behavior.

In [!DNL Target Standard], a location can be any element on a page, as long as the page contains a single line of code that enables [!DNL Target] in the `<head>` section of each page you want to track. This line of code calls the JavaScript libraries needed to collect information and deliver targeted experiences to your visitors.

See [Understanding the Target JavaScript Libraries](../c-implementing-target/c-considerations-before-you-implement-target/c-target-implement.md#concept_60B748DE4293488F917E8F1FA4C7E9EB) for more information about the differences between location implementation in [!DNL Target Standard] and the mbox implementation in [!DNL Target Classic].

Locations are combined with audiences to provide an almost endless number of options for targeting information to your customers. For example, if a visitor has never been to the site before, you might display a discount coupon for new customers. Likewise, the page might be changed to display offers that are more optimized to returning customers.

You can also use locations to track a visitor's progress through your Web site, or to track whether the visitor completes a specific success metric, such as adding an item to the shopping cart or completing a purchase.

## Experiences and Page Designs {#section_B806FB752EC1470784755C1EB3D4AC70}

An experience, sometimes called a recipe, defines the content that displays on your page, as well as other page elements, such as links.

An experience determines which offer displays in a certain location when specific targeting conditions are met. For example, the experience determines that, when a return visitor visits your site, an offer for two-day shipping displays at the top of the page. The experience also determines that, when a first-time visitor views the page, a 10% discount appears in the same location.

An experience consists of the offers, image assets, or other HTML elements (such as links) that appear on the page to help drive the visitor toward the result you desire. [!DNL Target] combines locations, offers, and experiences to determine which content displays on your site during a specific test.

An experience can also be a different page design. For example, one experience might have one set of links across the top of the page, where another experience has different links or the same links arranged in a different order. You might want to test whether one image provides more lift than another, or whether an ad is more likely to be clicked near the top of your page or in a different location.

[!DNL Target] optimizes experiences for each of your visitors across your digital touchpoints and to test different experiences to determine which will be most successful. By carefully planned targeting of experiences, you can make sure that your site visitors see the most relevant offers in the right locations on your page, improving your chances of a successful visit.

## Offers {#section_973D4CC4CEB44711BBB9A21BF74B89E9}

An offer is the content displayed on your webpages during campaigns or activities.

When you test your webpages, you measure the success of each experience with different offers in your locations.

An offer can contain different types of content, including:

* Image
* Text
* HTML
* Link
* Button

For example, a webpage might display either of two offers, depending on whether the visitor has been to your site before.

An *experience* determines which content displays when particular conditions are met.

## Audiences {#section_3F32DA46BDF947878DD79DBB97040D01}

Optimize your targeted content to activity entrants who meet specific criteria.

Audiences define the target for your activity and are used anywhere where targeting is available.

**Using Audiences in Adobe Target (6:21)**

This video explains how to use audiences in [!DNL Target Standard/Premium].

* Explain the term "Audience"
* Explain the two ways audiences are used for optimization
* Find audiences in the Audiences list
* Target an activity to an audience
* Use audiences for passive reporting in an activity

>[!VIDEO](https://www.youtube.com/watch?v=TAMBpW9vpOI)

[!DNL Target] audiences are a defined set of visitor criteria. Offers can be targeted to specific audiences (or segments). Only visitors who belong to that audience see the experience that is targeted to them.

For example, you might target an activity to an audience made up of visitors who use a particular browser or operating system.

Or, your activity might be targeted at visitors from one geographical region, or people who access your page from a certain search engine.

Audiences can be saved for reuse in multiple activities, or they can be created for a specific campaign.

<table id="table_8293411EA6844B0488254DDE98864C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Audience Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Reusable audiences </p> </td> 
   <td colname="col2"> <p>Reusable audiences can be selected for any test. Changing one of these audiences changes it for all activities that use it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom segments </p> </td> 
   <td colname="col2"> <p>Custom segments (also known as <i>campaign-specific</i> segments) are specific to a campaign in <span class="keyword"> Target Classic</span>. They are created as a part of the campaign and cannot be reused in other campaigns. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Shared audiences </p> </td> 
   <td colname="col2"> <p>Audiences can be shared across <span class="keyword"> Adobe Experience Cloud solutions</span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html" format="https" scope="external"> Experience Cloud Audiences</a> for examples. </p> </td> 
  </tr> 
 </tbody> 
</table>

For information about how the visitor profile tracks information about visitors to your site, see [Visitor Profiles](../c-target/c-visitor-profile/c-visitor-profile.md#concept_5E53D1A6DF224D7BAE76F4AE390B9DA1).
