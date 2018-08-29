---
# required metadata

title: Enroll your organization-provided macOS device in management | Microsoft Docs
description: Describes how to enroll an macOS device in Intune that was purchased and provided by your organization.
keywords:
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 
searchScope:
 - User help

# optional metadata

ROBOTS:  
#audience:
#ms.devlang:
ms.reviewer: japoehlm
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---  

# Enroll your organization-provided macOS device in management

Learn how to get your new macOS device managed in Intune.  

Devices that are provided by your work or school are often preconfigured before you receive them. Your organization will send these preconfigured settings to your device after you turn it on and sign in for the first time. After your device completes setup, you'll receive access to your work or school resources. 

To begin management setup, power on your device and sign in with your work or school credentials. The rest of this article describes the steps and screens you'll see as you walk through Setup Assistant.   

## What is Apple DEP?
Your organization might have purchased their devices through something called the *Apple Device Enrollment Program* (DEP). Apple DEP lets organizations buy large amounts of iOS or macOS devices. Organizations can then configure and manage those devices within their preferred mobile device management provider, such as Intune. If you're an administrator and want more information about Apple DEP, see [Automatically enroll macOS devices with Apple's Device Enrollment Program](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## Set up your macOS device  
Complete the following steps to enroll your macOS device in management. If you're using your own device, rather than an org-provided device, follow the steps for [personal and bring-your-own devices](enroll-your-device-in-intune-macos-cp.md).  

1. Power on your macOS device. 
2. Choose your **Language** and click **Continue**.  

   ![Screenshot of macOS device Setup Assistant Welcome screen, showing a list of languages to select from.](./media/macos-dep-welcome-1808.png)   
3. Choose a keyboard layout. The list shows one or more options based off your selected language. To see all layout options, regardless of your selected language, click **Show All**. When you're done, click **Continue.**  

   ![Screenshot of macOS device Setup Assistant Keyboard Layout screen, showing a list of keyboard languages to select from, an unchecked Show All option, and a Back and Continue button.](./media/macos-dep-keyboard-1808.png)  
4. Select your Wi-Fi network. You must have an internet connection to continue setup. If you do not see your network, or if you need to connect over a wired network, click **Other Network Options**. When you're done, click **Continue**.  

   ![Screenshot of macOS device Setup Assistant Select Your Wi-Fi Network screen, showing a list of available networks to choose from. Also shows an Other Network Options button, Back button, and Continue button.](./media/macos-dep-wifi-1808.png)  
5. After you're connected to Wi-Fi, the **Remote Management** screen appears. Remote management enables your organization's administrator to remotely configure your device with company-required accounts, settings, apps, and networks. Before proceeding, read over the documentation to help you understand how your device is managed. Then click **Continue**.  

   ![Screenshot of macOS device Setup Assistant Remote Management screen, with text explaining remote management and a link to documentation for more information. Also shows a Back button and Continue button.](./media/macos-dep-remote-management-1-1808.png)  
6. When prompted, sign in with your work or school account. After your authenticated, your device will install a management profile. The profile configures and enables your access to your organization's resources.  
7. Read about the Apple data & privacy icon so that you can later identify when personal information is being collected. Then click **Continue**.  

   ![Screenshot of macOS device Setup Assistant Data & Privacy screen, showing an illustration of two people shaking hands, and describing Apple's use of personal information. Also shows a Back and Continue button.](./media/macos-dep-apple-data-privacy-1808.png)  
8. After your device is enrolled, you might have additional steps to complete. The steps you see depend on how your organization customized the setup experience. It could require you to:
    * Sign in to an Apple account
    * Agree to the Terms and conditions
    * Create a computer account
    * Walk through an express setup
    * Set up your Mac  
## Get the Company Portal app      
Go to the App Store to get the Intune Company Portal app on your device. The app lets you monitor, sync, add, and remove your device from management, and install apps.

Still need help? Contact your company support. For contact information, check the [Company Portal website](https://go.microsoft.com/fwlink/?linkid=2010980).
