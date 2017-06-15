---
# required metadata

title: Service Description 
description: Intune is a cloud-based service that helps you manage Windows, iOS, Mac OS X, Android, and Windows Mobile devices.
keywords:
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 09/22/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: cacamp
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Microsoft Intune service description

[!INCLUDE[both-portal](./includes/note-for-both-portals.md)]

Microsoft Intune is a cloud-based service that helps you manage devices that run Windows, Mac OS X, iOS, Android, or Windows Mobile. Intune also helps protect corporate applications and data. You can use Intune alone, or you can integrate it with System Center Configuration Manager to extend your management capabilities.

Microsoft offers the Intune Onboarding benefit for eligible services in eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more about the Onboarding benefit, see [Microsoft Intune Onboarding Benefit Description](http://go.microsoft.com/fwlink/?LinkId=619281).

You can start to use Intune with a 30-day free trial that includes 100 user licenses. To start your free trial, [go to the Intune Sign up page](https://www.microsoft.com/server-cloud/products/microsoft-intune/). If your organization has an Enterprise Agreement or equivalent volume licensing agreement, contact your Microsoft representative to set up your free trial.

> [!NOTE]
> If your organization has a Microsoft Online Services work or school account, and you might continue with this Intune subscription in production after the trial period ends, then choose the **Sign in** option on that page and authenticate by using the Global Administrator account for your organization. This action will ensure that your Intune trial links to your existing work or school account.

For a list of settings that you can set up on mobile devices, see:

-   [Enrolled device management capabilities of Microsoft Intune](introduction-intune.md)

-   [Hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune](/sccm/mdm/understand/hybrid-mobile-device-management)

For more about System Center Configuration Manager, see [Documentation  for System Center Configuration Manager](/sccm/index).

## Learn how Intune service updates affect you

Because Intune is an online service and because the MDM ecosystem changes frequently with mobile device OS and mobile app releases, Microsoft updates Intune on a regular basis.

Use the information in this article to help you learn about the frequency of these service updates and the advance notification we give to you when an update might affect your use of the service.

There are three ways to learn about changes in the Intune service:

- First, review the [What's new in Microsoft Intune](whats-new.md). This list is updated with the monthly service update and weekly when, for example, apps such as the Company Portal app are released. 

- Second, important service updates will also be communicated to you in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) Message Center. If you install the companion [Office 365 Admin mobile app](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a), you can receive notifications on your mobile device. You can find detailed information on how to work within the Office 365 Message Center [here](https://support.office.com/en-US/client/results?Shownav=true&lcid=1033&ns=O365ENTADMIN&version=15&omkt=en-US&ver=15&HelpID=O365E_MCManageUpdates). 
    
    A few helpful hints: 

    - The messages in the Office 365 Message Center are targeted. This means that if your company doesn’t have an Intune for EDU offer, we won’t message you about Intune for EDU. 

    - Messages expire. For example, the notification that your service has been updated with a link to What’s New will likely expire prior to the next service update notification. Otherwise, you’d have a large backlog of posts that may no longer be relevant.

    - The Office 365 admin mobile app allows you to search through all the messages and to forward the notification if you wanted to share it with peers in your organization.

    - Under Edit message center preferences, we’ll eventually have a toggle for **Intune** so you can just look at those messages posted to an Intune subscription. If you see Mobile Device Management for Office 365, that is a different service, not Intune.

- Third, we use two blogs to share the EMS message and the Intune support best practices: 
    
    - [Enterprise Mobility + Security blog](https://blogs.technet.microsoft.com/enterprisemobility/) 

    - [Intune support blog](https://blogs.technet.microsoft.com/intunesupport/) 

>[!Note]
>You can monitor Intune service health in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx). Choose **Service Health** in the left pane. You can also use the [Office 365 Admin mobile app](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a) to view service health.

## Types of notices Microsoft provides about the Intune service

To help you plan for service changes, we notify you at least 7-90 days prior to the service change, depending on the impact of the change. These changes might include any of the following types of change:

- Changes to the end user experience that you may want to share with your helpdesk staff or your end users. We provide typically 7 to 30 days notice of those changes and document them on the [What’s New in Intune App UI](whats-new-app-ui.md). Something like a spelling error fix we won’t typically call out in documentation. But a change in the end user enrollment experience is significant enough in the UI that we’ll both post a message to customers in the Office 365 Message center and link to the What’s New in the Intune App UI so you are notified of what’s changing and have time to evaluate and update your end user guidance prior to the changes rolling out in production.

- Changes that require you to take action are called **Plan for Change** and typically provide about 30 days notice. In the Office 365 Message Center the Category specifically says Plan for Change, and if we have an exact date the change will hit production, we’ll also put in an **Act By** date and that’ll give you a visual queue and an explanation mark.

- For most deprecations, we prefer to provide 90 days notice of that deprecation. For example, if we’re no longer going to support a specific version of IE, our goal is to provide 90 days notice. However, deprecations do get complicated when it’s another company announcing the deprecation. For example, a browser company provided notice that they would no longer support Silverlight with their latest build, so we let customers know we were dropping support of that browser, but our notification to customers under the 90 day period.

- In the event of Intune service retirement, you would be notified 12 months in advance.

Finally, in the rare event there’s any post-incident action needed to get your service back to normal, or a large change that we deem potentially disruptive based on customer feedback, we will email the service administrators based on how your [Office 365 communication preferences](https://support.office.com/en-us/article/Change-your-contact-preferences-for-communications-from-Microsoft-6f70de1b-a64d-4498-bfbd-be8c83a9c0fc?ui=en-US&rs=en-US&ad=US) are set and whether you include a valid (and preferably work) email address.  


## Choose the management solution that’s right for you
You can set up Intune in several ways to manage and help protect your company's mobile devices and computers (referred to as **devices** in this article).

-**Intune stand-alone configuration.** Use the web-based admin console in Intune to manage devices in your organization. Intune can be used without any on-premises IT infrastructure. If you use Intune with Active Directory Domain Services, you can use domain user accounts that you manage with Domain Services with Intune.

-**Intune with System Center Configuration Manager.** Use the Configuration Manager management console to manage computers and mobile devices in your enterprise. This configuration can help you to manage all your organization’s devices through a single console, the Configuration Manager Admin Console. Configuration Manager supports very large numbers of mobile devices, servers, and computers. For more about Configuration Manager, see [Hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune](/sccm/mdm/understand/hybrid-mobile-device-management). For more help deciding which approach is right for you, see [Choose between Microsoft Intune standalone and hybrid mobile device management with Configuration Manager](/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).


## Learn more about Intune
Use these resources to learn more about Intune:

- The [Microsoft Intune Trust Center](https://www.microsoft.com/server-cloud/products/intune-trust-center/) provides information about the security, privacy, and compliance practices of Intune, and it describes some of Intune's certifications.

- [Enrolled device management capabilities of Microsoft Intune](introduction-intune.md)

### See also
[Microsoft Intune](index.md)
[Documentation Library for System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx)

[What's new in Microsoft Intune](whats-new.md)
