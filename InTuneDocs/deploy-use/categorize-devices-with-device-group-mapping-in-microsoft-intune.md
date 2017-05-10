---
# required metadata

title: Categorize devices with device group mapping | Microsoft Docs
description: Use Microsoft Intune device group mapping to group devices into categories that you define, in order to make it easier for you to manage those devices. 
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Categorize devices with device group mapping in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use Microsoft Intune **device group mapping** to automatically add devices to groups based on categories that you define, in order to make it easier for you to manage those devices. 

Device group mapping uses the following workflow:
1. Create categories that users will choose from when they enroll their device
2. You create groups, or use existing groups for each category you want to use. Depending on the version of Intune you are using, these will either be Intune groups, or Azure Active Directory security groups.
2. You configure rules that map the category you choose to the device group you created.
3. When end users enroll their device, they must choose a category from the list of categories you configured. After they choose, their device is automatically added to the corresponding group you created. If a device is already enrolled, the end user will be asked to select a category the next time they access the Company Portal app.
4. You can then deploy policies and apps to these groups.

You can create any device categories you want, for example:
* Point of sale device
* Demonstration device
* Sales
* Accounting
* Manager

## Important information about a change in group management for Intune

Based on your feedback, we are in the process of unifying the grouping and targeting experience across Enterprise Mobility + Security. For this reason, we will soon be converting Intune groups to Azure Active Directory-based security groups. After this change, you will no longer create groups using Intune. Instead, you'll create them in the Azure portal. This change will happen on a gradual basis and you can read full details about this change, and its timeline in [this topic](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### Which procedure in this topic should you use to configure device group mapping?

Due to the phased implementation of Azure Active Directory-based security groups, you must open the **Groups** workspace in the [Intune administration console](https://manage.microsoft.com) to identify which procedure to use:

-  If you see a link to the Azure portal, then you are no longer using Intune groups. Follow the [How to configure device group mapping for Azure Active Directory groups]/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) procedure below.
-  If you do not see a link to the Azure portal, then you are still using Intune groups. Follow the [How to configure device group mapping for Intune groups]/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) procedure below.

## How to configure device group mapping for Intune groups
1. For each device category you want to use, create an Intune device group, or identify an existing group. For information about how to create groups, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.
3. In the **Administration** workspace, expand **Mobile Device Management**, and then choose **Device Group Mapping**.
4. On the **Device Group Mapping** page, enable device group mapping.
5. Choose **Add** to create a new mapping rule.
6. In the **Add device group mapping rule** dialog box, enter the name of the category you want to create and then, from the drop-down list, choose the device collection you want to map this category to. Choose **Add** when you are done.
7. When you have finished adding categories and groups, choose **Save**.



## How to configure device group mapping for Azure Active Directory groups

### Step 1 - Create device categories in the Intune administration console
1. In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.
3. In the **Administration** workspace, expand **Mobile Device Management**, and then choose **Device Categories**.
4. On the **Device Categories** page, you'll see a list where you can configure device categories: 
- You can enter a name, then click **Add**, to add it as a new device category.
- Additionally, you can select a category and then **Delete** it.

You'll use the device category name when you create Azure Active Directory security groups in step 2.

### Step 2 - Create Azure Active Directory security groups

In this step, you'll create dynamic groups in the Azure portal based on the device category and device category name.

To continue, refer to the topic [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure Active Directory documentation.
Use the information in this topic to create a device group with an advanced rule using the **deviceCategory** attribute.
For example (**device.deviceCategory -eq** "<*the device category name you got from the Intune administration console*>")


## After you configure device groups

When users enroll their device, they are presented with a list of the categories you configured. After they choose a category and finish enrollment, their device is added to the Intune device group, or Active Directory security group that corresponds with the category they chose.

### See also
[Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
