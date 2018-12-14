---
description: The Collisions tab on the Activity Overview page lists activity collisions
  on your site.
keywords: Targeting
seo-description: The Collisions tab on the Activity Overview page lists activity collisions
  on your site.
seo-title: Activity Collisions
solution: Target
title: Activity Collisions
uuid: 0e53ef60-2f71-4b34-9383-1de5cf5d3ab5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Activity Collisions{#activity-collisions}

The Collisions tab on the Activity Overview page lists activity collisions on your site.

An activity collision occurs when multiple activities are set up to deliver content to the same page. If an activity collision occurs, you may not see the expected content on your page.

If your activity contains potential collisions, the [!UICONTROL Collisions] tab is available the on the activity overview page. All activities on the same URL are listed, regardless of any audience targeting in each activity. Open this tab for a list of activities that might be colliding. Click an activity in the list to view the overview page for that activity. If the collision alters the expected experience, edit the activity.

The Collisions list helps you:

* Identify whether a test is already running on a page before you set up a new activity
* Troubleshoot an activity if the expected content does not appear

The Collisions list shows every Target Standard scenario where the mbox is used and that uses the same URL. For each potential collision, the list shows the Activity URL, the mbox name where the collision might occur, and any activities that match bot of those criteria. If there are multiple mboxes, they are each listed.

The list shows the status and priority of each potential collision, along with other information. You can use the status and priority to help you determine the likelihood of a collision occurring. For example, if there is a potential collision between two activities and one is inactive, there will be no actual collision unless the inactive activity is activated. If the potential collision is between two live activities with the same priority and the same audience, a collision will occur. You can change the priority or status to prevent the collision.

If the audiences are different, there is still a potential collision because it's possible a particular visitor could belong to multiple audiences.
