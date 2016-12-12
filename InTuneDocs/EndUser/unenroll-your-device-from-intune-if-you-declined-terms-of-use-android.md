---
# required metadata

title: Unenroll your device from Intune if you declined "Terms of Use" | Microsoft Docs
description: Describes how to unenroll an Android device from Intune if you declined the terms of use and cannot sign in to the Company Portal app
keywords:
author: barlanmsftms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Unenroll your device from Intune if you declined "Terms of Use"

The best way to unenroll your Android device is to accept the terms of use, sign in to the Company Portal app, and then use [these instructions](unenroll-your-device-from-intune-android.md) to unenroll. However, if you declined the terms of use while trying to sign in to the Company Portal app, you are prevented from signing in to the Company Portal app on future tries, so you need to use these "workaround" instructions to unenroll your device.

When you uninstall the Company Portal app, you are also unenrolling your device from Intune. Your device will no longer be able to access company resources. For more about what happens when you unenroll, see [What happens if you unenroll your device from Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Before you can uninstall the Company Portal app, you have to go to the **Device administrators** setting, and turn off **Company Portal**. The steps may differ a little, depending on which Android device you have.

To unenroll your device from Intune and uninstall the Company Portal app:

1.  Go to **Settings** &gt; **Security &amp; Screen Lock** &gt; **Device administrators**.

    Completing this step immediately unenrolls your device.

2.  Uncheck the box next to, or turn off, **Company Portal**.

    You can now uninstall the Company Portal app.

Still need help? Contact your IT admin (check the [Company Portal website](http://portal.manage.microsoft.com) for contact information), or write the [Microsoft Android team](mailto:wintunedroidfbk@microsoft.com).
