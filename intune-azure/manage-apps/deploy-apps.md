---
# required metadata

title: How to assign apps to groups with Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Once you've added an app to Intune, you'll want to assign it to groups of users or devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# How to assign apps to groups with Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Once you've added an app to Intune, you'll want to get it out to users and devices. You do this by assigning it.

Apps can be assigned to devices whether or not they are managed by Intune. Use the following table to help you understand the various options for assigning apps to users and devices:

|||
|-|-|
|&nbsp;|Devices enrolled with Intune|Devices not enrolled with Intune|
|Assign to users|Yes|Yes|
|Assign to devices|Yes|No|
|Assign wrapped apps, or apps incorporating the Intune SDK (for app protection policies)|Yes|Yes|
|Assign apps as Available|Yes|Yes|
|Assign apps as Required|Yes|No|
|Uninstall apps|Yes|Yes|
|End users install available apps from Company Portal app|Yes|No|
|End users install available apps from web-based Company Portal|Yes|Yes|

> [!NOTE]
> Currently, you can assign apps to Android, Windows 10 Mobile, and Windows 10 desktop devices that are not enrolled with Intune.

## How to assign an app

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
1. In the **Manage Apps** workload, choose **Manage** > **Apps**.
2. On the list of apps blade, click the app you want to assign.
3. On the <*app name*> - **Overview** blade, choose **Manage** > **Assignments**.
4. Choose **Select Groups** then, on the **Select groups** blade, choose the Azure AD groups to which you want to assign the app.
5. For each app you choose, choose an **assignment type** for the app from:
	- **Available** - Users install the app from the Company Portal app or website.
	- **Not Applicable** - The app is not installed or shown in the Company Portal.
	- **Required** - The app is installed on devices in the selected groups.
	- **Uninstall** - The app is uninstalled from devices in the selected groups.
	- **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune. See the table above for help.
6. Once you are done, choose **Save**.

The app is now assigned to the group you chose.

See [How to monitor apps](monitor-apps.md) for information to help you monitor app assignments.
