---
# required metadata

title: What are device profiles in Microsoft Intune? | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about Intune device profiles and how they can help manage and protect devices in your company."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: azure-portal

---

# What are Microsoft Intune device profiles?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use the Microsoft Intune **Configure devices** workload to manage settings and features on all of the devices you manage. You'll mostly use this workload to create device profiles, which let you manage and control a whole range of different features and functionality on the devices you manage.

When you open this workload, you'll see the following options:

- **Overview** - This page gives you status and reports that help you monitor device configurations that you have assigned to users and devices.
- **Manage Profiles** - This section is where you'll go to create device configuration profiles. You can find a list below of all the profile types you can create.
- **Setup Certificate Authority** - This workflow walks you though the steps required to configure certificates. You'll need to do this if you want to work with Intune certificate profiles.

## Getting started

The workflow for creating device profiles is similar for all profiles. Read [How to create Microsoft Intune device configuration profiles](/intune-azure/configure-devices/how-to-create-device-profiles) for information about how to create profiles. Then read on for specific information about creating settings for each profile type.

You can manage the following capabilities on your devices:

## Device restrictions
Device restrictions let you control a wide range of settings and features you manage across a range of categories including security, browser, hardware, and data sharing settings. For example, you could create a device restriction profile that prevents users of iOS devices from accessing the device camera.
For more information, see [How to configure device restriction settings](how-to-configure-device-restrictions.md)
Supports: Android, iOS, macOS, Windows 10 and Windows 10 Team.

## Email
Email profiles let you create, deploy, and monitor Exchange ActiveSync email settings on devices you manage. By deploying these settings, you ensure consistency, reduce support calls, and let end users access company email on their personal devices without any required setup on their part.
For more information, see [How to configure email settings](how-to-configure-email-settings.md)
Supports: Android, iOS, Windows Phone 8.1 and Windows 10.

## Wi-Fi
Use Wi-Fi profiles to deploy wireless network settings to users and devices in your organization. When you deploy a Wi-Fi profile, your users will have access to your corporate Wi-Fi without having to configure it themselves.
For more information, see [How to configure Wi-Fi settings](how-to-configure-wi-fi-settings.md)
Supports: Android, iOS, macOS and Windows 8.1 (import only).

## VPN
Virtual private networks (VPNs) give your users secure remote access to your company network. Devices use a VPN connection profile to initiate a connection with the VPN server. Use VPN profiles to deploy VPN settings to users and devices in your organization, so they can easily and securely connect to the network.
For more information, see [How to configure VPN settings](how-to-configure-vpn-settings.md).
Supports: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 and Windows 10.

## Certificates
This profile type lets you configure trusted, SCEP, and PKCS certificates that can be assigned to devices and used to authenticate Wi-Fi, VPN, and email profiles.
For more information, see [How to configure certificates](how-to-configure-certificates.md)
Supports: Android, iOS, Windows Phone 8.1, Windows 8.1 and Windows 10.

## Edition upgrade
This profile type lets you automatically upgrade devices that run some versions of Windows 10 to a newer edition
For more information, see [How to configure Windows 10 edition upgrades](how-to-configure-windows-10-edition-upgrade.md)
Supports: Windows 10 only.

## Windows Information Protection
Windows Information Protection helps to protect against data leakage without otherwise interfering with the employee experience. It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees bring to work without requiring changes to your environment or other apps.
For more information, see [How to configure Windows Information Protection](how-to-configure-windows-information-protection.md)
Supports: Windows 10 only.

## Custom
Custom settings let you assign device settings that are not built-into Intune. For example, on Android devices, you can specify OMA-URI values that configure the device. For iOS devices, you can import a configuration file you created in the Apple Configurator.
For more information, see [How to configure custom settings](how-to-configure-custom-settings.md)
Supports: Android, iOS, macOS and Windows Phone 8.1.
