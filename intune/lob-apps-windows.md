---
# required metadata

title: How to add Windows line-of-business apps to Intune | Microsoft Docs
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn about adding Windows line-of-business apps to Intune."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/01/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Windows line-of-business (LOB) apps to Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


## Step 1 - Specify the software setup file

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **Line-of-business app**.

## Step 2 - Configure the app package file

1. On the **Add app** blade, choose **App package** file.
2. On the **App package** file blade, choose the browse button, and select a Windows installation file with the extension **.msi** (other installation file types are not supported).
3. When you are finished, choose **OK**.


## Step 3 - Configure app information

1. On the **Add app** blade, choose **App package** file.
2. On the **App information** blade, configure the following information. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **Name** - Enter the name of the app as it will be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **Description** - Enter a description for the app. This will be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Category** - Select one or more of the built-in app categories, or a category you created. This will make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
	- **Command-line arguments** - Optionally, enter any command line arguments that you want to apply to the .msi file when it runs, like **/q**.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Logo** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.
3. When you are finished, choose **OK**.

## Step 4 - Finish up

1. On the **Add app** blade, verify the information you configured is correct.
2. Choose **Add**, to upload the app to Intune.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).
