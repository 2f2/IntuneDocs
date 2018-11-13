---
# required metadata

title: Add custom settings to Windows Phone 8.1 devices in Microsoft Intune - Azure | Microsoft Docs
titleSuffix:
description: Add or create a custom profile to use the OMA-URI settings for devices running Windows Phone 8.1 in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
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

# Use custom settings for Windows Phone 8.1 devices in Intune

Using Microsoft Intune, you can add or create custom settings for your Windows Phone 8.1 devices using "custom profiles". Custom profiles are a feature in Intune. They're designed to add device settings and features that aren't built in to Intune.

Windows Phone 8.1 custom profiles use Open Mobile Alliance Uniform Resource Identifier (OMA-URI) settings to configure different features. These settings are typically used by mobile device manufacturers to control features on the device.

This article shows you how to create a custom profile for Windows Phone 8.1 devices. 

## Create the profile

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following settings:

    - **Name**: Enter a name for the profile, such as `windows phone custom profile`.
    - **Description**: Enter a description for the profile.
    - **Platform**: Choose **Windows Phone 8.1**.
    - **Profile type**: Choose **Custom**.

4. In **Custom OMA-URI Settings**, select **Add**. Enter the following settings:

    - **Name**: Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.
    - **Description**: Enter a description that gives an overview of the setting, and any other relevant information to help you locate the profile.
    - **OMA-URI** (case sensitive): Enter the OMA-URI you want to use as a setting.
    - **Data type**: Choose the data type you'll use for this OMA-URI setting. Your options:

        - String
        - String (XML file)
        - Date and time
        - Integer
        - Floating point
        - Boolean
        - Base64 (file)

    - **Value**: Enter the data value you want to associate with the OMA-URI you entered. The value depends on the data type you selected. For example, if you choose **Date and time**, select the value from a date picker.

    After you add some settings, you can select **Export**. **Export** creates a list of all the values you added in a comma-separated values (.csv) file.

5. Select **OK** to save your changes. Continue to add more settings as needed.
6. When finished, choose **OK** > **Create** to create the Intune profile. When complete, your profile is shown in the **Device configuration - Profiles** list.

## Next steps

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md).

See how to create a custom profile on [Windows 10 devices](custom-settings-windows-10.md).