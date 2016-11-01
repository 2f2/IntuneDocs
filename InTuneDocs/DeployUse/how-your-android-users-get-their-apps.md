---
# required metadata

title: How your Android users get their apps | Microsoft Intune
description: Methods for making Android apps available to end users
keywords:
author: Staciebarkerms.author: stabar
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# How your Android users get their apps
Use this information to understand how and where your Android end users get the apps that you distribute through Microsoft Intune. The information can vary by device type (native Android devices or Samsung Knox Standard devices).

## Native (non-Samsung Knox) Android devices

| App type | Line-of-business (LOB) apps | Play Store apps  |
| ------------- |-------------| -----|
| Available apps      | Users tap **install** in the Company Portal. A notification appears, which users then tap to start the installation. After the installation is successful, the notification disappears. | Users tap the app in the Company Portal and are taken to an app page in the Play Store, where they can start the installation.|
| Required apps      | Users are shown a notification, which they cannot dismiss, indicating that they need to install an app. Users tap the notification to start the installation. After the installation is successful, the notification disappears.    | Users are shown a notification, which they cannot dismiss, indicating that they need to install an app. Users tap the notification and are taken to an app page in the Play Store, where they can start the installation. After the installation is successful, the notification disappears. |

## Samsung Knox Standard Android devices

| App type | Line-of-business (LOB) apps | Play Store apps  |
| ------------- |-------------| -----|
| Available apps      | Users tap **install** in the Company Portal. The app installs without further user intervention. | Users tap the app in the Company Portal and are taken to an app page in the Play Store, where they can start the installation.|
| Required apps      | The app is installed without any user intervention.    | Users are shown a notification, which they cannot dismiss, indicating that they need to install an app. Users tap the notification and are taken to an app page in the Play Store, where they can start the installation. After the installation is successful, the notification disappears. |

Apps can be managed or unmanaged, as described below. The process of making apps managed is the same for all types of Android devices.

**Managed apps** - These are apps that can be managed through policies. They have been "wrapped" by Intune or built with the Intune Mobile Application Management (MAM) Software Development Kit (SDK). These apps can be managed by Intune, and application policies can be applied to them.

**Unmanaged apps** - These are apps that cannot be managed through policies. They have not been wrapped by Intune or do not incorporate the Intune MAM SDK. Application policies cannot be applied to these apps.

### See also
[Add apps with Microsoft Intune](/intune/deploy-use/add-apps)

[How your iOS users get their apps](how-your-ios-users-get-their-apps.md)

[How your Windows users get their apps](how-your-windows-users-get-their-apps.md)
