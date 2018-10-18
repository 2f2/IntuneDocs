---
# required metadata

title: Tutorial - Use Autopilot to enroll devices in Intune
titleSuffix: Microsoft Intune
description: In this tutorial, you'll set up Windows Autopilot to enroll devices in Intune.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/12/2018
ms.topic: tutorial
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 
Customer intent: As an Intune admin, I want to set up Windows Autopilot so that users can enroll in Intune.
---

# Tutorial: Use Autopilot to enroll Windows devices in Intune
Windows Autopilot simplifies enrolling devices. With Microsoft Intune and Autopilot, you can give new devices to your end users without the need to build, maintain, and apply custom operating system images. 

In this tutorial, you'll learn how to:
> [!div class="checklist"]
> * Add devices to Intune
> * Create an Autopilot device group
> * Create an Autopilot deployment profile
> * Assign the Autopilot deployment profile to the device group
> * Distribute Windows devices to users and instruct them on how to enroll

If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).

For an overview of Autopilot benefits, scenarios, and prerequisites, see [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## Prerequisites
- [Set up Windows automatic enrollment](quickstart-setup-auto-enrollment.md)
- [Azure Active Directory Premium subscription](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->


## Add devices

The first step in setting up Windows Autopilot is to add the Windows devices to Intune. All you have to do is create a CSV file as explained below and upload it to Intune.

1. In any text editor, create a list of comma separated values (CSV) that identify the Windows devices. Use the following format:
    
    *serial-number*, *windows-product-id*, *hardware-hash*, *optional-order-id*
    
    The first three items are required, but the order id is optional.

2. Save the CSV file.

3. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Devices** > **Import**.

    ![Screenshot of Windows Autopilot devices](media/enrollment-autopilot/autopilot-import-device.png)

4. Under **Add Windows Autopilot devices**, browse to the CSV file you just saved.

    ![Screenshot of Adding Windows Autopilot devices](media/enrollment-autopilot/autopilot-import-device2.png)

5. Choose **Import** to start importing the device information. Importing can take several minutes.

4. After import is complete, choose **Device enrollment** > **Windows enrollment** > **Windows Autopilot** > **Devices** > **Sync**. A message displays that the synchronization is in progress. The process might take a few minutes to complete, depending on how many devices you're synchronizing.

5. Refresh the view to see the new devices.

## Create an Autopilot device group

Next, you'll create a device group and put the Autopilot devices you just loaded into it.

1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Groups** > **New group**.
2. In the **Group** blade:
    1. For **Group type**, choose **Security**.
    2. For **Group name**, enter *Autopilot Group*. For **Group description**, enter *Test group for Autopilot devices*.
    3. For **Membership type**, choose either **Assigned**.
3. In the **Group** blade, choose **Members** and add the Autopilot devices to the group. Autopilot devices that aren't yet enrolled are devices where the name equals the serial number of the device.
4. Choose **Create**.  

## Create an Autopilot deployment profile

After creating a device group, you must create a deployment profile so that you can configure the Autopilot devices.

1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > **Create Profile**.
2. For **Name**, enter *Autopilot Profile*. For **Description**, enter *Test profile for Autopilot devices*.
3. Set **Convert all targeted devices to Autopilot** to **Yes**. This makes sure that all devices in the list get registered register with the Autopilot deployment service. Allow 48 hours for the registration to be processed.
4. For **Deployment mode**, choose **User-driven**. Devices with this profile are associated with the user enrolling the device. User credentials are required to enroll the device.
5. In the **Join to Azure AD as** box, choose **Azure AD joined**.
6. Choose **Out-of-box experience (OOBE)**, configure the following options and leave others set to the default, and then choose **Save**:
    - **End-user license agreement (EULA)**: **Hide**
    - **Privacy settings**: **Show**
    - **User account type**: **Standard**

6. Choose **Create** to create the profile. The Autopilot deployment profile is now available to assign to devices.

## Assign an Autopilot deployment profile to a device group

Now that the deployment profile is created, you'll assign it to the device group.
1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Deployment profiles** > choose a profile.
2. In the specific profile blade, choose **Assignments**. 
3. Choose **Select groups**, then in the **Select groups** blade, choose **Autopilot Group**, then choose **Select**.

## Distribute devices to users

You can now distribute the Windows devices to your users. When they sign in for the first time, the Autopilot system will automatically enroll and configure the devices. 

## Clean up resources

If you don't want to use Autopilot devices any more, you can delete them.

1. If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. In the [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Devices**.

3. Under **Windows Autopilot devices**, choose the devices you want to delete, and then choose **Delete**.

4. Confirm the deletion by choosing **Yes**. It can take a few minutes to delete.

## Next steps
For more information about other options available for Windows Autopilot, see the [in-depth Autopilot enrollment article](enrollment-autopilot.md).

