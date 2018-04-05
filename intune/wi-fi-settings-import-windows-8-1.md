---
# required metadata

title: Import Wi-Fi settings for Windows 8.1 and later
titleSuffix: Microsoft Intune
description: How to import Wi-Fi settings from Windows into an Intune Wi-Fi profile.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Import Wi-Fi settings for Windows 8.1 and later devices in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

For devices that run Windows 8.1, Windows 10 desktop or mobile, or Windows Holographic for Business, you can import a Wi-Fi configuration profile that was previously exported to a file.

## Export Wi-Fi settings from a Windows device

In Windows, use the **netsh wlan** utility to export an existing Wi-Fi profile to an XML file readable by Intune. On a Windows computer that already has the required WiFi profile installed, follow this following procedure.
1. Create a local folder for the exported W-Fi- profiles, such as **c:\WiFi**.
1. Open up a Command Prompt as an administrator.
1. Run the command **netsh wlan show profiles**, and note the name of the profile you'd like to export. In this example, the profile name is **WiFiName**.
1. Run this command: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**.This creates a Wi-Fi profile file named **Wi-Fi-WiFiName.xml** in your target folder.

## Import the Wi-Fi settings into Intune

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Device configuration**.
4. On the **Device configuration** pane under the **Manage** section, choose **Profiles**.
5. On the profiles pane, click **Create profile**.
6. On the **Create profile** pane, enter a **Name** and **Description** for the device restriction profile.


   > [!WARNING]
   > The name **must** be the same as the name attribute in the Wi-Fi profile xml, otherwise it fails.

7. From the **Platform** drop-down list, choose **Windows 8.1 and later**.
8. From the **Profile type** drop-down list, choose **Wi-Fi import**.
9. On the **Wi-Fi** pane, configure the following settings:
	- **Connection name** Enter the name of the Wi-Fi connection. This name is displayed to end users when they browse available Wi-Fi networks.
	- **Profile XML** Click the browse button to select the XML file containing the Wi-Fi profile settings that you want to import into Intune.
	- **File contents** Displays the XML code for the configuration profile you selected.
10. When you're done, choose **OK**, go back to the **Create profile** pane, and select **Create**.

The profile is created and appears on the profiles list pane.
