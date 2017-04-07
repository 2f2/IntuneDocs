---
# required metadata

title: Intune shared device configuration settings for iOS
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn the Intune settings you can use to display information on the iOS device lock screen."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Shared Device configuration settings to display messages on the iOS device lock screen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Shared device configuration settings let you specify optional text displayed on the login window and lock screen (For example, an "If Lost, Return to" message and Asset Tag Information). It is supported on supervised devices running iOS 9.3 and later.

1. On the **Device features** blade choose **Shared Device Configuration (supervised only)**.
2. On the **Shared Device Configuration (supervised only)** blade, configure the following:
	- **Asset tag information** - Enter information about the asset tag of the device. For example: **Contoso #12345**.
	- **Lock screen footnote** - Enter a note that might help get the device returned if it's lost or stolen. For example: **If found, please call 'number'**.
3. When you are finished, choose **OK** until you return to the **Create Profile** blade, then choose **Create**. 
