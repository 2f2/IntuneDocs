---
# required metadata

title: How to remove your Android device from Intune | Microsoft Docs
description: Describes how to unenroll an Android device from Intune
keywords:
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
 - User help

# optional metadata

ROBOTS:   
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---  

# Unenroll your Android device from management  

Remove an enrolled Android device so that it's no longer managed by your organization. This article describes how to remove the device from the Company Portal app. After you remove the device:  

* The device loses access to your organization's protected data and resources.
* The device no longer appears in Company Portal.
* You can’t install apps from Company Portal.
* Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.  

1. In Company Portal, go to the top-right corner and tap the three vertical dots. The action menu opens.

   ![An image of the Android Company Portal app, with the action menu opened in the top right corner. The new "remove company portal" option is available as the third option, underneath "my profile" and "settings", and above "terms and conditions", "help and feedback", and "about".](./media/android_remove_cp_menu_action_after_1705.png)

2. Tap **Remove Company Portal**.  

3. A message appears with information about what happens after you unenroll your device. Tap **OK** to confirm that you want to remove the device from Company Portal.

   ![An image of the confirmation dialog, that is available after selecting the new "remove company portal" option from the action menu. The dialog informs the user that "by removing company portal, your device will no longer be managed by your company support and may remove access to company data, company apps, and company email." It then asks the user to confirm that they want to remove the Company Portal app by selecting "Yes".](./media/android_remove_cp_menu_confirmation_after_1705.png)

## Removing data collected by the Company Portal app  

To remove all data that the Company Portal app for Android stores on your device:

-	Clear app data in Applications -> Click on app -> button "Clear data"
-	Delete the folder '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal'

## Uninstall the Company Portal app  
Company Portal is a device management app, so it can't be uninstalled until you [unenroll your device from its management](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). After that's complete, tap and hold the Company Portal app icon until you see **Uninstall**. Tap **Uninstall** to remove the app from your device.  

Alternatively, tap **Settings** > **Apps** > **Compay Portal** > **Uninstall**.  

Still need help? Contact your company support. For contact information, check the [Company Portal website](https://go.microsoft.com/fwlink/?linkid=2010980)
