---
description: Auto Allocate identifies a winner among two or more experiences and automatically
  reallocates more traffic to the winner to increase conversions while the test continues
  to run and learn.
keywords: automated traffic allocation;targeting;Increment Count and Keep User in
  Activity;traffic allocation
seo-description: Auto Allocate identifies a winner among two or more experiences and
  automatically reallocates more traffic to the winner to increase conversions while
  the test continues to run and learn.
seo-title: Auto-Allocate
solution: Target
title: Auto-Allocate
topic: Standard
uuid: e8aee4d7-2b99-4e1f-8004-2efc820658b5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Auto-Allocate{#auto-allocate}

Auto Allocate identifies a winner among two or more experiences and automatically reallocates more traffic to the winner to increase conversions while the test continues to run and learn.

>[!IMPORTANT]
>
>Auto-Allocate does not support [!DNL Target for Analytics] (A4T) reporting.

While [creating an A/B activity using the three-step guided workflow](../../c-activities/t-test-ab/t-test-create-ab/t-test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72), you can choose the [!UICONTROL Auto-Allocate to Best Experience] option.

## Training Videos {#section_893E5B36DC4A415C9B1D287F51FCCB83}

**Activity Workflow - Targeting (2:14)**

This video includes information about setting up traffic allocation.

* Assign an audience to your activity
* Throttle traffic up or down
* Select your traffic allocation method
* allocate traffic between different experiences

>[!VIDEO](https://www.youtube.com/watch?v=LOmBgKPeBtA)

**Creating A/B Tests (8:36)**

This video demonstrates how to create an A/B test using the Target three-step guided workflow. Automated traffic allocation is discussed beginning at 4:45.

* Create an A/B activity in Adobe Target
* Allocate traffic using a manual split or automatic traffic allocation

>[!VIDEO](https://www.youtube.com/watch?v=JG0dbWDAvtk)

## The Challenge {#section_85D5A03637204BACA75E19646162ACFF}

Standard A/B tests have an inherent cost. You have to spend traffic to measure performance of each experience and through analysis figure out the winning experience. Traffic distribution remains fixed even after you recognize that some experiences are outperforming others. Also, it's complicated to figure out the sample size, and the activity must run its entire course before you can act on a winner. After doing all of this, there is still a chance the identified winner is not a true winner.

## The Solution: Auto-Allocate {#section_98388996F0584E15BF3A99C57EEB7629}

Auto-Allocate reduces this cost and overhead of determining a winning experience. Auto-Allocate monitors the goal metric performance of all experiences and sends more new entrants to the high-performing experiences proportionately. Enough traffic is reserved to explore the other experiences. You can see the benefits of the test on your results, even while the activity is still running: optimization occurs in parallel with learning.

Auto-Allocate moves visitors toward winning experiences gradually, rather than requiring that you wait until an activity ends to determine a winner. You benefit from lift more quickly because activity entrants who would have been sent to less-successful experiences are shown potential winning experiences.

A normal A/B test in Target shows only pairwise comparisons of challengers with control. For example, if an activity has experiences: A, B, C, and D where A is the control, a normal Target A/B test would compare A versus B, A versus C, and A versus D.

In such tests, most products, including Target, use a Student's t-test to produce p-value-based confidence. This confidence value is then used to determine if the challenger is sufficiently different from the control. However, Target doesn't automatically perform the implicit comparisons (B versus C, B versus D, and C versus D) that are required in order to find the "best" experience. As a result, the marketer must manually analyze the results to determine the "best" experience.

Auto-Allocate performs all implicit comparisons across experiences and produces a "true" winner. There is no notion of a "control" experience in the test.

Auto-Allocate intelligently allocates new visitors to experiences until the confidence interval of the best experience does not overlap with that of any other experience. Normally this process could produce false positives, but Auto-Allocate uses confidence intervals based on the [Bernstein Inequality](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)) that compensates for repeated evaluations. At this point, we have a true winner. When Auto Allocate stops, provided there is no substantial time-dependence to the visitors who arrive at the page, there is at least a 95% chance that auto-allocate will return an experience whose true response is no worse than 1% (relative) less than the true response of the winning experience.

## When to Use Auto-Allocate versus A/B or Automated Personalization {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Use **Auto-Allocate** when you want to optimize your activity from the beginning and identify the winning experiences as quickly as possible. By serving high-performing experiences more often the overall activity performance is increased.
* Use a standard **[A/B test](../../c-activities/t-test-ab/t-test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** when you want to characterize the performance of all experiences before optimizing your site. An A/B test helps you rank all of your experiences, whereas Automated Traffic Allocation finds top performers but does not guarantee differentiation among the lower performers.
* Use [Automated Personalization](../../c-activities/t-automated-personalization/t-automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) when you want optimization algorithms of the highest complexity, such as machine-learning models that build predictions based on individual profile attributes. Automated Traffic Allocation looks at the aggregate behavior of experiences (just like standard A/B tests), and doesn't differentiate between visitors.

## Key Benefits {#section_0913BF06F73C4794862561388BBDDFF0}

* Preserves the strictness of an A/B test
* Finds a statistically significant winner faster than a manual A/B test
* Provides higher average campaign lift than a manual A/B test

## Terminology {#section_670F8785BA894745B43B6D4BFF953188}

The following terms are useful when discussing Auto-Allocate:

* **Multi-armed bandit:** A [multi-armed bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit) approach to optimization balances exploratory learning and exploitation of that learning.

## How the Algorithm Works {#section_ADB69A1C7352462D98849F2918D4FF7B}

The overall logic behind Auto-Allocate incorporates both measured performance (such as conversion rate) and confidence intervals of the cumulative data. Unlike a standard A/B test where traffic is split evenly between experiences, Auto-Allocate changes traffic allocation across experiences.

* 80% of visitors are allocated using the intelligent logic described below.
* 20% of visitors are randomly assigned across all experiences in order to adapt to changing visitor behavior.

The multi-armed bandit approach keeps some experiences free for exploration while exploiting the experiences that are performing well. More new visitors are placed into better performing experiences while preserving the ability to react to changing conditions. These models update at least once an hour to ensure that the model reacts to the latest data.

As more visitors enter the activity, some experiences start to become more successful, and more traffic is sent to the successful experiences. 20% of traffic continues to be served randomly to explore all experiences. If one of the lower-performing experiences starts to perform better, more traffic is allocated to that experience. Or if the success of a higher-performing activity decreases, less traffic is allocated to that experience. For example, if an event causes visitors to look for different information on your media site, or weekend sales on your retail site provide different results.

The following illustration represents how the algorithm might perform during a test with four experiences:

![](assets/auto-allocate.png)

The illustration shows how the traffic allocated to each experience progresses over several rounds of the activity lifetime until a clear winner is determined.

<table id="table_8252CA26599E4A71A8C4F9968F714F65"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Round </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><img href="assets/aa-phase-0.png" id="image_0BDFD174EE434221A3AAC940DE3B7FBA" /> </p> </td> 
   <td colname="col2"> <p><b>Warm-Up Round (0):</b> During the warm-up round, each experience gets equal traffic allocation until each experience in the activity has a minimum of 1,000 visitors and 50 conversions. </p> <p> 
     <ul id="ul_7663360057FA422F993C163FCCDD51E9"> 
      <li id="li_BDBF90D122E5495386A04F518323A2EF">Experience A=25% </li> 
      <li id="li_A2900230E1CC4B558B446FBAD26C7AE5">Experience B=25% </li> 
      <li id="li_A1B55E07ECE740E698A5BC86CECFD004">Experience C=25% </li> 
      <li id="li_F4BB66AA54E1459BA3446E8784DA4001">Experience D=25% </li> 
     </ul> </p> <p>After each experience gets 1,000 visitors and 50 conversions, Target starts automated traffic allocation. All allocations happen in rounds and two experiences are picked for each round. </p> <p>Only two experiences move forward into the next round: D and C. </p> <p>Moving forward means that the two experiences are allocated 80% of the traffic equally, while the other two experiences continue to participate but are only served as part of the 20% random traffic allocation as new visitors enter the activity. </p> <p>All allocations are updated every hour (shown by rounds along the x-axis above). After each round, the cumulative data is compared. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img href="assets/aa-phase-1.png" id="image_B097451B3B9C46BCA38DB2BABA13EFE0" /> </p> </td> 
   <td colname="col2"> <p><b>Round 1:</b> During this round, 80% of traffic is allocated to experiences C and D (40% each). 20% of traffic is allocated randomly to experiences A, B, C, and D (5% each). During this round, experience A performs well. </p> <p> 
     <ul id="ul_AE94BCEC678A4E21A533AABEE5556D2A"> 
      <li id="li_6DD4BC0F6E634F6A9DA9BCFA099F0C6C"> <p>The algorithm picks experience D to move forward into the next round because it has the highest conversion rate (as indicated by <img href="assets/aa-tick.png" id="image_153EA14CE0A54DE9888D144649E9C186" /> on each activity's vertical scale). </p> </li> 
      <li id="li_3E356F97D85D4246B0A0D17C119BFFDE"> <p>The algorithm picks experience A to move forward as well because it has the highest upper bound of the Bernstein 95% confidence interval of the remaining experiences. </p> </li> 
     </ul> </p> <p>Experiences D and A move forward. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img id="image_D7C4C37610304A5A87DC0CB01D78C282" href="assets/aa-phase-2.png" /> </p> </td> 
   <td colname="col2"> <p><b>Round 2:</b> During this round, 80% of traffic is allocated to experiences A and D (40% each). 20% of traffic is allocated randomly, so that means A, B, C, and D each get 5% of traffic. During this round, experience B performs well. </p> <p> 
     <ul id="ul_145A2C322D5C4822AA5CA0510E391F87"> 
      <li id="li_477844A87D174A09869E09192405D4F3"> <p>The algorithm picks experience D to move forward into the next round because it has the highest conversion rate (as indicated by <img href="assets/aa-tick.png" id="image_EE1FA84DAC694E89BA31DC0163E32997" /> on each activity's vertical scale). </p> </li> 
      <li id="li_0E04FF8C08BC45049DFE39D5E4E3E6FE"> <p>The algorithm picks experience B to move forward as well because it has the highest upper bound of the Bernstein 95% confidence interval of the remaining experiences. </p> </li> 
     </ul> </p> <p>Experiences D and B move forward. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img id="image_1B8316E72E834FBFB3106217682460DB" href="assets/aa-phase-3.png" /> </p> </td> 
   <td colname="col2"> <p><b>Round 3:</b> During this round, 80% of traffic is allocated to experiences B and D (40% each). 20% of traffic is allocated randomly, so that means A, B, C, and D each get 5% of traffic. During this round, experience D continues to perform well and experience C performs well. </p> <p> 
     <ul id="ul_DC884A8893724C889C22B2D7AE822D71"> 
      <li id="li_C8BA7BAC5363488E85956D2378BAAA45"> <p>The algorithm picks experience D to move forward into the next round because it has the highest conversion rate (as indicated by <img href="assets/aa-tick.png" id="image_3485B0250A3645A8A9A2AC7E21A6959F" /> on each activity's vertical scale). </p> </li> 
      <li id="li_11CD6CD743AD4FDB858C2B3DD793EC95"> <p>The algorithm picks experience C to move forward as well because it has the highest upper bound of the Bernstein 95% confidence interval of the remaining experiences. </p> </li> 
     </ul> </p> <p>Experiences D and C move forward. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img id="image_FD156B5CFF084B7B9CB3B87D43AA37B1" href="assets/aa-phase-4.png" /> </p> </td> 
   <td colname="col2"> <p><b>Round 4:</b> During this round, 80% of traffic is allocated to experiences C and D (40% each). 20% of traffic is allocated randomly, so that means A, B, C, and D each get 5% of traffic. During this round, experience C performs well. </p> <p> 
     <ul id="ul_55EE78DAA5CB4E48903B322E56095DDC"> 
      <li id="li_53781D3F2FCE42F3A9BF5F4E96905CCC"> <p>The algorithm picks experience C to move forward into the next round because it has the highest conversion rate (as indicated by <img href="assets/aa-tick.png" id="image_7E4B2BBD79CA4BC990EE507118702995" /> on each activity's vertical scale). </p> </li> 
      <li id="li_969FCEBDC1E444CD936F041F750F8781"> <p>The algorithm picks experience D to move forward as well because it has the highest upper bound of the Bernstein 95% confidence interval of the remaining experiences. </p> </li> 
     </ul> </p> <p>Experiences C and D move forward. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img id="image_E34C5278F17945379811E8B9568A4BA7" href="assets/aa-phase-n.png" /> </p> </td> 
   <td colname="col2"> <p><b>Round <i>n</i>:</b> As the activity progresses, a high-performing experience starts to emerge and the process continues until there is a winning experience. When the confidence interval of the experience with the highest conversion rate doesn't overlap with any other experience's confidence interval, it is labeled the winner and a <a href="../../c-activities/automated-traffic-allocation/c-determine-winner.md#concept_5741A89ED7224E1285A3BC34B2CCD0F9" format="dita" scope="local"> badge displays on the activity's page</a> and in the Activity list. </p> <p> 
     <ul id="ul_6F0D50E969E4450595E964C22CDE9635"> 
      <li id="li_96093AC2B40547D7A28483DEF142B195"> <p>The algorithm picks experience C as the clear winner. </p> </li> 
     </ul> </p> <p>At this point the algorithm serves 80% of traffic to experience C, while 20% of traffic continues to be served randomly to all experiences (A, B, C, and D). In total, C gets 85% of traffic. In the unlikely event that the confidence interval of the winner begins to overlap again, the algorithm reverts to the behavior of round 4 above. </p> <p> <p>Important:  If you manually chose a winner earlier in the process, it would have been easy to choose the wrong experience. For this reason, it is best practice to wait until the algorithm determines the winning experience. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

If the activity has only two experiences, both get equal traffic until Target finds an experience with 90% confidence. At that point, 70% of traffic is allocated to the winner and 30% to the loser. After that experience reaches 95% confidence, 100% of traffic is allocated to the winner and 0% to the loser.

After the model for an Auto-Allocate activity is ready (each experience has a minimum of 1,000 visitors and 50 conversions), the following operations from the UI are not allowed:

* Switching the "Traffic Allocation" mode to "Manual"
* Changing the goal metric type
* Changing options in the "Advanced Settings" panel

## Caveats {#section_5C83F89F85C14FD181930AA420435E1D}

* **Auto-Allocate A/B activities are no longer supported in Analytics for Target (A4T)**

   With the 16.10.1.0 release (October 25, 2016), Target does not support Analytics as a reporting source for Auto-Allocate A/B activities going forward. Any active Auto-Allocate A/B activities with A4T enabled will be switched to Manual mode (equal traffic allocation).

* **The Auto-Allocate feature works with only one advanced metric setting: Increment Count and Keep User in Activity**

   The following advanced metric settings are not supported: Increment Count, Release User, Allow Reentry and Increment Count, and Release User and Bar from Reentry.

* **Frequent return visitors can inflate experience conversion-rates.** If a visitor who sees experience A returns frequently and converts several times, the Conversion Rate (CR) of experience A is artificially increased. Compare this to experience B, where visitors convert but do not return often. As a result, the CR of A looks better than the CR of B, so new visitors are more likely to be allocated to A than to B. If you choose to count once per entrant, the CR of A and CR of B might be identical.

   If return visitors are randomly distributed, their effect on conversion rates is more likely to be evened out. To mitigate this effect, consider changing the counting method of the goal metric to count only once per entrant.

* **Differentiates between high-performers, not between low-performers.** Auto-Allocate is good at differentiating between high-performing experiences (and finding a winner). There could be times when you don't have enough differentiation among the under-performing experiences.

   If you want to produce statistically significant differentiation between all experiences, you might want to consider using manual Traffic Allocation mode.

* **Time-correlated (or contextually varying) conversion rates can skew allocation amounts.** Some factors that can be ignored during a standard A/B test because they affect all experiences equally cannot be ignored in an Auto-Allocate test. The algorithm is sensitive to the observed conversion rates. Following are examples of factors that can affect experience performance unequally:

   * Experiences with varying contextual (time, location, gender, etc.) relevance.

      For example:

      * "Thank God it's Friday" results in higher conversions on Friday
      * "Jump-start your Monday" has higher conversion on Monday
      * "Gear up for an East-coast winter" provides higher conversion in East-Coast or winter-afflicted locations
      These can skew the results in an Auto-Allocate test more than in an A/B test because the A/B test analyzes the results over a longer period.

   * Experiences with varying delays in conversion, possibly due to the urgency of the message.

      For example, "30% sale ends today" signals the visitor to convert today, but "50% off first purchase" doesn't create the same sense of urgency.


## Frequently Asked Questions {#section_0E72C1D72DE74F589F965D4B1763E5C3}

**Are returning visitors automatically reallocated to high-performing experiences?**

No. Only new visitors are automatically allocated. Returning visitors continue to see their original experience. This protects the validity of the A/B test.

**How does the algorithm treat false positives?**

The algorithm guarantees a 95% confidence or 5% false-positive rate if you wait until the winner-badge appears.

**When does Auto-Allocate start allocating traffic?**

The algorithm starts working after all experiences in the activity have a minimum of 1,000 visitors and 50 conversions.

**How aggressively does the algorithm exploit?**

80% of traffic is served using Auto-Allocate and 20% of traffic is served randomly. When a winner as been identified, all of the 80% of traffic goes to it, while all experiences continue to get some traffic as part of the 20%, including the winning experience.

**Are losing experiences shown at all?**

Yes. The multi-armed bandit ensures that at least 20% of traffic is reserved to explore changing patterns or conversion rates across all experiences.

**What happens to activities with long conversion delays?**

As long as all experiences being optimized face similar delays, the behavior is the same as an activity with a faster conversion cycle, although it will take longer to reach the 50 conversion threshold before the traffic allocation process begins.

**How is Auto-Allocate different from Automated Personalization?**

Automated Personalization uses each visitor's profile attributes to determine the best experience. In doing so, it not only optimizes, but also personalizes the activity for that user.

Auto-Allocate, on the other hand, is an A/B test that produces an aggregate winner (the most popular experience, but not necessarily the most effective experience for each visitor).

**Do returning visitors inflate conversion rate on my success metric?**

Currently, the logic favors visitors that convert quickly or visit more often. This is because such visitors temporarily inflate the overall conversion rate of the experience they belong to. The algorithm adjusts itself frequently, so the increase in conversion rate is amplified at each snapshot. If the site gets a lot of return visitors, their conversions can potentially inflate the overall conversion rate for the experience they belong to. There is a good chance that return visitors are randomly distributed, in which case the aggregate effect (increased lift) is evened out. To mitigate this effect, consider changing the counting method of the success metric to count only once per entrant.

**Can I use the sample size calculator when using Auto Allocate to estimate how long the activity will take to identify the winner?**

You can use the existing [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html) with Bonferroni correction appropriately applied to get an estimate of how long the test will run. In our experiments, we’ve seen the Auto-Allocate activity end much sooner than this sample size.
