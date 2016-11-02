---
# required metadata

title: Remotely lock a device from the Company Portal website | Microsoft Intune
description:
keywords:
author: barlanmsftms.author: barlan
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: adc6af23-b22f-42e5-955a-4dffbdb8b42b

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Remotely lock a device from the Company Portal website

If your device has been lost or stolen, you can lock the device by using the Remote Lock option on the [Company Portal website](http://portal.manage.microsoft.com). Remote Lock works for the following types of devices:

Platform  |Support details  
---------|---------
Android | Supported       
iOS | Supported
Windows 10 Mobile | Supported only if the phone has a passcode set     
Windows 10 Desktop | Not supported  
Windows Phone 8.1 | Supported only if the phone has a passcode set
PC (Windows 8.0 and earlier) | Not supported       
PC (Windows 8.1) | Not supported

</br>
To use Remote Lock to lock your device:

1.	On the [Company Portal website](http://portal.manage.microsoft.com), tap the name of the device you want to lock.

2.	Tap **Remote Lock**.

	![remote-lock-option-on-company-portal-website](./media/iwp-screen-with-all-options.png)

3.	Read the warning message, indicating that you are about to lock your device, and then tap **Remote Lock** to have the Company Portal website try to lock your device.

	Once you tap **Remote Lock**, a “Remote lock pending” status appears.  When Remote Lock succeeds, the status changes to “Remote lock successful.”

	The Remote Lock status displays in three places:

	* The notifications area of the website.
	* The Details page for the device.
	* The tile that shows the device name on the My Devices section of the page.

	If you see a “Remote Lock failed” notification, wait a few minutes, and then try again to lock your device. Once you tap to retry, the status changes back to “Remote lock pending.”

	If a retry doesn’t work, contact your IT administrator for help. If you find your device and want to unlock it after using Remote Lock, just enter your passcode.

Still need help? Contact your IT administrator. For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).

