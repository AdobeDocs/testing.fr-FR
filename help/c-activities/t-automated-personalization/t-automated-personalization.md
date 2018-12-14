---
description: Automated Personalization (AP) combines offers or messages, and uses
  advanced machine learning to match different offer variations to each visitor based
  on their individual customer profile, in order to personalize content and drive
  lift.
keywords: automated personalization;Audiences;ensemble;random forest
seo-description: Automated Personalization (AP) combines offers or messages, and uses
  advanced machine learning to match different offer variations to each visitor based
  on their individual customer profile, in order to personalize content and drive
  lift.
seo-title: Automated Personalization
solution: Target
title: Automated Personalization
title-outputclass: premium
topic: Advanced
uuid: cf9489f2-45b2-4028-8956-36d0afe0ee0a
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Automated Personalization{#automated-personalization}

Automated Personalization (AP) combines offers or messages, and uses advanced machine learning to match different offer variations to each visitor based on their individual customer profile, in order to personalize content and drive lift.

Similarly to Auto-Target, Automated Personalization uses a Random Forest algorithm, a leading data science ensemble method, as its main personalization algorithm to determine the best experience to show a visitor. Automated Personalization can be valuable in the discovery phase of testing. It is also useful to allow machine learning to determine the most effective content when targeting diverse visitors. Over time, the algorithm learns to predict the most effective content and displays the content most likely to achieve your goals.

To find more information about how Automated Personalization differs from Auto Target, see [Auto-Target For Personalized Experiences](../../c-activities/c-auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

>[!NOTE]
>
>Automated Personalization is available as part of the Target Premium solution. It is not included with Target Standard without a Target Premium license. If you have a Target Premium license, the Target Premium card replaces the Target Standard card in the Adobe Experience Cloud.

**Activity Types (9:03)**

This video explains the activity types available in Target Standard/Premium. Automated Personalization is discussed beginning at 5:55.

* Describe the types of activities included in [!DNL Adobe Target]
* Select the appropriate activity type to achieve your goals
* Describe the three-step guided workflow that applies to all activity types

>[!VIDEO](https://www.youtube.com/watch?v=vtHg1pPFJp8)

Marketers implement one file on their site which enables them to point and click on any content and then visually create and select additional content options for that area using the VEC (Visual Experience Composer). Then, the algorithm automatically determines which piece of content to deliver to each individual visitor based on all the behavioral data that the system has about that visitor, providing a personalized experience. Because Automated Personalization can adapt to changes in visitor behavior, it can be run without a set end date to provide ongoing lift and personalization. This is sometimes referred to as “always-on” mode. The marketer does not need to run a test, analyze the results, then deliver a winner before realizing the lift found from optimization—a standard order of operations to implement the outcome of a standard A/B activity.

The following terms are useful when discussing Automated Personalization:

| Term | Definition |
|---|---|
| Multi-armed bandit | A multi-armed bandit approach to optimization balances exploratory learning and exploitation of that learning. |
| Random Forest | Random Forest is a leading machine learning approach. In data-science speak, it is an ensemble classification or regression method that works by constructing a large number of decision trees based on visitor and visit attributes. Within Target, Random Forest is used to determine which experience is expected to have the highest likelihood of conversion (or highest revenue per visit) for each specific visitor. For more information about Random Forest in Target, see [Random Forest Algorithm](../../c-activities/t-automated-personalization/c-algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
| Thompson Sampling | The goal of Thompson Sampling is to determine which experience is the best overall (non-personalized), while minimizing the “cost” of finding that experience. Thompson sampling always picks a winner, even if there is no statistical difference between two experiences. For more information, see [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling). |

Consider the following details when using Automated Personalization:

**Automated Personalization uses a Random Forest algorithm to personalize.**

Random Forest is a leading machine learning approach. In data-science speak, it is an ensemble classification or regression method that works by constructing a large number of decision trees based on visitor and visit attributes. Within Target, Random Forest is used to determine which experience is expected to have the highest likelihood of conversion (or highest revenue per visit) for each specific visitor. For example, visitors who use Chrome, are gold loyalty members, and access your site on Tuesdays might be more likely to convert with Experience A, while visitors from New York might be more likely to convert with Experience B. For more information about Random Forest in Target, see [Random Forest Algorithm](../../c-activities/t-automated-personalization/c-algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

**The personalization model optimizes for each visit.**

* The algorithm predicts a visitor's likelihood of conversion (or estimated revenue from conversion) in order to serve the best experience.
* A visitor is eligible for a new experience upon the end of an existing session (unless he or she is in the control group, in which case the experience that visitor sees on the first visit is the same experience he or she will see in subsequent visits).
* Within a session, the experience presented does not change to maintain visual consistency.

**The personalization model adapts to changes in visitor behavior.**

* The multi-arm bandit ensures that the model is always “spending” a small fraction of traffic to continue learning throughout the life of the activity, and to prevent over-exploitation of previously learned trends.
* The underlying models are re-built every 24 hours using the latest visitor behavior data to ensure Target is always leveraging changing visitor preferences.
* If the algorithm can't determine winning experiences for individual visitors, it automatically switches to showing the overall best-performing experience, while still continuing to look for personalized winners. The best-performing experience is found using [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

**The model continually optimizes a single goal metric.**

* This metric could be conversion-based or revenue-based (more specifically, Revenue per Visitor).

**Target automatically collects information about visitors to build the personalization models.**

* For more information about the attributes used in Auto-Target and Automated Personalization, see [Automated Personalization Data Collection](../../c-activities/t-automated-personalization/r-ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**Target automatically uses all Experience Cloud shared audiences to build the personalization models.**

* You don’t have to do anything specific to add audiences to the model. For information about using Experience Cloud Audiences with Target, see [Experience Cloud Audiences](../../c-integrating-target-with-mac/c-mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969).

**Marketers can upload offline data, propensity scores or other custom data to build personalization models.**

Offline data, such as CRM information or customer churn propensity scores, can be incredibly valuable when building personalization models. There are several ways to input data in Automated Personalization (AP) and Auto-Target personalization algorithms.

* [mbox parameters](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/c-methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [Profile parameters](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/c-methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [Server-side APIs for profile update](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/c-methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)

For information about the data automatically collected and used by Automated Personalization and Auto-Target personalization algorithms, see [Automated Personalization Data Collection](../../c-activities/t-automated-personalization/r-ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).
