---
# required metadata

title: Enroll devices - device enrollment managertitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Use the device enrollment manager account to enroll devices in Intune. "
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Enroll devices using device enrollment manager

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Organizations can use Intune to manage large numbers of mobile devices with a single user account. The *device enrollment manager* (DEM) account is a special user account that can enroll up to 1,000 devices. You add existing users to the DEM account to give them the special DEM capabilities. Each enrolled device uses a single license. We recommend that you use devices enrolled through this account as shared devices rather than personal ("BYOD") devices.  

Users must exist in the Azure portal to be added as device enrollment managers. For optimal security, the DEM user should not also be an Intune admin.

>[!NOTE]
>The DEM enrollment method can't be used with these other enrollment methods: [Apple Configurator with Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator with direct enrollment](apple-configurator-direct-enroll-ios.md), or [device enrollment program](device-enrollment-program-enroll-ios.md). 

## Example of a device enrollment manager scenario

A restaurant wants to provide 50 point-of-sale tablets for its wait staff, and order monitors for its kitchen staff. The employees never need to access company data or sign in as users. The Intune admin creates a device enrollment manager account and adds a restaurant supervisor to the DEM account, in effect giving that supervisor DEM capabilities. The supervisor can now enroll the 50 tablets devices by using the DEM credentials.

Only users in the Intune console can be device enrollment managers. The device enrollment manager user cannot be an Intune admin.

The DEM user can:

-   Enroll up to 1000 devices in Intune.
-   Sign in to the Company Portal to get company apps.
-   Configure access to company data by deploying role-specific apps to the tablets.

## Limitations of devices that are enrolled with a DEM account

Devices that are enrolled with a device enrollment manager account have the following limitations:

  - There is no specific device "user." Therefore, there is no email or company data access. However VPN, for example, could still be used to provide device apps with access to data.

  - There is no conditional access because these are per-user scenarios.

  - The DEM user can't unenroll DEM-enrolled devices on the device itself by using the Company Portal. The Intune admin has this capability, but the DEM user does not.

  - Only the local device appears in the Company Portal app or website.
 
  - Users can't use Apple Volume Purchase Program (VPP) apps because of per-user Apple ID requirements for app management.
 
  - (iOS only) If you use DEM to enroll iOS devices, you can't use the Apple Configurator or Apple Device Enrollment Program (DEP) to enroll devices.


> [!NOTE]
> To deploy company apps to devices that are managed by the device enrollment manager, deploy the Company Portal app as a **Required Install** to the device enrollment manager's user account.
> To improve performance, viewing the Company Portal app on a DEM device shows only the local device. Remote management of other DEM devices can only be done from the Intune admin console.


## Add a device enrollment manager

1.  In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2.  On the Intune blade, choose **Enroll devices**, and then choose **Device Enrollment Managers**.

3.  Select **Add**.

4.  On the **Add User** blade, enter a user principal name for the DEM user, and select **Add**. The DEM user is added to the list of DEM users.

## Remove a device enrollment manager

Removing a device enrollment manager does not affect enrolled devices. When a device enrollment manager is removed:

-   Removing a user from the list of DEM users does not affected enrolled devices, and the enrolled devices continue to be fully managed.

-   The removed device enrollment manager account credentials remain valid.

-   The removed device enrollment manager still cannot wipe or retire devices.

-   The removed device enrollment manager cannot enroll additional devices unless the per-device limit, configured by the Intune admin, has not been reached.

**To remove a device enrollment manager**

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Device Enrollment Managers**.

3. On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Remove**.

## View the properties of a device enrollment manager

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Device Enrollment Managers**.

3. On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Properties**.
