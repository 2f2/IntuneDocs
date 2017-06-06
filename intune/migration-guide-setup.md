---
# required metadata

title: Intune basic setup | Microsoft Docs
description: The purpose of this article is to provide the necessary steps to set up Microsoft Intune.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Phase 1: Basic setup

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

After you assessed your environment, it’s time to setup Intune.

## External dependencies for an Intune deployment

### Identity

Intune requires Azure Active Directory (AAD) as the identity and user grouping provider.

-   Learn more about [identity requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Learn more about [directory synchronization requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Learn more about [multi-factor authentication requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Learn more about [planning your user and device groups](/intune-classic/deploy-use/plan-your-user-and-device-groups).

-   Learn [how to create user and device groups](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

If your organization is already using Office 365, it’s important that Intune uses the same Azure Active Directory environment.

### PKI (optional)

If you're planning to use certificate-based authentication for VPN, Wi-Fi, or e-mail profiles with Intune, you’ll need to make sure that you have a supported [PKI infrastructure in place](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles), ready to create and deploy certificate profiles.

More information about configuring certificates in Intune is below.

-   [How to configure the certificate infrastructure for SCEP](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep).

-   [How to configure the certificate infrastructure for PFX](/intune-classic/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [How to configure Intune certificate profiles](/intune-classic/deploy-use/configure-intune-certificate-profiles).

-   [How to configure resource access policies](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## Task list for an Intune Setup

### Task 1: Intune subscription

Before you can migrate to Intune, you first need an Intune subscription.

-   You can visit [this page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), which gives you instructions on how to:

    -   Create a new Intune subscription linked to a new AAD tenant.

    -   Link the Intune subscription by signing into an existing AAD tenant.

### Task 2: Assign Intune user licenses

-   Learn [how to assign Intune user licenses](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

-   If you have created a new Azure Active Directory tenant, learn [how to create new users or sync user from your on-premises Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### Task 3: Set your MDM authority to Intune

Intune can be managed through the Azure Portal or the Configuration Manager Current Branch console. Unless you need to integrate Intune with a Configuration Manager Current Branch deployment, it is recommended to manage Intune from the [Azure Portal](https://portal.azure.com).

Set your MDM authority to **Intune** to enable the Intune Azure Portal. Using a different MDM authority allows Intune to transfer MDM management to alternate Microsoft management consoles. These cases are uncommon.

> [!IMPORTANT]
> If you are transferring your mobile device management to Intune for the first time, you should set the MDM authority to Intune.

-   Learn [how to set the mobile management authority](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

## Next step

[Phase 1: Configure device and app management policies](/intune-classic/plan-design/migration-phase1-configure-device-and-app-management-policies)
