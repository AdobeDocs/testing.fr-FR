---
description: Auto-Target uses advanced machine learning to select from multiple high-performing
  marketer-defined experiences, and serves the most tailored experience to each visitor
  based on his or her individual customer profile and the behavior of previous visitors
  with similar profiles, in order to personalize content and drive conversions.
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble
  shooting
seo-description: Auto-Target uses advanced machine learning to select from multiple
  high-performing marketer-defined experiences, and serves the most tailored experience
  to each visitor based on his or her individual customer profile and the behavior
  of previous visitors with similar profiles, in order to personalize content and
  drive conversions.
seo-title: Auto-Target
solution: Target
title: Auto-Target
title-outputclass: premium
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Auto-Target{#auto-target}

Auto-Target uses advanced machine learning to select from multiple high-performing marketer-defined experiences, and serves the most tailored experience to each visitor based on his or her individual customer profile and the behavior of previous visitors with similar profiles, in order to personalize content and drive conversions.

>[!NOTE]
>
>Auto-Target is available as part of the [!DNL Target Premium] solution. This feature is not available in [!DNL Target Standard] without a [!DNL Target Premium] license.

While [creating an A/B activity using the three-step guided workflow](../c-activities/t-test-ab/t-test-create-ab/t-test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72), you can choose to allocate traffic using the [!UICONTROL Auto-Target For Personalized Experiences] option:

![](assets/auto-target-ui.png)

**Understanding Auto-Target Activities**

This video explains how to set up an Auto-Target A/B activity.

After completing this training, you should be able to:

* Define Auto-Target testing
* Compare and contrast Auto-Target to Automated Personalization
* Create Auto-Target activities

>[!VIDEO](https://www.youtube.com/watch?v=9ki7XJfzcD4)

## Overview {#section_972257739A2648AFA7E7556B693079C9}

The Auto-Target option within the A/B activity flow lets you harness machine-learning to personalize based on a set of marketer-defined experiences in one click. Auto-Target is designed to deliver maximum optimization, compared to traditional A/B testing or Auto Allocate, by determining which experience to display for each visitor. Unlike an A/B activity in which the objective is to find a single winner, Auto-Target automatically determines the best experience for a given visitor (based on his or her profile and other contextual information) to deliver a highly personalized experience.

Similarly to Automated Personalization, Auto-Target uses a Random Forest algorithm, a leading data science ensemble method, to determine the best experience to show to a visitor. Because Auto-Target can adapt to changes in visitor behavior, it can be run perpetually to provide lift. This is sometimes referred to as "always-on" mode.

Unlike an A/B activity in which the experience allocation for a given visitor is sticky, Auto-Target optimizes the specified business goal over each visit. Like in Auto Personalization, Auto-Target, by default, reserves part of the activity's traffic as a control group to measure lift. Visitors in the control group are served a random experience in the activity.

There are a few important notes to keep in mind when using Auto-Target:

* You cannot switch a specific activity from Auto-Target to Automated Personalization, and vice-versa.
* You cannot switch from Manual traffic allocation (traditional A/B Test) to Auto-Target, and vice-versa after an activity is live.
* When using hosts and environments (host groups), models are built for the "Production" environment only. All environments contribute data to build models for "Production" campaigns.
* You must use a minimum of two experiences.

## Terminology {#section_A309B7E0B258467789A5CACDC1D923F3}

The following terms are useful when discussing Auto-Target:

| Term | Definition |
|---|---|
| Multi-armed bandit | A multi-armed bandit approach to optimization balances exploratory learning and exploitation of that learning. |
| Random Forest | Random Forest is a leading machine learning approach. In data-science speak, it is an ensemble classification, or regression method, that works by constructing a large number of decision trees based on visitor and visit attributes. Within Target, Random Forest is used to determine which experience is expected to have the highest likelihood of conversion (or highest revenue per visit) for each specific visitor. For more information about Random Forest in Target, see [Random Forest Algorithm](../c-activities/t-automated-personalization/c-algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
| Thompson Sampling | The goal of Thompson Sampling is to determine which experience is the best overall (non-personalized), while minimizing the “cost” of finding that experience. Thompson sampling always picks a winner, even if there is no statistical difference between two experiences. For more information, see [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling). |

## How Auto-Target Works {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Learn more about the data and algorithms underlying Auto-Target and Automated Personalization at the links below:

<table id="table_EA4B250AA1FE4B699F4E8D8699964F4E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Term </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../c-activities/t-automated-personalization/c-algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA" format="dita" scope="local"> Random Forest Algorithm</a> </p> </td> 
   <td colname="col2"> <p>Target's main personalization algorithm used in both Auto-Target and Automated Personalization is Random Forest. Ensemble methods like Random Forest use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms. The Random Forest algorithm in the automated personalization system is a classification, or regression method, that operates by constructing a multitude of decision trees at training time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="../c-activities/t-automated-personalization/c-uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6" format="dita" scope="local"> Uploading Data For Target's Personalization Algorithms</a> </p> </td> 
   <td colname="col2"> There are several ways to input data for Auto-Target and Automated Personalization models. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="../c-activities/t-automated-personalization/r-ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058" format="dita" scope="local"> Data Collection for Target's Personalization Algorithms</a> </p> </td> 
   <td colname="col2"> <p> Target's personalization algorithms automatically collect a variety of data. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Determining Traffic Allocation {#section_AB3656F71D2D4C67A55A24B38092958F}

Depending on the goal of your activity, you might choose a different traffic allocation between control and personalized experiences. Best practice is to determine this goal before you make your activity live.

The [!UICONTROL Custom Allocation] drop-down list lets you choose from the following options:

* Evaluate Personalization Algorithm
* Maximize Personalization Traffic
* Custom Allocation

![](assets/split.png)

<table id="table_F62EB1E564674B21B6E5CC61C7FB0E6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Activity Goal </th> 
   <th colname="col2" class="entry"> Suggested Traffic Allocation </th> 
   <th colname="col3" class="entry"> Tradeoffs </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Evaluate Personalization Algorithm (50/50)</b> </p> <p> Your goal is to determine how well the personalization algorithm is working compared to the control (i.e. a randomly served experience). You might be in the beginning stages of evaluating your personalization program. </p> </td> 
   <td colname="col2"> <p>50% Control / 50% Personalized Experience split </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_2046B7E159324EA4B8FDA06E84D1470C"> 
      <li id="li_84F829B900B64587B653F307249273EE"> <p>Maximizes accuracy of lift between control and personalized </p> </li> 
      <li id="li_D1F670650D0747FD8A57652B211287B6"> <p>Relatively fewer visitors will have a personalized experience </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Maximize Personalization Traffic (90/10)</b> </p> <p> Your goal is to create an "always on" personalization activity that maximizes the amount of traffic that is personalized. You want to maximize the lift while continuing to have a Control benchmark lift to compare against. </p> </td> 
   <td colname="col2"> <p>Best practice is to use a 10% - 30% Control / 70% - 90% Personalized Experience split </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_9FF58BE03F4A416BA93FF4F3948D000C"> 
      <li id="li_573083D165D64C43878C4EFD2020D2BE"> <p>Maximizes number of visitors who have a personalized experience </p> </li> 
      <li id="li_1B8C27AD5B5B43C6B4B9D7F1EBF58ADE"> <p>Maximizes lift </p> </li> 
      <li id="li_D6FAD005AB3A40D78166F4D0AD872911"> <p> Less accuracy as to what the lift is for the activity </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Custom Allocation</b> </p> </td> 
   <td colname="col2"> <p>Manually split the percentage as desired. </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_E538A7699C5D425EA2CB9D12D1B794E1"> 
      <li id="li_FC100FA78CAB4F9490C518B5A19B8133"> <p>You might not achieve the desired results. If you are unsure, follow the suggestions for either of the preceding options </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

To adjust the Control percentage, click the - or + symbols. You cannot decrease the control group to less than 10%.

![](assets/auto-target-control-bigl.png)

## When should you choose Auto-Target over Automated Personalization? {#section_BBC4871C87944DD7A8B925811A30C633}

There are several scenarios where you might prefer to use Auto-Target over Automated Personalization:

* If you want to define the entire experience rather than individual offers that will be automatically combined to form an experience.
* If you want to leverage the full set of Visual Experience Composer (VEC) features not supported by Auto Personalization: the custom code editor, multiple experience audiences, and more.
* If you want to make structural changes to your page in different experiences. For example, if you wanted to rearrange the order of elements on your home page, Auto-Target would be more appropriate to use than Automated Personalization.

## What does Auto-Target Have in Common with Automated Personalization? {#section_2A601F482F9A44E38D4B694668711319}

**The algorithm optimizes for a favorable outcome for each visit.**

* The algorithm predicts a visitor's propensity for conversion (or estimated revenue from conversion) in order to serve the best experience.
* A visitor is eligible for a new experience upon the end of an existing session (unless the visitor is in the control group, in which case the experience that visitor is assigned on his or her first visit remains the same for subsequent visits).
* Within a session, the prediction doesn’t change, to maintain visual consistency.

**The algorithm adapts to changes in visitor behavior.**

* The multi-arm bandit ensures the model is always "spending" a small fraction traffic to continue to learn throughout the life of the activity learning and to prevent over-exploitation of previously learned trends.
* The underlying models are rebuilt every 24 hours using the latest visitor behavior data to ensure Target is always exploiting changing visitor preferences.
* If the algorithm can't determine winning experiences for individuals, it automatically switches to showing the overall best-performing experience while still continuing to look for personalized winners. The best-performing experience is found using [Thompson sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

**The algorithm continually optimizes for a single goal metric.**

* This metric could be conversion-based or revenue-based (more specifically Revenue per Visit).

**The algorithm does not support using [!DNL Analytics] as a data-source or a reporting endpoint.**

**Target automatically collects information about visitors to build the personalization models.**

* For more information about the parameters used in Auto-Target and Automated Personalization, see [Automated Personalization Data Collection](../c-activities/t-automated-personalization/r-ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**Target automatically uses all Experience Cloud shared audiences to build the personalization models.**

* You don't have to do anything specific to add audiences to the model. For information about using Experience Cloud Audiences with Target, see [Experience Cloud Audiences](../c-integrating-target-with-mac/c-mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

**Marketers can upload offline data, propensity scores, or other custom data to build personalization models.**

* Learn more about [uploading data for Auto-Target and Automated Personalization](../c-activities/t-automated-personalization/c-uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

## How Does Auto-Target differ from Automated Personalization? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**Auto-Target frequently requires less traffic than Automated Personalization for a personalized model to build.**

Although the amount of traffic *per experience* required for Auto-Target or Auto Personalization models to build are the same, there are usually more experiences in an Automated Personalization activity than an Auto-Target activity. For example, if you had an Auto Personalization activity where you've created two offers per location with two locations, there would be four (2 = 4) total experiences included in the activity (with no exclusions). Using Auto-Target, you could set experience 1 to include offer 1 in location 1 and offer 2 in location 2, and experience 2 to include offer 1 in location 1 and offer 2 in location 2. Because Auto-Target allows you could choose to have multiple changes within one experience, you can reduce the number of total experiences in your activity.

For Auto-Target, simple rules of thumb can be used to understand traffic requirements:

* **When Conversion is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 7,000 visits and 350 conversions.
* **When Revenue per Visit is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 1,000 conversions per experience. RPV usually requires more data to build models due to the higher data variance that typically exists in visit revenue compared to conversion rate.

**Auto-Target has full-fledged setup functionality.**

* Because Auto-Target is embedded in the A/B activity workflow, Auto-Target benefits from the more mature and full-fledged Visual Experience Composer (VEC). You can also leverage [QA links](../c-activities/c-activity-qa/c-activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) with Auto-Target.

**Auto-Target provides an extensive online testing framework.**

* The multi-arm bandit is part of a larger online-testing framework that allows our data-scientists and researchers to understand the benefits of their continual improvements in real-world conditions.
* In the future, this test bed will allow us to open our machine learning platform to our data-savvy clients so that they can bring in their own models to augment Target's models.

## Reporting and Auto-Target {#section_42EE7F5E65E84F89A872FE9921917F76}

For more information, see [Auto-Target Summary Report](../c-reports/c-auto-target-summary-report.md#concept_E2171F7B57C1417DAAD7E7909A3FB073) in the [Reports](../c-reports/c-reports.md#concept_B5077F5503AA4C98901AA99EDCE6CDE6) section.

## Auto-Target Frequently Asked Questions {#section_5C120A2B11D14D9BAF767BBAB50FED23}

<table id="table_2E4DF5F6B8B34199914F99B088CB07DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> FAQ </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>What are best practices to set up an Auto-Target activity? </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_35952295EFD0407690D79C17814B957E"> 
      <li id="li_A8BF85B281DA406B976B96A219886316"> <p>Decide if the business value of a Revenue per Visit (RPV) success metric is worth the additional traffic requirements. RPV typically needs at least 1,000 conversions per experience for an activity to work versus conversion. </p> </li> 
      <li id="li_222A8A0D8D334A70AE736DB04558E4E1"> <p>Decide on the allocation between control and personalized experiences before beginning the activity based on your goals. </p> </li> 
      <li id="li_7E6092C1FF38409ABBF37703C8EEEC3A"> <p>Determine if you have sufficient traffic to the page where your Auto-Target activity will run for personalization models to build in a reasonable amount of time. </p> 
       <ul id="ul_B9CDA865042D4D0B8D5B351B9825FB61"> 
        <li id="li_911F665DCCAE4D2DB03691AE90E2B9E3"> <p>If you are testing the personalization algorithm, you shouldn’t change experiences or add/remove profile attributes while the activity is live. </p> </li> 
       </ul> </li> 
      <li id="li_BB165041CB0D425E96FF47E2F65E7458"> <p>Consider completing an A/B activity between the offers and locations you are planning to use in your Auto-Target activity to ensure the location(s) and offers have an impact on the optimization goal. If an A/B activity fails to demonstrate a significant difference, Auto-Target likely will also fail to generate lift. </p> 
       <ul id="ul_A5DC915A14014CA1BE4E128CAC44575C"> 
        <li id="li_E165121CC60B45568C7523A16CD3D354"> <p>If an A/B test shows no statistically significant differences between experiences, it is likely the offers you are considering are not sufficiently different from each other, the locations you selected do not impact the success metric, or the optimization goal is too far in the conversion funnel to be affected by your chosen offers. </p> </li> 
       </ul> </li> 
      <li id="li_91BED93C6773407A86FBDA4E3EEB9478"> <p>Try not to make substantial changes to the experiences during the course of the activity. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Do the check marks indicating a model is built for that experience update if the report date range changes? </p> </td> 
   <td colname="col2"> <p> No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>If a visitor does NOT see the Auto-Target activity and converts, does the conversion count in my activity? </p> </td> 
   <td colname="col2"> <p>No, only visitors who qualify for and view the Auto-Target activity are counted in reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>My Auto-Target activity doesn’t seem to be generating any lift. What is going on? </p> </td> 
   <td colname="col2"> <p>There are four factors required for an Auto-Target activity to generate lift: </p> <p> 
     <ul id="ul_A71BBCCEE6944F0687C22DFE96344C73"> 
      <li id="li_B2D5438B6C174CDAA48D2E29ACA4396C"> <p>The offers need to be different enough to influence visitors. </p> </li> 
      <li id="li_4326600EBB9C4BFFB3BDD6F2CAE7D9E2"> <p>The offers need to be located somewhere that makes a difference to the optimization goal. </p> </li> 
      <li id="li_D18CB1E92F9E4D03ACD030AD7B2DF5D2"> <p>There must be enough traffic and statistical “power” in the test to detect the lift. </p> </li> 
      <li id="li_2B3CF564497A43FF8C52CAC1FEA2306A"> <p>The personalization algorithm must work well. </p> </li> 
     </ul> </p> <p>The best course of action is to first make sure the content and locations that make up the activity experiences truly make a difference to the overall response rates using a simple, non-personalized A/B test. Be sure to compute the sample sizes ahead of time to ensure there is enough power to see a reasonable lift and run the A/B test for a fixed duration without stopping it or making any changes. </p> <p>If an A/B test's results show statistically significant lift on one or more of the experiences, then it is likely that a personalized activity will work. Of course, personalization can work even if there are no differences in the overall response rates of the experiences. Typically, the issue stems from the offers/locations not having a large enough impact on the optimization goal to be detected with statistical significance. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>When should I stop my Auto-Target activity? </p> </td> 
   <td colname="col2"> <p>Auto-Target can be used as “always on” personalization that will constantly optimize. Especially for evergreen content, there is no need to stop your Auto-Target activity. </p> <p>If you want to make substantial changes to the content in your Auto-Target activity, the best practice is to start a new activity so that other users reviewing reports will not confuse or relate past results with different content. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>How long should I wait for models to build? </p> </td> 
   <td colname="col2"> <p>The length of time it takes for models to build in your Auto-Target activity typically depends on the traffic to your selected activity location(s) and your activity success metric. </p> <p>For Auto-Target, simple rules of thumb can be used to understand traffic requirements: </p> <p> 
     <ul id="ul_5231F86C8A17445FBB690025F16E3BF7"> 
      <li id="li_907F477BFBBF45C5A01D8CFD9F875DF4"> <p><b>When Conversion is your success metric:</b> 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 7,000 visits and 350 conversions. </p> </li> 
      <li id="li_3DFB406BB92B4E69B697E75AB4023D09"> <p><b>When Revenue per Visit is your success metric:</b> 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 1,000 conversions per experience. RPV usually requires more data to build models due to the higher data variance that typically exists in visit revenue compared to conversion rate. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>One model is built in my activity. Are the visits to that experience personalized? </p> </td> 
   <td colname="col2"> <p>No, there must be at least two models built within your activity for personalization to begin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>When can I start to look at the results of my Auto-Target activity? </p> </td> 
   <td colname="col2"> <p>You can begin to look at the results of your Auto-Target test after you have at least two experiences with models built (green checkmark) for the experience that have models built. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Troubleshooting Auto-Target {#section_23995AB813F24525AF294D20A20875C8}

Sometimes activities don't go as expected. Here are some potential challenges you may face while using Auto-Target, and some suggested solutions.

<table id="table_519FC87F482A42A78AC7A3399F7569B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Issue </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> My Auto-Target activity is taking too long to build models. </p> </td> 
   <td colname="col2"> <p>There are several activity setup changes that can decrease the expected time to build models, including the number of experiences in your Auto-Target activity, the traffic to your site, and your selected success metric. </p> <p> <b>Solution:</b> Review your activity setup and see if there are any changes you are willing to make to improve the speed at which models will build. </p> <p> 
     <ul id="ul_2B7F7D460B9E447E92F702A2FFF6DCAF"> 
      <li id="li_AC87EEE8B74843179D1FAFE787C13254"> <p>If your success metric is set to RPV, can you change to conversion? Conversion activities tend to require less traffic to build models. You will not lose activity data if you change the success metric from RPV to conversion. </p> </li> 
      <li id="li_D6D6C7AB29D2474997250206D210FAF7"> <p>Is your success metric far down the sales funnel from your activity experiences? A lower activity conversion rate will increase the traffic requirements needed for models to build, as a minimum number of conversions is required. </p> </li> 
      <li id="li_805DC6329EED47ABAF3D9682F769A652"> <p>Are there some experiences you can drop from your activity? Decreasing the number of experiences in an activity will lessen the amount of time to build models. </p> </li> 
      <li id="li_797DA9BE80DB4A3F8E105C0B054E0C91"> <p>Is there a higher-traffic page on which this activity would be more successful? The more traffic and conversions in your activity locations, the quicker models will build. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> My Auto-Target activity isn't generating any lift. </p> </td> 
   <td colname="col2"> <p>There are four factors required for an AP activity to generate lift: </p> <p> 
     <ul id="ul_803A91F52887461B98EACA7B781C7CFA"> 
      <li id="li_4D13CA9BCADD4926903AFB46D8FE013F"> <p>The offers need to be different enough to influence visitors. </p> </li> 
      <li id="li_3B68565312C54F8E9DEE25D99F7F1C32"> <p>The offers need to be located somewhere that makes a difference to the optimization goal. </p> </li> 
      <li id="li_E46C0B2812CE48D0A8437021CB5C454A"> <p>There must be enough traffic and statistical “power” in the test to detect the lift. </p> </li> 
      <li id="li_B7BC241A7AD14A949D6F21E45279C9AB"> <p>The personalization algorithm must work well. </p> </li> 
     </ul> </p> <p><b>Solution:</b> First, make sure that your activity is personalizing traffic. If models aren't built for all of the experiences, your Auto-Target activity is still randomly serving a significant portion of visits to attempt to build all models as quickly as possible. If models aren't built, Auto-Target is not personalizing traffic. </p> <p> Next, make sure the offers and the activity locations truly make a difference to the overall response rates using a simple, non-personalized A/B test. Be sure to compute the sample sizes ahead of time to ensure there is enough power to see a reasonable lift and run the A/B test for a fixed duration without stopping it or making any changes. If an A/B test results show statistically significant lift on one or more of the experiences, then it is likely that a personalized activity will work. Of course, personalization can work even if there are no differences in the overall response rates of the experiences. Typically, the issue stems from the offers/locations not having a large enough impact on the optimization goal to be detected with statistical significance. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Any metric dependent on conversion metric never converts. </p> </td> 
   <td colname="col2"> <p>This is expected. </p> <p>In an Auto-Target activity, once a conversion metric (whether optimization goal or post goal) is converted, the user is released from the experience and the activity is restarted. </p> <p> For example, there is an activity with a conversion metric (C1) and an additional metric (A1). A1 is dependent on C1. When a visitor enters the activity for the first time, and the criteria for converting A1 and C1 are not converted, metric A1 is not converted due to the success metric dependency. If the visitor converts C1 and then converts A1, A1 is still not converted because as soon as C1 is converted, the visitor is released. </p> </td> 
  </tr> 
 </tbody> 
</table>

