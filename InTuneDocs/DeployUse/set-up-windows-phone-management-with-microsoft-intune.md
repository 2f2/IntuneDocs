---
# required metadata

title: Set up Windows 10 Mobile and Windows Phone management | Microsoft Intune
description: Enable mobile device management (MDM) for Windows 10 Mobile or Windows Phone devices with Microsoft Intune.
keywords:
author: staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Set up Windows Phone and Windows 10 Mobile management with Microsoft Intune

As an Intune admin, you can enable enrollment and management for Windows 10 Mobile and Windows Phone devices in two ways:

- **[Automatic enrollment with Azure Active Directory](#azure-active-directory-enrollment)** -  Windows 10 and Window 10 Mobile users enroll their devices by adding a work or school account to the device
- **[Company Portal enrollment](#company-portal-app-enrollment)** - Windows Phone 8.1 and later users enroll their devices by downloading and installing the Company Portal app and then entering their work or school account credentials in the app.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Company Portal app enrollment
You can let users install and enroll their devices by using the Intune Company Portal app. If you create DNS CNAME resource records, users connect and enroll in Intune without entering a server name.

1.  **Set up Intune**<br>If you haven’t already, prepare for mobile device management by  [setting the mobile device management (MDM) authority](prerequisites-for-enrollment.md#set-mobile-device-management-authority) as **Microsoft Intune** and then setting up MDM.

2.  **Create CNAMEs** (optional)<br>Create **CNAME** DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com. If there is more than one verified domain, create a CNAME record for each domain. The CNAME resource records must contain the following information:

  |TYPE|Host name|Points to|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Hour|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Hour|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

  `EnterpriseRegistration.windows.net` – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory by using their work or school account

  If your company uses multiple domains for user credentials, create CNAME records for each domain.

  For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to EnterpriseEnrollment-s.manage.microsoft.com. Changes to DNS records might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

3.  **Verify CNAME**<br>In the [Intune administration console](http://manage.microsoft.com), choose **Administration** &gt; **Mobile Device Management** &gt; **Windows Phone**. Enter the URL of the verified domain of the company website in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.

    ![Set up mobile device management for Windows dialog box](../media/windows-phone-enrollment.png)

4.  **Optional steps**<br>The **Add Sideloading keys** step is not needed for Windows 10. The **Upload Code-Signing Certificate** step is only needed if you will distribute line-of-business (LOB) apps that are not available from the Windows Store to devices.

5.  **Tell your users how to enroll their devices to get access to company resources.**

	For end-user enrollment instructions, see [Enroll your Windows device in Intune](../enduser/enroll-your-device-in-intune-windows.md). You can also send users to [What can your IT administrator see when you enroll your device in Intune?](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

	For information about other end-user tasks, see these articles:
    - [What to tell your end users about using Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [End user guidance for Windows devices](../enduser/using-your-windows-device-with-intune.md)

No additional work is required unless you will deploy the Company Portal to devices.  Steps 2 and 3 in the admin console can be safely ignored.
