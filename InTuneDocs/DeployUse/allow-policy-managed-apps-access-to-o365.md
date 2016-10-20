---
# required metadata

title: App based conditional access to 0365 | Microsoft Intune
description: Understand the concepts of how MAM CA can help with controlling what apps have access to O365 services.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Allow only mobile apps that support Intune MAM policies to access Office 365 services
[Intune mobile app management (MAM) policies](protect-apps-and-data-with-microsoft-intune.md) help protect your company data on devices that are enrolled for management in Intune. You can also use MAM policies on **employee owned devices that are not enrolled for management in Intune**.  In this case, even though you don't manage the device, you still need to make sure that your company data and resources is protected. Using conditional access for MAM (MAM CA), you can create a policy that allows only mobile apps that support Intune MAM policies to access O365 services like Exchange Online.

For example, by only allowing the **Microsoft Outlook app** to access Exchange Online, you can **block the built-in mail apps on iOS and Android**, which don't have the data protection from Intune MAM policies to get email from **Exchange Online**.

## Prerequisites
**Before** you can configure MAM CA policy you must have an **Enterprise Mobility + Security or an Azure Active Directory premium subscription**, and the users must be licensed for EMS or Azure AD. For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Supported apps
**Exchange Online**
* Microsoft Outlook for Android and iOS


## What to expect when using an app with MAM CA
MAM CA verifies the identity of the approved application by means of a broker app that must be present on the device:
*  On **iOS**, the **Azure Authenticator app** is the broker app.
* On **Android**, the **Intune Company Portal app** is the broker app. 

End-users signing in for the first time, to an app that is supported by MAM CA, like OneDrive or Outlook, are prompted to install the broker app and register the device with Azure AD. Device registration in Azure AD (previously known as Workplace Join) will create a device record and certificate against which tokens are issued.  This is **not** the same as **MDM enrollment**. There are no management profiles or policies that are applied, and there is no inventory taken of apps on the device.  The process of installing the broker app and registering the device will only happen on the first use of a managed app.
## MAM CA with Azure Active Directory certificate based authentication

MAM CA must not be used with Azure Active Directory (Azure AD) certificate based authentication. You can only have one of these configured at a time.


## Next steps
[Create an Exchange Online Policy for MAM apps](mam-ca-for-exchange-online.md)

[Block apps that do not have modern authentication](block-apps-with-no-modern-authentication.md)

### See also

[Protect app data with MAM policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
