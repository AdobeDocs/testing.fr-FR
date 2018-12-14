---
description: Information about expected data variances between Target and Adobe Analytics
  when not using Analytics as the Reporting Source (A4T), which eliminates data variance
  altogether.
keywords: data variances;analytics;differences;variance;a4t;analytics for target;analytics
  as the reporting source;discrepancies;discrepancy
seo-description: Information about expected data variances between Target and Adobe
  Analytics when not using Analytics as the Reporting Source (A4T), which eliminates
  data variance altogether.
seo-title: Expected Data Variances When Not Using A4T
solution: Target
title: Expected Data Variances When Not Using A4T
topic: Advanced
uuid: 61bef460-8613-4251-b1b2-b6226ec86d9b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Expected Data Variances When Not Using A4T{#expected-data-variances-when-not-using-a-t}

Information about expected data variances between Target and Adobe Analytics when not using Analytics as the Reporting Source (A4T), which eliminates data variance altogether.

<table id="table_8C6EF23E70CF4788AADA1C9941DEDF31"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <p>Note:  With A4T, both Analytics and Target reporting of activities use Analytics data exclusively, so there is no variance between the solutions in Target activity reports. In some circumstances, however, customers might compare Target data to Analytics data outside the scope of the A4T integration and, thus, experience the variance issues described below. </p> </p> <p>Here is a scenario in which you might experience expected data variance: Suppose you create an Auto-Allocate activity open to all visitors to a particular page. Because Auto-Allocate activities don't support A4T, all of the activity data is collected by Target. You might expect that the visitors to the activity in the Target reporting should match the visitors to that page in the Analytics reporting for the same date range. This is a scenario in which the variance described below is expected. </p> <p>For a complete list of activity types that support A4T, see <a href="../../c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA" format="dita" scope="local"> Supported Activity Types </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Variances of 15-20% are normal, even with similar data sets. Systems that count differently can result in much higher data variances, as much as 35-50%. In some cases, variances can be even higher.

Although actual data can vary significantly, trends are usually consistent. As long as the differences and trends remain consistent, the data remains valuable and useful. If the differences and trends are inconsistent, it could mean that something is set up incorrectly. In this case, contact your account representative for assistance.

Analytics uses a system based on visits and transactions, but Target uses visitor-based metrics. That means that whenever a visitor opens a page, it counts as a visit in Analytics, but Target does not count the visit until the conditions set in the activity are met.

Reports in Target show performance based on the conversion mbox selected when defining the activity, but this conversion mbox data is not sent to Analytics, which has its own conversion variables as defined by your Analytics tagging implementation. In cases where you might expect identical data (for example, if a retailer's order confirm page contains both a conversion mbox and an Analytics purchase event), data might differ due to the placement of these tags. In general, trends in the two products' reports should be the similar.

Expected data variances can be caused by both technical and business variances.

## Examples of Technical Variances {#section_C3B50ED2E2F9416FAC91437CF1A87369}

The following can cause data variances based on technical differences:

* Target visitors must allow cookies and JavaScript
* 1st- and 3rd-party cookies are processed differently; as a result, data from these cookie types do not match
* Relative location of tags on pages and "leakage" caused by visitors who exit the page before it fully loads
* Time zone considerations
* Differences in which devices can be counted

## Examples of Business Variances {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

The following can cause data variances based on business differences:

* Differences between visitor and visit metrics
* Targeting on activities excludes some visitors
* A single mbox can be located on multiple pages, counting visitors on each of those pages
* Activity priorities might include some visitors and exclude others on a page
* Visitors who have converted once can be counted again when they re-enter the activity
* Analytics counts all conversions for all visits and visitors, but Target only counts conversions for those visits and visitors that are included in the activity

