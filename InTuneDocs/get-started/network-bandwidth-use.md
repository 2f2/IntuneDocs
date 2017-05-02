---
# required metadata

title: Intune network bandwidth use | Microsoft Docs
description: intune network bandwidth usage
keywords:
author: nathbarnms.author: nathbarn
manager: angrobe
ms.date: 03/07/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Intune network bandwidth use

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This guidance helps Intune admins understand the network requirements for the Intune service. You can use this information to understand bandwidth requirements and IP address and port settings needed for proxy settings.

## Average network traffic
This table lists the approximate size and frequency of common content that travels across the network for each client.

> [!NOTE]
> To ensure that computers and mobile devices receive the necessary updates and content from the Intune service, they must be periodically connected to the Internet. The time taken to receive updates or content will vary, but as a guideline, they should remain continuously connected to the Internet for at least 1 hour each day.

|Content type|Approximate size|Frequency and details|
|----------------|--------------------|-------------------------|
|Intune client installation<br /><br />**The following requirements are in addition to the Intune client installation**|125 MB|**One time**<br /><br />The size of the client download varies depending on the operating system of the client computer.|
|Client enrollment package|15 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Endpoint Protection agent|65 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Operations Manager agent|11 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Policy agent|3 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Remote Assistance via Microsoft Easy Assist agent|6 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Daily client operations|6 MB|**Daily**<br /><br />The Intune client regularly communicates with the Intune service to check for updates and policies, and to report the client’s status to the service.|
|Endpoint Protection malware definition updates|Varies<br /><br />Typically 40 KB to 2 MB|**Daily**<br /><br />Up to three times a day.|
|Endpoint Protection engine update|5 MB|**Monthly**|
|Software updates|Varies<br /><br />The size depends on the updates you deploy.|**Monthly**<br /><br />Typically, software updates release on the second Tuesday of each month.<br /><br />A newly enrolled or deployed computer can use more network bandwidth while downloading the full set of previously released updates.|
|Service packs|Varies<br /><br />The size varies for each service pack you deploy.|**Varies**<br /><br />Depends on when you deploy service packs.|
|Software distribution|Varies<br /><br />The size depends on the software you deploy.|**Varies**<br /><br />Depends on when you deploy software.|

## Ways to reduce network bandwidth use
You can use one or more of the following methods to reduce network bandwidth use for Intune clients.

### Use a proxy server to cache content requests
You can use a proxy server that can cache content to reduce duplicate downloads and reduce the use of network bandwidth by clients that request content from the Internet.

A caching proxy server receives requests for content from client computers on your network, retrieves that content from the Internet, and can then cache both HTTP responses and binary downloads. The server uses the cached information to answer subsequent requests from Intune client computers.

The following are typical settings to use for a proxy server that caches content for Intune clients.

|Setting|Recommended value|Details|
|-----------|---------------------|-----------|
|Cache size|5 GB to 30 GB|The value varies based on the number of client computers in your network and the configurations you use. To prevent files from being deleted too soon, adjust the size of the cache for your environment.|
|Individual cache file size|950 MB|This setting might not be available in all caching proxy servers.|
|Object types to cache|HTTP<br /><br />HTTPS<br /><br />BITS|Intune packages are CAB files retrieved by Background Intelligent Transfer Service (BITS) download over HTTP.|
For information about using a proxy server to cache content, see the documentation for your proxy server solution.

### Use Background Intelligent Transfer Service on computers
Intune supports using Background Intelligent Transfer Service (BITS) on a Windows computer to reduce the network bandwidth that is used during the hours that you configure. You can configure policy for BITS on the **Network bandwidth** page of the Intune Agent policy.

To learn more about BITS and Windows computers, see [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in the TechNet Library.

### Use BranchCache on computers
Intune clients can use BranchCache to reduce wide area network (WAN) traffic. The following operating systems that are supported as clients also support BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

To use BranchCache, the client computer must have BranchCache enabled, and then be configured for **distributed cache mode**.

By default, BranchCache and distributed cache mode are enabled on a computer when the Intune client is installed. However, if the client already has Group Policy that disables BranchCache, Intune does not override that policy and BranchCache will remains disabled on that computer.

If you use BranchCache, you should communicate with other administrators in your organization who manage Group Policy and Intune Firewall policy to ensure they do not deploy policy that disables BranchCache or Firewall exceptions. For more about BranchCache, see [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx).

## Network communication requirements

You must enable network communications between the devices you manage and use to manage your Intune subscription, and the websites required for cloud-based services.

Intune uses no on-premises infrastructure such as servers running Intune software, but there are options to use on-premises infrastructure including Exchange and Active Directory synchronization tools.

To manage computers that are behind firewalls and proxy servers, you must set up firewalls and proxy servers to allow communications for Intune. To manage computers that are behind a proxy server, be aware that:

-   The proxy server must support both **HTTP** and **HTTPS** because Intune clients use both protocols
-   Intune supports unauthenticated proxy servers

You can modify proxy server settings on individual client computers, or you can use Group Policy settings to change settings for all client computers that are located behind a specified proxy server.

Managed devices require configurations that let **All Users** access services through firewalls.

The following tables list the ports and services that the Intune client accesses:

|**Domains**|**IP address**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |	13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |

### DNS names and services

The following table identifies DNS names and their IP addresses.

|**DNS** | **Purpose** |
|-----------|----------|
|manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br> a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | Used for device enrollment and device check-in. <br><br>manage.microsoft.com is also used for couple of other services that are called by our services (not directly hit by any customer)|
|sts.manage.microsoft.com |Used by Company Portal and services listed above |
|portal.manage.microsoft.com <br>m.manage.microsoft.com <br><br>fei.&lt;MSU/ASU>.manage.microsoft.com <br> <br>portal.fei.&lt;MSU/ASU>.manage.microsoft.com <br> <br>m.fei.&lt;MSU/ASU>.manage.microsoft.com |Used by Company Portal (end user portal)|

>[!div class="step-by-step"]

>[&larr; **Prerequisites**](what-to-know-before-you-start-microsoft-intune.md)     [**Subscription** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  
