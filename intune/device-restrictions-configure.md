---
# required metadata

title: Configure device restriction settings in Microsoft Intune - Azure | Microsoft Docs
description: Add a device profile to restrict features on Android, macOS, iOS, Windows Phone, and Windows 10 devices in Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
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
 
# Configure device restriction settings in Microsoft Intune

Device restrictions let you control a wide range of settings and features you manage across a range of categories such as:
- Security
- Browser
- Hardware
- Data sharing settings

For example, you can create a device restriction profile that prevents users of iOS devices from accessing the device camera.

Learn device restriction profile basics, and then read further articles for each platform to learn about device specifics.

## Create a device profile containing device restriction settings

1. In to the [Azure portal](https://portal.azure.com), select **All services** > filter on **Intune** > select **Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter a **Name** and **Description** for the device restriction profile.
4. From the **Platform** drop-down list, select the device platform to which you want to apply custom settings. Currently, you can choose one of the following platforms for device restriction settings:

    - **Android**
    - **Android enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 and later**
    - **Windows 10 and later**

5. From the **Profile type** drop-down list, choose **Device restrictions**. To create a device restrictions profile for Windows 10 Team devices, such as Surface Hub, then choose **Device restrictions (Windows 10 Team)**.
6. Depending on the platform you chose, the settings you can configure are different. Choose your platform detailed settings:

    - [Android settings](device-restrictions-android.md)
    - [Android enterprise settings](device-restrictions-android-for-work.md)
    - [iOS settings](device-restrictions-ios.md)
    - [macOS settings](device-restrictions-macos.md)
    - [Windows Phone 8.1 settings](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10 settings](device-restrictions-windows-10.md)
    - [Windows 10 Team settings](device-restrictions-windows-10-teams.md)
    - [Windows Holographic for Business settings](device-restrictions-windows-holographic.md)

7. When you're done, go back to the **Create profile** page, and select **Create**.

The profile is created and appears on the profiles list page. 

## Next step

After the profile is created, it's ready to be assigned. See [assign device profiles](device-profile-assign.md) for the steps. 

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
