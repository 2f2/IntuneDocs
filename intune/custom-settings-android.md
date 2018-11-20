---
# required metadata

title: Add custom settings to Android devices in Microsoft Intune - Azure | Microsoft Docs
description: Add or create a custom profile for Android devices to create a WiFi profile with a pre-shared key, create a per-app VPN profile, or allow/block apps for Samsung Knox Standard devices in Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use custom settings for Android devices in Microsoft Intune

Using Microsoft Intune, you can add or create custom settings for your Android devices using a "custom profile". Custom profiles are a feature in Intune. They are designed to add device settings and features that aren't built in to Intune.

Android custom profiles use Open Mobile Alliance Uniform Resource Identifier (OMA-URI) settings to configure different features on Android devices. These settings are typically used by mobile device manufacturers to control these features.

Using a custom profile, you can configure and assign the following Android settings. The following settings aren't built in to Intune:

- [Create a Wi-Fi profile with a pre-shared key](/intune/wi-fi-profile-shared-key)
- [Create a per-app VPN profile](/intune/android-pulse-secure-per-app-vpn)
- [Allow and block apps for Samsung Knox Standard devices](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Only the settings listed can be configured by in a custom profile. Android devices don't expose a complete list of OMA-URI settings you can configure. If you'd like to see more settings, then vote for more settings at the [Intune Uservoice site](https://microsoftintune.uservoice.com/forums/291681-ideas).

This article shows you how to create a custom profile for Android devices.

## Create the profile

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following settings:

    - **Name**: Enter a name for the profile, such as `android custom profile`.
    - **Description**: Enter a description for the profile.
    - **Platform**: Choose **Android**.
	- **Profile type**: Choose **Custom**.

4. In **Custom OMA-URI Settings**, select **Add**. Enter the following settings:

    - **Name**: Enter a unique name for the OMA-URI setting so you can easily find it.
    - **Description**: Enter a description that gives an overview of the setting, and any other important details.
    - **OMA-URI**: Enter the OMA-URI you want to use as a setting.
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

See how to [create the profile on Android Enterprise devices](custom-settings-android-for-work.md).
