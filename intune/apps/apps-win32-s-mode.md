---
title: Enable Win32 apps on S mode devices
titleSuffix:
description: Learn how to enable Win32 apps on S mode devices using Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology:
ms.assetid: 

ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Enable Win32 apps on S mode devices

[Windows 10 S mode](https://docs.microsoft.com/windows/deployment/s-mode) is a locked-down operating system that only runs Store apps. By default, Windows S mode devices do not allow installation and execution of Win32 apps. These devices include a a single *Win 10S base policy*, which locks the S mode device from running any Win32 apps on it. However, by creating and using an **S mode supplemental policy** in Intune, you can install and run Win32 apps on Windows 10 S mode managed devices. By using the [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) PowerShell tools, you can create one or more supplemental policies for Windows S mode. You must sign the supplemental policies with the [Device Guard Signing Service (DGSS)](https://go.microsoft.com/fwlink/?linkid=2095629) or with [SignTool.exe](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/signing-policies-with-signtool) and then upload and distribute the policies via Intune. As an alternative, you can sign the supplemental policies with a codesigning certificate from your organization, however the prefered method is to use DGSS.

By assigning the S mode supplemental policy in Intune, you enable the device to make an exception to the device's existing S mode policy, which allows the uploaded corresponding signed app catalog. The policy sets an allow list of apps (the app catalog) that can be used on the S mode device.

<!-- Add WDAC tooling diagram  -->

The steps to allow Win32 apps to run on a Windows 10 device in S mode are the following:

1. Enable S mode devices through Intune
   - You can use the [Device Guard Signing Service (DGSS)](https://go.microsoft.com/fwlink/?linkid=2095629) to generate a root certificate for your organization and upload it to Intune. For more information, see the [Device Guide deployment guide](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
   - Intune will ensure this certificate is included in a device’s enable token from OCDUS, and any app catalogs which are signed with it will be able to run on the enabled device. Intune  will inspect all the uploaded supplemental policies for the highest intermediary cert included in the supplemental policy blob and include the hash of all these cert in OCDUS enable token.
2. Create a supplemental policy to allow Win32 apps
   - You can use [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) tools to create a supplemental policy. The base policy Id within the policy must match the S mode base policy Id (which is hard coded on the client)​. Also, make sure that the policy version is higher than the previous version.
   - You use DGSS to sign your supplemental policy. For more information, see [Sign code integrity policy with Device Guard signing](https://docs.microsoft.com/microsoft-store/sign-code-integrity-policy-with-device-guard-signing).
   - You upload the signed supplemental policy to Intune by creating a Windows 10 S mode supplemental policy (see below).
3. You allow Win32 app catalogs through Intune 
   - You create catalog files (1 for every app) and signs them using DGSS or other certificate infrastructure.
   - You submit the signed catalog to Intune.
   - Intune applies the signed catalog to enabled S mode device using [Intune Management Extension](~/apps/intune-management-extension.md).
   - S mode policies are enforced at the device level. Multiple targeted policies will be merged on the device. The merged policy is what will be applied.

> [!NOTE]
> Line-of-business (LOB) `.appx` and `.appx` bundles on Windows 10 S mode will be supported via Microsoft Store for Business (MSFB) signing.
>
> **S mode supplemental policy** for apps must be delivered via Intune Management Extension.

To create a Windows 10 S mode supplemental policy, use the following steps:

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. In the **Intune** pane, select **Client apps** > **S mode supplemental policies** > **Create policy**.
3. Before adding the **Policy file**, you must create and sign it. For more information, see:
    - [Create a WDAC policy using PowerShell tools and convert it to a binary format](https://go.microsoft.com/fwlink/?linkid=2095387)
    - [Sign using Device Guard Signing Service](https://go.microsoft.com/fwlink/?linkid=2095629) **(recommended)**<br>
      Or as an alternative, [Sign your policy with a trusted certificate](https://go.microsoft.com/fwlink/?linkid=2095541)

4. On the **Basics** page, add the following values:

    | Value | Description |
    |--------------|------------------------------------------------|
    | Policy file | The the file that contains the WDAC policy. |
    | Name | The name of this policy. |
    | Description | [Optional] The description of this policy. |

5. Click **Next: Scope tags**.<br>
   On the **Scope tags** page you can optionally configure scope tags to determine who can see the app policy in Intune. For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](.~/fundamentals/scope-tags.md).

6. Click **Next: Assignments**.<br>
   The **Assignments** page allows you can assign the policy to users and devices. It is important to note that you can assign a policy to a device whether or not the device is managed by Intune.
6. Click **Next: Review + create** to review the values you entered for the profile.
7. When you are done, click **Create** to create the S mode supplemental policy in Intune. 

Once the policy is created, you will see it added to the list of S mode supplemental policies in Intune. Once the policy is assigned, the policy gets deployed to the devices. Note that you must deploy the app to same security group as the supplemental policy​. After the devices have the policy, you can start targeting and assigning apps to those devices. This will allow your end users to install and execute the apps on those devices.

## Removal of S mode policy

Currently, to remove the policy from the device, you must assign and deploy an empty policy to overwrite the existing S mode supplemental policy.

## Policy Reporting​

The S mode supplemental policy, which is enforced at device level, only has device level reporting.​ Device level reporting is available for sucesss and error conditions. 

## Next steps

- For more information about adding apps to Intune, see [Add apps to Microsoft Intune](apps-add.md).
- For more information about Win32 apps, see [Intune Win32 app management](~/apps/apps-win32-app-management.md).
