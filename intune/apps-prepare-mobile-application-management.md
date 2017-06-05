---
# required metadata

title: Decide how to prepare apps for mobile application management with Microsoft Intune | Microsoft Docs
description: The information in this topic helps you decide when you should use the App wrapping tool and the App SDK to enable your custom line-of-business apps to use the mobile app management policies.
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: oldang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Prepare line of business apps for MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

You can enable your apps to use mobile application management (MAM) policies by using either the Intune App Wrapping Tool or the Intune App SDK. Use this information to learn about these two methods and when to use them.

## Intune App Wrapping Tool
The App Wrapping Tool is used primarily for internal line-of-business (LOB) apps. The tool is a command line application that creates a wrapper around the app, which then allows the app to be managed by an Intune MAM policy.

You don't need the source code to use the tool, but you do need signing credentials.  For more about signing credentials, see the [Intune blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). For the App Wrapping Tool documentation, see [Android App Wrapping Tool ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) and [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

The App Wrapping Tool does **not** support apps in the Apple App Store or Google Play Store. It also doesn't support certain features that require developer integration (see the following feature comparison table).


For more information about the App Wrapping Tool for MAM on devices that are not enrolled in Intune, see [Protect line of business apps and data on devices not enrolled in Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

### Reasons to use the App Wrapping Tool:
* Your app does not have built-in data protection features.
* Your app is simple.
* Your app is deployed internally.
* You don't have access to the app's source code
* You didn't develop the app.
* Your app has minimal user authentication experiences.


### Supported app development platforms

|**App Wrapping Tool** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Yes|Yes|
|**Android**| No |Yes|

## Intune App SDK
The App SDK is designed mainly for customers who have apps in the Apple App Store or Google Play Store, and want to be able to manage the apps with Intune. However, any app can take advantage of integrating the SDK, even line-of-business apps.

To learn more about the SDK, see the [Overview](../develop/intune-app-sdk.md). To get started with the SDK, see [Getting Started With the Microsoft Intune App SDK](../develop/intune-app-sdk-get-started.md).

### Reasons to use the SDK
* Your app does not have built-in data protection features.
* Your app is complex and contains many experiences.
* Your app is deployed on a public app store such as Google Play or Apple's App Store.
* You are an app developer and have the technical background to use the SDK.
* Your app has other SDK integrations.
* Your app is frequently updated.

### Supported app development platforms

|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Yes – use the [Intune App SDK Xamarin Component](../develop/intune-app-sdk-xamarin.md).|Yes – use the [Intune App SDK Cordova Plugin](../develop/intune-app-sdk-cordova.md).|
|**Android**| Yes - use the [Intune App SDK Xamarin Component](../develop/intune-app-sdk-xamarin.md).|Yes – use the [Intune App SDK Cordova Plugin](../develop/intune-app-sdk-cordova.md).|

## Feature comparison
This table lists the settings that you can use for the App SDK and App Wrapping Tool.

> [!NOTE]
> The App Wrapping Tool can be used with Intune standalone or Intune with Configuration Manager.

|Feature|App SDK|App Wrapping Tool|
|-----------|---------------------|-----------|
|Restrict web content to display in a corporate managed browser|X|X|
|Prevent Android, iTunes or iCloud backups|X|X|
|Allow app to transfer data to other apps|X|X|
|Allow app to receive data from other apps|X|X|
|Restrict cut, copy and paste with other apps|X|X|
|Require simple PIN for access|X|X|
|Replace built-in app PIN with Intune PIN|X||
|Specify the number of attempts before PIN reset|X|X|
|Allow fingerprint instead of PIN |X|X|
|Require corporate credentials for access|X|X|
|Block managed apps from running on jailbroken or rooted devices|X|X|
|Encrypt app data|X|X|
|Recheck the access requirements after a specified number of minutes|X|X|
|Specify the offline grace period|X|X|
|Block screen capture (Android only)|X|X|
|Full Wipe|X|X|
|Selective Wipe <br></br>**Note:** For iOS, when the management profile is removed, the app is also removed.|X||
|Prevent “Save as” |X||
|Support for Multi-Identity|X||
|Support for MAM without device enrollment|X|X|
|Customizable Style |X|||
### See also

[Android app wrapping tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS app wrapping tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Use the SDK to enable apps for mobile application management](use-the-sdk-to-enable-apps-for-mobile-application-management.md)
