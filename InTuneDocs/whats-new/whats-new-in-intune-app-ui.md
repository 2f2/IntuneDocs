---
# required metadata

title: UI updates for Intune end user apps | Microsoft Docs
description: "Find out what has changed in UI for apps that work on end user devices with Intune."
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/26/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---
# UI updates for Intune end user apps
Learn what updates we've made to the UI for apps that your end users will see in this release of Microsoft Intune. This can help you with user communications and any updating custom documentation that you've created to support your deployment. It can also help you understand how to better troubleshoot any issues they're facing should they call helpdesk for support using the Company Portal.

> [!Note]
> Please note that the images below are previews, and the announced product may differ from the presented versions.

## April 2017

### Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123-->

We are improving the sign in experience for the Intune Company Portal apps for Android, iOS, and Windows.  The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change. In addition, users can now sign in to the Company Portal from another device with a generated, single-use code. This is especially useful in cases when users need to sign in without credentials.  

Below you can see the previous sign in experience, the new sign in experience with credentials, and the new sign in experience from another device.

__Previous sign in experience__

![The Company Portal sign in page, with an icon of a person in front of a graphical representation of a website. Underneath is the "Sign in" button. A link at the bottom leads to Microsoft Privacy and Cookies information.](./media/cp_ios_aad_signin_before_1704_001.png)

![After tapping Sign in, the user enters their credentials on this page, which asks for a user's email and password, along with offering ways to resolve password failures.](./media/cp_ios_aad_signin_before_1704_002.png)

![After providing their password, the Company Portal app signs in, noting this with a loading bar.](./media/cp_ios_aad_signin_before_1704_003.png)

__New sign in experience__

![The Company Portal sign in page, with an icon of a person in front of a graphical representation of a website. Underneath is the "Sign in" button. A link at the bottom leads to Microsoft Privacy and Cookies information.](./media/cp_ios_aad_signin_after_1704_001.png)

![The user is prompted to provide just their email address rather than their email and password on the same screen.](./media/cp_ios_aad_signin_after_1704_002.png)

![The user is prompted for their password after their email address has been accepted.](./media/cp_ios_aad_signin_after_1704_003.png)

__New sign in experience when signing in from another device__

![The Company Portal sign in page, with an icon of a person in front of a graphical representation of a website. Underneath is the "Sign in" button. A link at the bottom leads to Microsoft Privacy and Cookies information.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Tap the __Sign in from another device__ link.

![The user is prompted to provide just their email address rather than their email and password on the same screen. The link underneath the email field says "Sign in from another device".](./media/cp_ios_aad_signin_from_another_device_after_1704_002.png)

![Instructions are provided to go to the aka.ms/devicelogin page with a unique passcode from your work computer, then to use the code to sign in.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Launch a browser and go to [https://aka.ms/devicelogin](https://aka.ms/devicelogin).

![An image of the user's browser on their work computer rather than their Company Portal app. The "Device login" page displayed prompts the user for the code they received in the Company Portal app.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Enter the code you saw in the Company Portal app. When you select __Continue__, you will be able to authenticate in the using any method that is supported by your company, such as a smartcard.

![The user has input their unique code into the field, and the "Device login" site has asked for confirmation that the Intune Company Portal was the correct app to receive authorization to sign in.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![A confirmation page that states that the user has now signed into the Company Portal app on their device, and that this page can be closed.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

The Company Portal app will begin signing in.

![After going through the authentication process, the Company Portal app signs in, noting this with a loading bar.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

### New icons for the Managed Browser and the Company Portal <!--918433, 918431-->

The Managed Browser is receiving updated icons for both the Android and iOS versions of the app. The new icon will contain the updated Intune badge to make it more consistent with other apps in Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

The Company Portal is also receiving updated icons for the Android, iOS, and Windows versions of the app to improve consistency with other apps in EM+S. These icons will be gradually released across platforms from April to late May.

### Sign-in progress indicator in Android Company Portal <!--953374-->

An update to the Android Company Portal app shows a sign-in progress indicator when the user launches or resumes the app. The indicator progresses through new statuses, beginning with "Connecting...", then "Signing in...", then "Checking for security requirements..." before allowing the user to access the app.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### Improved app install status for the Windows 10 Company Portal app <!--676495-->
The Windows 10 Company Portal app now provides an install progress bar on the app details page. This is supported for modern apps on devices running the Windows 10 Anniversary Update and up..

__Before__
  ![An image of the previous version of the loading screen, where the status simply said 'installing.'](./media/cp_win10_install_status_before_1704.png)

__After__
  ![An image of the updated version of the loading screen, which now shows an install progress bar.](./media/cp_win10_install_status_after_1704.png)

## February 2017

### New user experience for the Company Portal app for Android <!--621622, announced 1702-->
Beginning in March, the Company Portal app for Android will follow [material design guidelines](https://material.io/guidelines/material-design/introduction.html) to create a more modern look and feel. This improved user experience includes:

* __Colors__: tab headers can be colored according to your custom color palette.

![On the left, an image of the Company Portal app for Android before the update. On the right, an image of the Company Portal app for Android after the update. Both images show the Devices tab as the selected tab from the three available tabs of Apps, Devices, and Contact IT.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Interface__: __Featured Apps__ and __All Apps__ buttons have been updated in the __Apps__ tab. The __Search__ button is now a floating action button.

![On the left, an image of the Company Portal app for Android before the update. On the right, an image of the Company Portal app for Android after the update. Both images show the Apps tab as the selected tab from the three available tabs of Apps, Devices, and Contact IT.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navigation__: All Apps shows a tabbed view of __Featured__, __All__ and __Categories__ for easier navigation. __Contact IT__ has been streamlined for improved readability.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## January 2017

### Modernizing the Company Portal website <!--753980, announced 1701-->
Beginning in February, the Company Portal website will support apps that are targeted to users who do not have managed devices. The website will align with other Microsoft products and services by using a new contrasting color scheme, dynamic illustrations, and a "hamburger menu," ![Small image of the hamburger menu that is now added at the top left corner of the Company Portal website](./media/CP_hamburger_menu.png) which will contain helpdesk contact details and information on existing managed devices. The landing page will be rearranged to emphasize apps that are available to users, with carousels for Featured and Recently Updated apps.

![On the left, an image of the current version of the Company Portal website with its previous version of Apps, My Devices, and Featured and Categories views. On the right, an image of the updated version of the Company Portal website with a refreshed app carousel, list of Recently Published apps, and updated Categories view.](./media/CP_Website_BeforeAfter_Feb2016.png)


### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Azure preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new archive](whats-new-archive.md)
