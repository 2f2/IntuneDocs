---
# required metadata

title: How to configure Intune custom device settingstitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to use Intune to configure custom settings on devices you manage."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
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

# How to configure custom device settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## When to use custom settings

Custom device settings can be useful when Intune doesn't have the settings you want to configure built-in, and available from other device profiles.
Custom settings are configured differently for each platform. For example, with Android and Windows devices, you can specify Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values to control features on devices. For Apple devices, you can import a file you created with the [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Use the information in this topic to learn the basics about configuring profiles with custom settings, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing custom settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply custom settings. Currently, you can choose one of the following platforms for custom device settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Custom**.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](custom-for-android.md)
	- [iOS settings](custom-for-ios.md)
	- [macOS settings](custom-for-macos.md)
	- [Windows Phone 8.1 settings](custom-for-windows-phone-8-1.md)
	- [Windows 10 settings](custom-for-windows-10.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](how-to-assign-device-profiles.md).
