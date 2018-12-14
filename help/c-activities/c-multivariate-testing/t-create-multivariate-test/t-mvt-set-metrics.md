---
description: Use metrics in a Multivariate Test to determine when a visit is successful.
keywords: multivariate;mvt;metrics;set metrics;goal metric;activity settings;success
  metric;conversion;revenue;engagement
seo-description: Use metrics in a Multivariate Test to determine when a visit is successful.
seo-title: Set metrics
solution: Target,standard
title: Set metrics
uuid: 0fb297ba-f1c3-4139-ac37-7fa0bf2ac308
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Set metrics{#set-metrics}

Use metrics in a Multivariate Test to determine when a visit is successful.

For detailed information about success metrics, see [Success Metrics](../../../c-activities/r-success-metrics/r-success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Specify the goal of the activity.
1. Select a [success metric](../../../c-activities/r-success-metrics/r-success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![](assets/mvt_metrics.png)

   The [!UICONTROL Select Metrics] page lists the success metrics you can choose for your activity. The success metrics are divided into the following categories:

   * Conversion
   * Revenue
   * Engagement
   You can use any of the pre-built success metrics, or create a custom success metric. You can also mark a success metric as a primary metric. Reports and Experience Cloud cards default to show the primary metric, if one is set.
1. Specify the settings for your metrics.

   The available settings depend on the success metric you are using.

   If enabled, the [!UICONTROL Estimated Value of the Conversion]field (not available for the Page Score metrics) provides a value for your goal. This value enables Target to calculate an estimated lift in revenue. This field is optional; however, incremental revenue for any non-revenue metric cannot be calculated without it. The data type is currency. This field is progressively shown after the user indicates the action taken to satisfy the goal. See [Estimating Lift in Revenue](../../../administrating-target/r-target-account-preferences/c-estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE) for more information.

   The correct configuration of success metrics is critical for making sure you get the data you expect.

   For more information, see [Success Metrics](../../../c-activities/r-success-metrics/r-success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)
1. (Optional) Add additional metrics.
1. Click **[!UICONTROL Continue]** when you are finished setting your metrics.
Note that when you name or rename a metric, the following characters are not allowed:

   <table id="table_F5E365667FDC48AD8B4461E40CD669B8"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Character </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>/ </p> </td> 
      <td colname="col2"> <p>Forward slash </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>? </p> </td> 
      <td colname="col2"> <p>Question mark </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p># </p> </td> 
      <td colname="col2"> <p>Number sign </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>: </p> </td> 
      <td colname="col2"> <p>Colon </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>= </p> </td> 
      <td colname="col2"> <p>Equals to </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>+ </p> </td> 
      <td colname="col2"> <p>Plus </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>- </p> </td> 
      <td colname="col2"> <p>Minus </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>@ </p> </td> 
      <td colname="col2"> <p>At sign </p> </td> 
   </tr> 
   </tbody> 
   </table>

**Activity Metrics (7:43)**

This video includes information about working with success metrics.

* Understand "goal" metrics
* Understand and build Conversion, Revenue, and Engagement metrics
* Build a click-tracking metric

>[!VIDEO](https://www.youtube.com/watch?v=oCMD2SymhoI)
