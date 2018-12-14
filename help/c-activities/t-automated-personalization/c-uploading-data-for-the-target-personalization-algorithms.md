---
description: Offline data, such as CRM information or customer churn propensity scores,
  can be incredibly valuable when building personalization models.
seo-description: Offline data, such as CRM information or customer churn propensity
  scores, can be incredibly valuable when building personalization models.
seo-title: Upload data for Target's personalization algorithms
solution: Target
title: Upload data for Target's personalization algorithms
topic: Premium
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Upload data for the Target personalization algorithms{#upload-data-for-target-s-personalization-algorithms}

Offline data, such as CRM information or customer churn propensity scores, can be incredibly valuable when building personalization models.

There are several ways to input data in Automated Personalization (AP) and Auto-Target personalization algorithms. In addition to the methods in [Methods to get Data into Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/c-methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17), Experience Cloud shared audiences (Adobe Analytics, Audience Management) and in-activity reporting audiences are also used in our algorithms.

For information about the data automatically collected and used by Automated Personalization and Auto-Target personalization algorithms, see [Automated Personalization Data Collection](../../c-activities/t-automated-personalization/r-ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## Best Practices {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

The following list presents best practices for uploading data for Target's personalization algorithms:

* The more high-quality data that is available to Target’s personalization algorithms, the better the quality the resulting models in your AP and Auto Target activities.
* Limit using multiple profile scripts or attributes that serve the same purpose.
* Don’t pass a unique Id, such as a session ID if not needed.
* Review what data Target automatically collects ( [Data Collection for Target's Personalization Algorithms](../../c-activities/t-automated-personalization/r-ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)) so that you don’t send duplicate information. For example, Target uses IP addresses to determine visitors' ZIP codes. It is not necessary to pass this information as a separate variable.
* Do not pass multiple values in the same attribute/variable. If multiple variables are concatenated, Target’s personalization algorithms treat each string as a unique value, reducing the value of the information for personalization.
* Use a memorable and meaningful naming convention to make your [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/c-personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) more understandable.

