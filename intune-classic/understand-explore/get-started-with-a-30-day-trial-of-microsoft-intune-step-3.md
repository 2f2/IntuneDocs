---
# required metadata

title: Create groups to organize users and devices in free trial 
description: How to create device groups and user groups when you sign up for a free, 30-day evaluation of Microsoft Intune.
keywords:
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Create groups to organize evaluation subscription users and devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Groups in Intune give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a variety of administrative tasks at scale, from setting policies for a set of users to deploying applications to a set of devices.

## Create a device group
Use device groups to deploy software and updates, and configure Microsoft Intune Agent Settings and Windows Firewall Settings policies. For example, set up a "My Trial Devices" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **Overview** &gt; **Create Group**.

2.  For the **Group name**, type “My Trial Devices” and, from the parent group list, select **All Devices**, and then choose **Next**.

3.  On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.

4.  On the **Define Direct Membership** page, choose **Next**. If you previously created a group that does not include all devices, and you wanted to add specific devices to your new group, you can do that here.

5.  On the **Summary** page, review the actions that will be taken, and then choose **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace under **All Devices**. From here, you can also edit or delete the group.

## Create a user group
Use user groups to deploy software and device policies. For example, set up a "My Trial Users" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **Overview** &gt; **Create Group**.

2.  For the **Group name**, type “My Trial Users” and, from the parent group list, select **All Users**, and then choose **Next**.

3.  On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.

4.  Beside **Exclude members from these security groups**, choose **Browse** and then select **Company Administrator**. This exclusion lets you manage the My Trial Users group without affecting the Company Administrator account (also known as the tenant administrator).

5.  On the **Define Direct Membership** page, choose **Next**. You don’t need to do anything here because you want the My Trial Users group to include all users, except for the Company Administrator.

6.  On the **Summary** page, review the actions that will be taken, and then choose **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace under **All Users**. From here, you can also edit or delete the group.

To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](/intune-classic/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## Next steps
[Create policies](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  
