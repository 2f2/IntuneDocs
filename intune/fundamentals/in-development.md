---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 01/07/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
ms.collection: M365-identity-device-management
---

# In development for Microsoft Intune - January 2020

To help in your readiness and planning, this page lists Intune UI updates and features that are in development but not yet released. In addition to the information on this page: 

- If we anticipate that you'll need to take action before a change, we'll publish a complementary post in Office message center.
- When a feature enters production, whether it's a preview or generally available, the feature description will move from this page to [What's new](whats-new.md).
- This page and the [What's new](whats-new.md) page are updated periodically. Check back for additional updates.
- Refer to the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) for strategic deliverables and timelines.

> [!NOTE]
> This page reflects our current expectations about Intune capabilities in a future release. Dates and individual features might change. This page doesn't describe all features in development.

**RSS feed**: Find out when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## App management

### Display notifications for the Company Portal app on Windows<!-- 1808082  -->
We'll update the Company Portal app on Windows devices to display toast notifications to users, even when the application is closed. The update will show notifications for available apps only when the installation status is completed or failed. The Company Portal app won't show notifications for required applications. 

### Display installation status messages for the Company Portal app<!-- 2514416  -->
The Company Portal app will show additional app installation status messages to end users. The following conditions will apply to new Win32 dependency features:
- App failed to install. Dependencies defined by the admin were not met.

### Retarget web clips to Microsoft Edge on iOS devices<!-- 5455276 idready -->
Web clips, which act as pinned web apps on iOS devices, will need to be updated. Newly deployed web clips will open in Microsoft Edge instead of the Intune Managed Browser if required to open in a protected browser. You must retarget pre-existing web clips to ensure they open in Microsoft Edge instead of the Managed Browser. 

### User experience change when adding apps to Intune<!-- 4705829 idready -->
You will see a new user experience when adding apps via Intune. This experience provides the same settings and details that you have used previously, however the new experience follows a wizard-like process before adding an app to Intune. This new experience also provides a review page before adding the app. From the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Apps** > **All apps** > **Add**. For more information, see [Add apps to Microsoft Intune](~/apps/apps-add.md).

#### Require Win32 apps to restart <!-- 3136567-->
You can require that a Win32 app must restart after a successful install. Also, you can choose the amount of time (the grace period) before the restart must occur.

<!-- ***********************************************-->
## Device configuration

### Add automatic proxy settings to Wi-Fi profiles for Android Enterprise work profiles<!-- 4490822 idready -->
On Android Enterprise Work Profile devices, you can create Wi-Fi profiles. When you choose the Wi-Fi Enterprise type, you can also enter the Extensible Authentication Protocol (EAP) type used on your Wi-Fi network.

In a future update, when you choose the Enterprise type, you'll be able to enter automatic proxy settings, including a proxy server URL, such as `proxy.contoso.com`.

To see the current Wi-Fi settings you can configure, go to [Add Wi-Fi settings for devices running Android Enterprise and Android kiosk in Microsoft Intune](../configuration/wi-fi-settings-android-enterprise.md).

Applies to:
- Android Enterprise work profile

### Wired network device configuration profiles for macOS devices<!-- 3508686  -->
A new macOS device configuration profile will be available that configures wired networks (**Device configuration** > **Profiles** > **Create profile** > **macOS** for platform > **Wired Network** for profile type). Use this feature to create 802.1x profiles to manage wired networks, and deploy these wired networks to your macOS devices.

Applies to:
- macOS

### VPN profiles with IKEv2 VPN connections can use always on with iOS devices <!-- 1947932 idready -->
On iOS devices, you can create a VPN profile that uses an IKEv2 connection (**Device configuration** > **Profiles** > **Create profile** > **iOS/iPadOS** for platform > **VPN** for profile type). In a future update, you can configure always-on with IKEv2. When configured, IKEv2 VPN profiles connect automatically, and stay connected (or quickly reconnect) to the VPN. It stays connected even when moving between networks or restarting devices.

On iOS, always-on VPN is limited to IKEv2 profiles.

To see the current IKEv2 settings you can configure, go to [Add VPN settings on iOS devices in Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Applies to:
- iOS

### Improved user interface experience when creating configuration profiles on iOS and macOS devices<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
When you create a profile for iOS or macOS devices, the experience in the Endpoint Management Admin Center will be updated. This change impacts the following device configuration profiles (**Devices** > **Configuration Profiles** > **Create profile** > **iOS** or **macOS** for platform):

- Custom: iOS, macOS
- Device features: iOS, macOS
- Device restrictions: iOS, macOS
- Endpoint protection: macOS
- Extensions: macOS
- Preference file: macOS

### Improved user interface experience when creating OEMConfig configuration profiles on Android Enterprise devices<!-- 5568645 idready  -->
When you create or edit an OEMConfig profile for Android Enterprise devices, the experience in the Endpoint Management admin center is updated. The updated experience will provide a summary of settings you've configured at a glance. This change impacts the OEMConfig device configuration profile (**Devices** > **Configuration profiles** > **Create profile** > **Android Enterprise** for platform > **OEMConfig** for profile type).

This feature applies to:
- Android Enterprise 

<!-- ***********************************************-->
## Device enrollment

### Block Android enrollments by device manufacturer<!--5197392 idready-->
You'll be able to block devices from enrolling based on the manufacturer of the device. This applies to Android device administrator and Android Enterprise work profile devices. To see enrollment restrictions, go to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)> **Devices** > **Enrollment restrictions**.



<!-- ***********************************************-->
## Device management

### Deploy Software Updates to macOS devices <!-- 3194876 idready -->
You'll be able to deploy Software Updates to groups of macOS devices. This feature includes critical, firmware, configuration file, and other updates. You'll be able to send updates on the next device check-in or select a weekly schedule to deploy updates in or out of time windows that you set. This helps when you want to update devices outside standard work hours or when your help desk is fully staffed. You'll also get a detailed report of all macOS devices with updates deployed. You can drill into the report on a per-device basis to see the statuses of particular updates.

### New information in device details<!-- 4471759 5604099  -->
The following information will be added to the **Overview** page for devices:
- Memory Capacity (amount of physical memory on the device)
- Storage Capacity (amount of physical storage on the device) 
- CPU Processor Type and Speed
- RAM and processor data

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
## Role-based access control

### New Intune built-in role Endpoint security manager<!--4253397 idready-->
A new Intune built-in role will be available: the Endpoint security manager. This new role gives admins full access to the Endpoint Manager node in Intune and ready-only access to other areas. The role is an expansion of the “Security Administrator” role from Azure AD. If you currently just have Global Admins as roles, then there’s no changes needed. If you use roles, and you’d like the granularity that the Endpoint Security Manager provides, then assign that role when it is available. For more information about built-in roles, see [Role-based access control](role-based-access-control.md).

### Intune Roles user interface changes coming<!--5801612 idready-->
The user interface for [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) > **Tenant administration** > **Roles** will be changing to a more user-friendly and intuitive design. This experience provides the same settings and details that you use now, however the new experience employs a wizard-like process.


<!-- ***********************************************-->
## Security

### Derived credentials support on Android COBO devices<!--4839592-->
You'll be able to use derived credentials on Android Enterprise fully managed devices. Support will be included for retrieving a derived credential for Entrust Datacard, Intercede, and DISA Purebred. You'll be able to use a derived credential for app authentication, Wi-Fi, VPN, or S/MIME signing and/or encryption with apps that support it. 

<!-- ***********************************************-->
## Notices

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## See also
For details about recent developments, see [What's new in Microsoft Intune](whats-new.md).


