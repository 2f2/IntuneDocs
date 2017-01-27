---
# required metadata

title: Set up Windows device management with Microsoft Intune | Microsoft Docs
description: Enable mobile device management (MDM) for Windows PCs including Windows 10 devices with Microsoft Intune.
keywords:
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Set up Windows device management

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As an Intune admin, you can enable enrollment and management for Windows PCs in two ways:

- **[Automatic enrollment with Azure Active Directory](#azure-active-directory-enrollment)** -  Windows 10 and Window 10 Mobile users enroll their devices by adding a work or school account to the device.

- **[Company Portal enrollment](#set-up-company-portal-app-enrollment)** - Windows 8.1 and later users enroll their devices by downloading and installing the Company Portal app and then entering their work or school account credentials in the app.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Set up Company Portal app enrollment
You can let users install and enroll their devices by using the Intune Company Portal app. If you create DNS CNAME resource records,  users connect and enroll in Intune without entering a server name.

1. **Set up Intune**<br>
If you haven’t already, prepare for mobile device management by  [setting the mobile device management (MDM) authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and then setting up MDM.

2. **Create CNAMEs** (optional)<br>Create **CNAME** DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment-s.manage.microsoft.com.

    Although creating CNAME DNS entries is optional, CNAME records make enrollment easier for users. If no enrollment CNAME record is found, users are prompted to manually enter the MDM server name, manage.microsoft.com.	

    If you currently have a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com, we suggest that you replace it with a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment-s.manage.microsoft.com. This change is recommended, because the manage.microsoft.com endpoint is being deprecated for enrollments in a future release.

	CNAME resource records must have the following information:

  |TYPE|Host name|Points to|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Hour|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Hour|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

  `EnterpriseRegistration.windows.net` – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory by using their work or school account

  If your company uses multiple domains for user credentials, create CNAME records for each domain.

  For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to EnterpriseEnrollment-s.manage.microsoft.com. Changes to DNS records might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

3.  **Verify CNAME**<br>In the [Intune administration console](http://manage.microsoft.com), choose **Admin** &gt; **Mobile Device Management** &gt; **Windows**. Enter the URL of the verified domain of the company website in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.

4.  **Tell your users how to enroll their devices and what to expect after they're brought into management.**

	For end-user enrollment instructions, see [Enroll your Windows device in Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

	For more information about end-user tasks, see [Resources about the end-user experience with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### See also
[Prerequisites for enrolling devices in Microsoft Intune](prerequisites-for-enrollment.md)
