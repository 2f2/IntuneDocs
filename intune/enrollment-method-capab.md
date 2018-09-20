---
# required metadata

title: Intune capabilities by enrollment method
titlesuffix: Microsoft Intune
description: See which capabilities each enrollment method supports.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Capabilities by enrollment method
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune lets you manage your workforce’s devices and apps and how they access your company data. The devices must first be enrolled in the Intune service. There are several methods to enroll your workforce’s devices. Each method has different best practices and capabilities, as shown in the tables below.

## Best practices by enrollment method
| **Best practices** | **[Azure AD joined](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD joined with Autopilot](enrollment-autopilot.md)** |**[Bulk](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **GPO** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Commonly used in EDU|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Devices can be used as shared devices|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Personal devices must access company resources|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|
|Self-servicing of apps|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|

## Capabilities by enrollment method

| **Capabilities** | **[Azure AD joined](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD joined with Autopilot](enrollment-autopilot.md)** |**[Bulk](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **GPO** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Conditional access                                      |![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|
|User gets associated with the device                    |![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|
|Requires Azure AD Premium                               |![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|
|Device can assess resources protected by CA             |![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|
|Users must not be admins on their devices               |![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Ability to configure the device setup experience        |![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Ability to enroll devices without user interaction      |![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|
|Ability to run PowerShell scripts                       |![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Supports automatic enrollment after AD domain join      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|
|Supports automatic enrollment after Hybrid Azure AD join|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Checkmark](media/checkmark.png)|
|Supports automatic enrollment after Azure AD join       |![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![Checkmark](media/checkmark.png)|![X](media/xmark.png)|

## Next steps

[Enrollment options](enrollment-options.md)

