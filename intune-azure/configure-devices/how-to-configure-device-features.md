---
# required metadata

title: Configure Intune device feature settingstitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to use Intune to configure features on devices you manage."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure device feature settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Device restrictions let you control features on iOS and macOS devices like AirPrint, notifications, and shared device configurations.

Use the information in this topic to learn the basics about configuring device feature profiles, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing device restriction settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the device features profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply the settings. Currently, you can choose one of the following platforms for device features:
	- **iOS**
	- **macOS**
6. From the **Profile type** type drop-down list, choose **Device features**. 
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [AirPrint settings for iOS and MacOS](air-print-settings-for-ios-and-macos.md)
 	- [AirPlay settings for iOS](airplay-settings-for-ios-devices.md)
	- [Home screen layout settings for iOS](home-screen-settings-for-ios.md)
	- [App notification settings for iOS](app-notification-settings-for-ios.md)
	- [Shared device configuration settings for iOS](shared-device-settings-for-ios.md)
	- [Web content filter settings for iOS](web-content-filter-settings-for-ios.md)

8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](how-to-assign-device-profiles.md).



