---
# required metadata

title: Intune PC software client capabilities | Microsoft Docs
description: Learn about the capabilities of Intune when you manage Windows PCs with the Intune software client.
keywords:
author: robstackmsftms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows PC management capabilities when you use the Intune software client
In most scenarios, you will enroll your devices with Microsoft Intune, which provides a greater set of capabilities. However, you can also manage PCs by using the Intune software client, which provides the following features:

-   **[Software update management](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** - You can keep PCs up to date and decide when updates are applied.

-   **[Windows Firewall policy](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** - This helps to ensure that no PC that's used in your company has an inactive or improperly-configured Windows Firewall.

-   **[Anti-malware protection](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** - Intune includes Endpoint Protection, which helps protect your PCs from malware.

-   **[Remote assistance](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** - Intune lets users contact IT support staff, who can then provide assistance by using a remote desktop feature that is included with Intune (requires TeamViewer software).

-   **[Software license management](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** - Track how many software licenses are available, and how many available licenses are being used.
-   **[App deployment](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** - Deploy software to PCs that you manage. Some app management features are not available when you manage PCs with the software client.


Intune supports installing the software client on up to 7,000 Windows devices.

## Operating system requirements
Intune can manage PCs that are running the following Windows versions (both 32-bit and 64-bit):


-   **Windows Vista** - Business, Enterprise, and Ultimate versions

-   **Windows 7** - Pro, Enterprise, and Ultimate versions (with no service pack, or with SP1)

-   **Windows 8** - Pro and Enterprise versions

-   **Windows 8.1** - Pro and Enterprise versions

- **Windows 10** - Pro, Education, and Enterprise versions


## Minimum hardware requirements
Following are the minimum hardware requirements for installing the Intune software client:

|Requirement|Details|
|---------------|--------------------|
|Network|The client requires the PC to have Internet connectivity.|
|Processor and memory|Refer to the processor and RAM requirements for the PC's operating system.|
|Disk space|200 MB available disk space before the client software is installed.|

## Further requirements
Following are the software requirements for installing the Intune software client:

|Requirement|Details|
|---------------|--------------------|
|Administrative permissions|The account that installs the client software must have local administrator permissions for that PC.|
|Windows Installer 3.1|The PC must have, at a minimum, Windows Installer 3.1.|
|Remove incompatible client software|Before you install the Intune PC client software, you must uninstall the following client software from that PC:<br /><br />-   Any version of Configuration Manager<br />-   Any version of Microsoft Systems Management Server (SMS)|

### See also
[Enrolled device management capabilities of Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)
