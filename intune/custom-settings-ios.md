---
# required metadata

title: Add custom settings to iOS devices in Microsoft Intune - Azure | Microsoft Docs
titleSuffix:
description: Export iOS settings from Apple Configurator or Apple Profile Manager tools, and then import these settings into Microsoft Intune. These settings can create, use, and contorol custom settings and features on iOS devices. This custom profile can then be assigned or distributed to iOS devices in your organization to create a baseline or standard.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use custom settings for iOS devices in Microsoft Intune

Using Microsoft Intune, you can add or create custom settings for your iOS devices using "custom profiles". Custom profiles are a feature in Intune. They are designed to add device settings and features that aren't built in to Intune.

When using iOS devices, there are two ways to get custom settings into Intune:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

You can use these tools to export settings to a configuration profile. In Intune, you import this profile, and then assign this profile to your iOS users and devices. Once assigned, the settings are distributed, and also create a baseline or standard for iOS in your organization.

This article shows you how to create a custom profile for iOS devices. It also provides some guidance on using Apple Configurator and Apple Profile Manager.

## Before you begin

- When using **Apple Configurator** to create the configuration profile, be sure the settings you export are compatible with the iOS version on the devices you're using. For information on resolving incompatible settings, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.

- When using **Apple Profile Manager**, be sure to:

  - Enable [mobile device management](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) in Profile Manager.
  - Add [iOS devices](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) in Profile Manager.
  - After you add a device in Profile Manager, go to **Under the Library** > **Devices** > select your device > **Settings**. Enter the general settings for the device.

    Download and save this file. You'll enter this file in the Intune profile.

  - Be sure the settings you export from the Apple Profile Manager are compatible with the iOS version on the devices you're using. For information on resolving incompatible settings, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.

## Create the profile

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following settings:

    - **Name**: Enter a name for the profile, such as `ios custom profile`.
    - **Description**: Enter a description for the profile.
    - **Platform**: Choose **iOS**.
	- **Profile type**: Choose **Custom**.

4. In **Custom configuration**, enter the following settings:

    - **Custom configuration profile name**: Enter a name for the policy. This name is shown on the device, and in the Intune status.
    - **Configuration profile file**: Browse to the configuration profile you created using the Apple Configurator or Apple Profile Manager. The file you imported is shown in the **File contents** area.

5. Select **OK** > **Create** to create the Intune profile. When complete, your profile is shown in the **Device configuration - Profiles** list.

## Next steps

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md).

See how to [create the profile on macOS devices](custom-settings-macos.md). 