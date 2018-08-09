---
# required metadata

title: Reset Windows 10 devices with Microsoft Intune - Azure | Microsoft Docs
description: Use Fresh Start to remove or uninstall apps on Windows 10 PCs by using Microsoft Intune. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/09/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use Fresh Start to reset Windows 10 devices with Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

The **Fresh Start** device action removes any apps that are installed on a Windows 10 PC that is running the Creators Update. Then it automatically updates the PC to the latest version of Windows. Fresh Start helps remove pre-installed (OEM) apps that are typically installed with a new PC.  

1. Sign in to the [Azure portal](https://portal.azure.com) and go to > **Microsoft Intune** > **Devices** > **All devices**.
2. From the list of devices you manage, choose a Windows 10 desktop device.
3. Click **Fresh Start**. 
4. Select **Retain user data on this device** to:
   * Keep the device Azure AD joined
    * Keep the device enrolled in mobile device management 
    * Keep the contents of the device user's Home folder, and only remove apps and settings  
  > [!IMPORTANT]
 > If you do not retain user data, the device will be restored to its out-of-box state. It will be unenrolled from Azure AD and mobile 
 > device management. 
 
5. Click **OK**.   
6. To see the status of this action, go back to **Devices** and click **Device actions**.  
