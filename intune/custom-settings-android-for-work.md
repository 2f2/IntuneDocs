---
# required metadata

title: Add custom settings to Android Enterprise devices in Microsoft Intune - Azure | Microsoft Docs
description: Add or create a custom profile for Android Enterprise devices to create  in Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use custom settings for Android Enterprise devices in Microsoft Intune

Using Microsoft Intune, you can add or create custom settings for your Android Enterprise devices using a "custom profile". Custom profiles are a feature in Intune. They are designed to add device settings and features that aren't built in to Intune.

Android Enterprise custom profiles use Open Mobile Alliance Uniform Resource Identifier (OMA-URI) settings to control features on Android Enterprise devices. These settings are typically used by mobile device manufacturers to control features on the device.

Intune supports a limited number of Android custom profiles.

This article shows you how to create a custom profile for Android Enterprise devices. It also provides an example of a custom profile that blocks copy-and-paste.

## Create the profile

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following settings:

    - **Name**: Enter a name for the profile, such as `android enterprise custom profile`
    - **Description**: Enter a description for the profile
    - **Platform**: Choose **Android Enterprise**
	- **Profile type**: Choose **Custom**

4. In **Custom OMA-URI Settings**, select **Add**. Enter the following settings:

    - **Name**: Enter a unique name for the OMA-URI setting so you can easily find it.
    - **Description**: Enter a description that gives an overview of the setting, and any other important details.
    - **OMA-URI**: Enter the OMA-URI you want to supply a setting.
    - **Data type**: Choose the data type you'll use for this OMA-URI setting. Your options:

      - String
      - String (XML file)
      - Date and time
      - Integer
      - Floating point
      - Boolean
      - Base64 (file)

    - **Value**: Enter the data value you want to associate with the OMA-URI you entered. The value depends on the data type you selected. For example, if you choose **Date and time**, select the value from a date picker.

5. Select **OK** to save your changes. Continue to add more settings as needed.
6. When finished, choose **OK** > **Create** to create the Intune profile. When complete, your profile is shown in the **Device configuration - Profiles** list.

## Example

In this example, you create a custom profile that restricts copy and paste actions between work and personal apps on Android Enterprise devices.

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following settings:

    - **Name**: Enter a name for the profile, such as `android ent block copy paste custom profile`.
    - **Description**: Enter a description for the profile.
    - **Platform**: Choose **Android Enterprise**.
	- **Profile type**: Choose **Custom**.

4. In **Custom OMA-URI Settings**, select **Add**. Enter the following settings:

    - **Name**: Enter something like `Block copy and paste`.
    - **Description**: Enter something like `Blocks copy/paste between work and personal apps`.
    - **OMA-URI**: Enter `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste`.
    - **Data type**: Choose **Boolean** so the value for this OMA-URI is **True** or **False**.
    - **Value**: Choose **True**.

5. After you enter the settings, your environment should like similar to the following image:

    ![Block copy and paste for Android work profile.](./media/custom-policy-afw-copy-paste.png)

When you assign this profile to Android Enterprise devices you manage, copy and paste is blocked between apps in the work and personal profiles.

## Next steps

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md).

See how to [create the profile on Android devices](custom-settings-android.md).