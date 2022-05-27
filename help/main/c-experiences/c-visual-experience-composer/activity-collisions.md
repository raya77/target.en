---
keywords: targeting;collisions;conflicts
description: Collisions occur when multiple activities are set up to deliver content to the same page. Learn how to avoid collisions when using Adobe Target.
title: How Can I Avoid Activity Collisions?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
---
# Activity collisions

The [!UICONTROL Collisions] tab on the [!UICONTROL Activity Overview] page in [!DNL Adobe Target] lists activity collisions on your site.

An activity collision occurs when multiple activities are set up to deliver content to the same page. If an activity collision occurs, you may not see the expected content on your page.

The [!UICONTROL Collisions] tab is available on the activity overview page and can inform you if your activity contains potential collisions. All activities on the same URL are listed, regardless of any audience targeting in each activity. Open this tab for a list of activities that might be colliding. Click an activity in the list to view the overview page for that activity. If the collision alters the expected experience, edit the activity.

The [!UICONTROL Collisions] list helps you:

* Identify whether a test is already running on a page before you set up a new activity 
* Troubleshoot an activity if the expected content does not appear

The [!UICONTROL Collisions] list shows every [!DNL Target] scenario where the mbox is used and that uses the same URL. For each potential collision, the list shows the Activity URL, the mbox name where the collision might occur, and any activities that match both of those criteria. If there are multiple mboxes, they are each listed.

The list shows the status and priority of each potential collision, along with other information. You can use the status and priority to help you determine the likelihood of a collision occurring. For example, if there is a potential collision between two activities and one is inactive, there will be no actual collision unless the inactive activity is activated. If the potential collision is between two live activities with the same priority and the same audience, a collision will occur. You can change the priority or status to prevent the collision.

If the audiences are different, there is still a potential collision because it's possible a particular visitor could belong to multiple audiences.
