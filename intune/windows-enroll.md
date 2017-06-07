---
# required metadata

title: Enroll Windows devices
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Enable Intune mobile device management (MDM) for Windows devices."
keywords:
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enroll Windows devices

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

This topic helps IT administrators simplify Windows enrollment for their users.  Windows devices can be enrolled without any additional steps, but you can make enrollment easier for users.

Devices that run the Windows 10 Creators Update, and are Azure Active Directory domain-joined, are now supported for multi-user management by Intune. This means that when different standard users log onto the device with their Azure AD credentials, they will receive any apps and policies that were assigned to their user name. Users cannot currently use the Company Portal for self-service scenarios like installing apps.

Two factors determine how you can simplify Windows device  enrollment:

- **Do you use Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) is included with Enterprise Mobility + Security and other licensing plans.
- **What versions of Windows clients will enroll?** <br>Windows 10 devices can automatically enroll by adding a work or school account. Earlier versions must enroll using the Company Portal app.

||**Azure AD Premium**|**Other AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatic enrollment](#enable-windows-10-automatic-enrollment) |[User enrollment](#enable-windows-enrollment-without-azure-ad-premium)|
|**Earlier Windows versions**|[User enrollment](#enable-windows-enrollment-without-azure-ad-premium)|[User enrollment](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## Enable Windows enrollment without Azure AD Premium
You can let users enroll their devices without Azure AD Premium automatic enrollment. Once you assign licenses, users can enroll after adding their work account to their personally-owned devices or joining their corporate-owned devices to your Azure AD. Creating a DNS alias (CNAME record type) makes it easier for users to enroll their devices. If you create DNS CNAME resource records, users connect and enroll in Intune without having to enter the Intune server name.

**Step 1: Create CNAME** (optional)<br>
Create CNAME DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment-s.manage.microsoft.com.

Although creating CNAME DNS entries is optional, CNAME records make enrollment easier for users. If no enrollment CNAME record is found, users are prompted to manually enter the MDM server name, enrollment.manage.microsoft.com.

|Type|Host name|Points to|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hour|

If you have more than one UPN suffix, you need to create one CNAME for each domain name and point each one to EnterpriseEnrollment-s.manage.microsoft.com. For example, if users at Contoso use name@contoso.com, but also use name@us.contoso.com, and name@eu.constoso.com as their email/UPN, the Contoso DNS admin would need to create the following CNAMEs.

|Type|Host name|Points to|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hour|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hour|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hour|

`EnterpriseEnrollment-s.manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

Changes to DNS records might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

**Step 2: Verify CNAME** (optional)<br>
In the Azure Intune portal, choose **More Services** > **Monitoring + Management** > **Intune**. On the Intune blade, choose **Enroll devices** > **Windows Enrollment**. Enter the URL of the verified domain of the company website in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.

## Tell users how to enroll Windows devices
Tell your users how to enroll their Windows devices and what to expect after they're brought into management. For end-user enrollment instructions, see [Enroll your Windows device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). You can also tell users [What can my IT admin see on my device](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

For more information about end-user tasks, see [Resources about the end-user experience with Microsoft Intune](end-user-educate.md).
