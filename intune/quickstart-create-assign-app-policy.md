---
# required metadata

title: Quickstart - Create and assign an app protection policy
titlesuffix: Microsoft Intune
description: In this quickstart you will use Microsoft Intune to create an assign and app protection policy.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/08/2018
ms.topic: quickstart
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2586fce0-5dca-4686-b9c4-791778838401

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Quickstart: Create and assign an app protection policy

In this quickstart, you will use Intune to create an assign an app protection policy to a client app on an end user's device. Intune uses app protection policies to confirm that your apps are meeting your organization’s data protection requirements.

If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).

## Prerequisites

- To complete this quickstart, you must:
    - [Create a user](quickstart-create-user.md)
    - [Create a group](quickstart-create-group.md)
    - [Enroll a device](quickstart-setup-auto-enrollment.md)
    - [Add and assign an app](quickstart-add-assign-app.md)

## Sign in to Intune

Sign in to the [Intune](https://aka.ms/intuneportal) as a [Global administrator or an Intune Service administrator](users-add.md#types-of-administrators). If you have created an Intune Trial subscription, the account you created the subscription with is the Global administrator.

## Create an app protection policy

Use the following steps create an app protection policy:

1. In [Intune](https://aka.ms/intuneportal), select **Client apps** > **App protection policies** > **Create Policy**. 
2. Enter the following details: 

    - **Name**: *Windows 10 content protection*
    - **Description**: *Users associated with this policy will not be able to cut, copy, or paste any content between the assigned app and other non-managed apps on the device.*
    - **Platform**: *Windows 10*
    - **Enrollment state**: *With enrollment*

3. Select **Protected apps** to choose the apps that must adhere to this policy.
4. Click **Add apps**.
5. Under **Recommended apps**, select **Word Mobile**.
5. Click **OK** > **OK**. 
6. Select **Required settings** to configure the app.
7. Click **Allow Overrides** to set the Windows Information Protection mode. Selecting this option will block enterprise data from leaving the protected app.
8. Click **OK** > **Create**.

You’ll now see the app protection policy in Intune.

### Assign the app protection policy

After you've created an app protection policy in Intune, you can assign to groups. 

Use the following steps to assign the app protection policy:

1.	In [Intune](https://aka.ms/intuneportal), select **Intune** > **Client apps** > **App protection policies**. 
2.	Select the app protection policy you created earlier. In this quickstart, the policy is **Windows 10 content protection**.
3.	Select **Assignments**.
4.	Click **Select groups to include** in the **Include** tab.
5.	Select **Contoso Testers** as the group to include.
6.	Click **Select**. 

You now have assigned the app protection policy.

> [!NOTE]
> App protection policies can only be applied to groups that contains users, not groups that contain devices.

## Next steps

In this quickstart, you created and assigned an app protection policy. Users of the app that have this policy assigned will not be able to cut, copy, or paste any content between the assigned app and other non-managed apps on the device. This type of protection will help protect your organization’s data.

> [!div class="nextstepaction"]
> [Quickstart: Create and assign a custom role](quickstart-create-custom-role.md)
