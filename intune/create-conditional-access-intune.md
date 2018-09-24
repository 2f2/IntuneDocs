---
# required metadata

title: Quickstart - Create an email device profile for iOS
titlesuffix: Microsoft Intune
description: Learn how to use Microsoft Intune to create an email device profile so iOS devices can securely connect to company email.
keywords:
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 09/19/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up device-based conditional access with Intune

With Intune, you can enhance conditional access in Azure Active Directory by adding mobile device compliance and mobile app management to the access controls. Once you’ve created an Intune compliance policy that defines the requirements for devices to be compliant, you can use a device’s compliance status to either allow or block access to your apps and services. 

A conditional access policy specifies the app or services you want to protect, the conditions under which the apps or services can be accessed, and the users to whom the policy applies. Conditional access is an Azure AD feature that is configurable in Azure Active Directory, but you can also set up these same policies from within the Intune portal, as shown below.

> [!NOTE]
> Conditional access requires an Azure Active Directory Premium license.

1.	In the Intune portal, select **Conditional access** > **Policies** > **New policy**.
   
    ![Create a new conditional access policy](media/create-conditional-access-intune/create-ca.png)
 
2.	Under **Assignments**, select **Users and groups**. 
3.	On the **Include** tab, identify the users or groups to whom you want this conditional access policy to apply. Once you’ve chosen whom to include, you can use the **Exclude** tab if there are any users, roles, or groups you want to exclude from this policy.
  
   - **All users**: Select this option to apply the policy to all users and groups, including internal and guest users.
  
   - **Select users and groups**: Select this option and specify one or more of the following:
  
     a. **All guest users**: Select this option to include or exclude external guest users (e.g. partners, external collaborators)
      
     b. **Directory roles**: Select one or more Azure AD roles to include or exclude users who are assigned these roles.
      
     c. **Users and groups**: Select this option to search for and select individual users or groups you want include or exclude.
     
      > [!TIP]
      > Test the policy against a smaller group of users to make sure it works as expected.
4.	Select **Done**.
5.	Under **Assignments**, select **Cloud apps**. 
6.	On the **Include tab**, identify the apps and services you want to protect with this conditional access policy. Then you can use the **Exclude** tab if there are any apps or services you want to exclude from this policy.
  - **All cloud apps**: Select this option to apply the policy to all apps.
      > [!IMPORTANT]
      > The Microsoft Azure Management app for access to the Azure portal is included in this list. Be sure to use the **Exclude** tab either here or in the **Users and groups** options to make sure you (or the users or groups you designate) will be able to sign in to the Azure portal. 

  - **Select apps**: Select this option, choose **Select**, and then use the applications list to search for and select the apps or services you want to protect.
    
    ![Create a new conditional access policy](media/create-conditional-access-intune/create-ca-select-apps.png)

7.	Select **Done**.
8.	Under **Assignments**, select **Conditions**.
  - **Sign-in risk**: Choose Yes to use Azure AD Identity Protection sign-in risk detection with this policy, and then choose the sign-in risk levels the policy should apply to.
  - **Device platforms**: On the **Include** tab, identify the device platforms you want to this conditional access policy to apply to. Use the **Exclude** tab to exclude platforms from this policy.
  - **Locations**: On the **Include** tab, specify whether the policy applies to any location, trusted network locations that are under the control of your IT department, or specific network locations. Use the **Exclude** tab to exclude network locations from this policy. 
  - **Client apps**: Choose **Yes** to specify if the policy should apply to browser apps, mobile apps, and desktop clients. You can also select **Modern authentication clients** (such as Outlook for iOS or Outlook for Android) and **Exchange ActiveSync clients**.
  - **Device state**: The conditional access policy will apply to all device states unless you choose Yes and specifically exclude the states Device Hybrid Azure AD joined or Device marked as compliant (or both).
    
    ![Create a new conditional access policy](media/create-conditional-access-intune/create-ca-device-platforms.png)

     > [!TIP]
     > f you want to protect both **Modern authentication** clients and **Exchange ActiveSync clients**, create two separate conditional access policies, one for each client type. Although Exchange ActiveSync supports modern authentication, the only condition that is supported by Exchange ActiveSync is platform. Other conditions, including multi-factor authentication, are not supported. To effectively protect access to Exchange Online from Exchange ActiveSync, create a conditional access policy that specifies the cloud app Office 365 Exchange Online and the client app Exchange ActiveSync with Apply policy only to supported platforms selected.

9.	Select **Done**.
10.	Under **Access controls**, select **Grant**. This is where you specify what happens based on the conditions you’ve set up. You can selection from the following:
  - **Block access**: The users specified in this policy will be denied access to the apps under the conditions you’ve specified.
  - **Grant access**: The users specified in this policy will be granted access, but you can require any of the following further actions:
     - **Require multi-factor authentication**: The user will need to complete additional security requirements, like a phone call or text.
     - **Require device to be marked as compliant**: The device must be Intune compliant. If the device is noncompliant, the user will be given the option to enroll the device in Intune. 
     - **Require Hybrid Azure AD joined device**:
     - **Require approved client app**: The device must use approved client apps. 
     - **For multiple controls**: Select **Require all the selected controls** so that all of the requirements above will be enforced when a device attempts to access the app.
    
    ![Access controls Grant settings](media/create-conditional-access-intune/create-ca-grant-access-settings.png)
 
11.	Under **Enable policy**, select **On**.
     
    ![Enable the policy](media/create-conditional-access-intune/enable-policy.png)

12.	Select **Create**.

## See also
[App-based conditional access with Intune](app-based-conditional-access-intune.md)