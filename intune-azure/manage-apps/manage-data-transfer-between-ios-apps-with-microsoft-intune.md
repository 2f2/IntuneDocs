---
# required metadata

title: Manage transferring data between iOS apps |Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Use this topic to understand how you can use the iOS Open-in feature and mobile app management policies to manage data transfers between apps."
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to manage data transfer between iOS apps
## Manage iOS apps
Protecting your company data includes making sure that file transfers are restricted to apps that are managed by you.  You can manage iOS apps in the following ways:

-   Prevent company data loss  by configuring an app protection policy for the apps, which we will refer to as **policy-managed**  apps. See [all the Intune-enlightened apps you can manage with app protection policy](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   You can also deploy and manage apps through the **MDM channel**.  This requires that the devices are enrolled in the MDM solution. These can be **policy-managed**  apps or other managed  apps.

The **Open in management** feature for iOS devices can limit file transfers between apps that are deployed through the **MDM channel**. Open in management restrictions are set in configuration settings and deployed using your MDM solution.  When the user installs the deployed app, the restrictions you set are applied.
##  Using app protection with iOS apps
App protection policies can be used with the iOS **Open in management** feature to protect company data in the following ways:

-   **Employee owned devices not managed by any MDM solution:** You can set the app protection policy settings to **Allow app to transfer data to only managed apps**. When the end user opens a protected file in an app that is not policy-managed, the file is unreadable.

-   **Devices managed by Intune:** For devices enrolled in Intune, data transfer between apps with app protection policies and other managed iOS apps deployed through Intune is allowed  automatically. To allow data transfer between apps with app protection policies, enable the **Allow app to transfer data to only managed apps** setting. You can use the **Open in management** feature to control data transfer between apps that are deployed through Intune.   

-   **Devices managed by a third party MDM solution:** You can restrict data transfer to only managed apps by using the iOS **Open in management** feature.
To make sure that apps that you deploy using your third party MDM solution are also associated with the app protection policies you have configured in Intune, you must configure the user UPN setting as described in the [Configure user UPN setting](#configure-user-upn-setting-for-third-party-EMM) walkthrough.  When apps are deployed with the user UPN setting, the app protection policies are applied to the app when the end user signs-in using their work account.

> [!IMPORTANT]
> The user UPN setting is only required for apps deployed to devices managed by a third-party MDM.  For Intune-managed devices, this setting is not required.


## Configure user UPN setting for third-party EMM
Configuring the user UPN setting is **required** for devices that are managed by a third-party EMM solution. The procedure described below is a general flow on how to configure the UPN setting and the resulting end user experience:


1.  In the Azure portal, [configure an app protection policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) for iOS platform. Configure policy settings per your company requirements and select the apps that should have this policy.

2.  Deploy the apps and the email profile that you want managed **through your third-party MDM solution** using the generalized steps below. This experience is also covered by Example 1.

  1.  Deploy the app  with the following app configuration settings:

      **key** = IntuneMAMUPN,  **value** = <username@company.com>

      Example: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Deploy the Open in management policy using your third-party MDM provider to enrolled devices.


### Example 1: Admin experience in third-party MDM console

1. Go to the admin console of third-party MDM provider. Go to the section of the console in which you deploy application configuration settings to enrolled iOS devices.

2. In the Application Configuration section, enter the following setting:

  **key** = IntuneMAMUPN,  **value** = <username@company.com>

  The exact syntax of the key/value pair may differ based on your third-party MDM provider. The table below shows examples of third-party MDM providers and the exact values you should enter for the key/value pair.

|Third-party MDM provider| Configuration Key | Value Type | Configuration Value|
| ------- | ---- | ---- | ---- |
|VMware AirWatch| IntuneMAMUPN | String | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | String | ${userUPN} **or** ${userEmailAddress} |


### Example 2: End-user experience

1.  End user installs Microsoft Word app on the device.

2.  End user launches the managed native email app to access their email.

3.  End user tries to open document from native mail in Microsoft Word.

4.  When the Word app launches, the end user is prompted to log in using their work account.  This work account the end user enters when prompted should match account you specified in the configured in the app configuration settings for the Microsoft Word app.

    > [!NOTE]
    > The end user can add other personal accounts to Word to do their personal work and not be affected by the app protection policies when using the Word app in a personal context.

5.  When the login is successful, the app policy settings are applied to the Word app.

6.  Now the data transfer succeeds and the document is tagged as corporate identity in the app. In addition, the data is treated in a work context and the policy settings are applied accordingly.

### Validate user UPN setting for third-party EMM

After configuring the user UPN setting, you should validate the iOS app's ability to receive and comply to Intune app protection policy.

For example, the **Require app PIN** policy setting is easy to visually test on a device. If the policy setting is set to **Yes**, the end user should see a prompt to set or enter a PIN when attempting to access company data.

First,  [create and deploy an app protection policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) to the iOS app. See [Validate app protection policies](validate-mobile-application-management.md) for more information on how to test app protection policy.


### See also
[What is Intune app protection policy](what-is-app-protection-policy.md)
