---
title: Use SCEP certificate profiles with Microsoft Intune - Azure | Microsoft Docs
description: Create and assign Simple Certificate Enrollment Protocol (SCEP) certificate profiles with Microsoft Intune.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/28/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Create and assign SCEP certificate profiles in Intune

After you [configure your infrastructure](certificates-scep-configure.md) to support Simple Certificate Enrollment Protocol (SCEP) certificates, you can create and then assign SCEP certificate profiles to users and devices in Intune.

> [!IMPORTANT]  
> Before you create SCEP certificate profiles, devices that will use a SCEP certificate profile must trust your Trusted Root Certification Authority (CA). Use a *trusted certificate profile* in Intune to provision the Trusted Root CA certificate to users and devices For information about the trusted certificate profile, see [Export the trusted root CA certificate](certificates-configure.md#export-the-trusted-root-ca-certificate) and [Create trusted certificate profiles](certificates-configure.md#create-trusted-certificate-profiles) in *Use certificates for authentication in Intune*.


## Create a SCEP certificate profile

1. Sign in to the [Intune portal](https://aka.ms/intuneportal).
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter a **Name** and **Description** for the SCEP certificate profile.
4. From the **Platform** drop-down list, select a [supported device platform](certificates-configure.md#supported-platforms-and-certificate-profiles) for this SCEP certificate. 
5. From the **Profile type** drop-down list, select **SCEP certificate**.
6. Select **Settings**, and then complete the following configurations:

   - **Certificate type**:   
     *(Applies to:  Android enterprise, iOS, macOS, Windows 8.1 and later, and Windows 10 and later.)*  

      Select a type depending on how you'll use the certificate profile:
      - **User**: *User* certificates can contain both user and device attributes in the subject and SAN of the certificate.  
      - **Device**:  *Device* certificates can only contain device attributes in the subject and SAN of the certificate.  
      
        Use **Device** for scenarios such as user-less devices, like kiosks, or for Windows devices. Place the certificate in the Local Computer certificate store.  

   - **Subject name format**:  
     Select how Intune automatically creates the subject name in the certificate request. Options for the subject name format depend on the Certificate type you select, either **User** or **Device**.  

     - **User certificate type**  
       Format options for the *Subject name format* include:  
       - **Not configured**
       - **Common name**
       - **Common name including email**
       - **Common name as email**
       - **IMEI (International Mobile Equipment Identity)**
       - **Serial number**
       - **Custom**: When you select this option, a **Custom** text box is also shown. Use this field to enter a custom subject name format, including variables. Custom format supports two variables: **Common Name (CN)** and **Email (E)**. **Common Name (CN)** can be set to any of the following variables:

         - **CN={{UserName}}**: The user principal name of the user, such as janedoe@contoso.com
         - **CN={{AAD_Device_ID}}**: An ID assigned when you register a device in Azure Active Directory (AD). This ID is typically used to authenticate with Azure AD.
         - **CN={{SERIALNUMBER}}**: The unique serial number (SN) typically used by the manufacturer to identify a device.
         - **CN={{IMEINumber}}**: The International Mobile Equipment Identity (IMEI) unique number used to identify a mobile phone.
         - **CN={{OnPrem_Distinguished_Name}}**: A sequence of relative distinguished names separated by comma, such as *CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com*.

           To use the *{{OnPrem_Distinguished_Name}}* variable, be sure to sync the *onpremisesdistingishedname* user attribute using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to your Azure AD.

         - **CN={{onPremisesSamAccountName}}**: Admins can sync the samAccountName attribute from Active Directory to Azure AD using Azure AD connect into an attribute called *onPremisesSamAccountName*. Intune can substitute that variable as part of a certificate issuance request in the subject of a certificate. The samAccountName attribute is the user sign in name used to support clients and servers from a previous version of Windows (pre-Windows 2000). The user sign in name format is: *DomainName\testUser*, or only *testUser*.

            To use the *{{onPremisesSamAccountName}}* variable, be sure to sync the *onPremisesSamAccountName* user attribute using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to your Azure AD.

         By using a combination of one or many of these variables and static strings, you can create a custom subject name format, such as:  
         - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
            
        That example includes a subject name format that uses the CN and E variables, and strings for Organizational Unit, Organization, Location, State, and Country values. [CertStrToName function](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) describes this function, and its supported strings.

      - **Device certificate type**  
        Format options for the Subject name format include the following variables: 
        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId​}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}** *(Only applicable for Windows and domain-joined devices)*
        - **{{MEID}}**
        
        You can specify these variables, followed by the text for the variable, in the textbox. For example, the common name for a device named *Device1* can be added as **CN={{DeviceName}}Device1**.

        > [!IMPORTANT]  
        > - When you specify a variable, enclose the variable name in curly brackets { } as seen in the example, to avoid an error.  
        > - Device properties used in the *subject* or *SAN* of a device certificate, like **IMEI**, **SerialNumber**, and **FullyQualifiedDomainName**, are properties that could be spoofed by a person with access to the device.
        > - A device must support all variables specified in a certificate profile for that profile to install on that device.  For example, if **{{IMEI}}** is used in the subject name of a SCEP profile and is assigned to a device that doesn’t have an IMEI number, the profile fails to install.  
 


   - **Subject alternative name**:  
     Select how Intune automatically creates the subject alternative name (SAN) in the certificate request. Options for the SAN depend on the Certificate type you selected; either **User** or **Device**.  

      - **User certificate type**  
        Select from the available attributes:  
        - **Email address**
        - **User principal name (UPN)** 

        For example, user certificate types can include the user principal name (UPN) in the subject alternative name. If a client certificate is used to authenticate to a Network Policy Server, set the subject alternative name to the UPN.

      - **Device certificate type**  
        Use the **Attribute** dropdown and select an attribute, assign a **Value**, and **Add** that to the certificate profile. You can add multiple values by selecting additional attributes.  

        Available attributes include:
        - **Email address**
        - **User principal name (UPN)**
        - **DNS**

        With the *Device* certificate type, you can use the following device certificate variables for the value:  

        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId​}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}**
        - **{{MEID}}**

        To specify a value for an attribute, include the variable name with curly brackets, followed by the text for that variable. For example, a value for the DNS attribute can be added **{{AzureADDeviceId}}.domain.com** where *.domain.com* is the text. For a user named *User1* an Email address might appear as {{FullyQualifiedDomainName}}User1@Contoso.com.  

        > [!IMPORTANT]  
        > - When using a device certificate variable, enclose the variable name in curly brackets { }.  
        > - Don’t use curly brackets **{ }**, pipe symbols **|**, and semicolons **;**, in the text that follows the variable.  
        > - Device properties used in the *subject* or *SAN* of a device certificate, like **IMEI**, **SerialNumber**, and **FullyQualifiedDomainName**, are properties that could be spoofed by a person with access to the device.  
        > - A device must support all variables specified in a certificate profile for that profile to install on that device.  For example, if **{{IMEI}}** is used in the subject name of a SCEP profile and is assigned to a device that doesn’t have an IMEI number, the profile fails to install.

   - **Certificate validity period**:  
     You can enter a value that is lower than the validity period in the certificate template, but not higher. If you configured the certificate template to [support a custom value that can be set from within the Intune console](certificates-scep-configure.md#modify-the-validity-period-of-the-certificate-template), use this setting to specify the amount of remaining time before the certificate expires.  

     For example, if the certificate validity period in the certificate template is two years, you can enter a value of one year, but not a value of five years. The value must also be lower than the remaining validity period of the issuing CA's certificate.

   - **Key storage provider (KSP)**:  
     *(Applies to:  Windows 8.1 and later, and Windows 10 and later)*  
     
     Specify where the key to the certificate is stored. Choose from the following values:  
     - **Enroll to Trusted Platform Module (TPM) KSP if present, otherwise Software KSP**
     - **Enroll to Trusted Platform Module (TPM) KSP, otherwise fail**
     - **Enroll to Passport, otherwise fail (Windows 10 and later)**
     - **Enroll to Software KSP**

   - **Key usage**:  
     Select key usage options for the certificate:

     - **Digital signature**: Allow key exchange only when a digital signature helps protect the key.
     - **Key encipherment**: Allow key exchange only when the key is encrypted.  

   - **Key size (bits)**:  
     Select the number of bits contained in the key.  

   - **Hash algorithm**:  
     *(Applies to Android, Android enterprise, Windows Phone 8.1, Windows 8.1 and later, and Windows 10 and later)*  

     Select one of the available hash algorithm types to use with this certificate. Select the strongest level of security that the connecting devices support.

   - **Root Certificate**:  
     Select the *trusted certificate profile* you previously configured and assigned to applicable users and devices for this SCEP certificate profile. The trusted certificate profile is used to provision users and devices with the Trusted Root CA certificate. For information about the trusted certificate profile, see [Export your trusted root CA certificate](certificates-configure.md#export-the-trusted-root-ca-certificate) and [Create trusted certificate profiles](certificates-configure.md#create-trusted-certificate-profiles) in *Use certificates for authentication in Intune*,

   - **Extended key usage**:  
     Add values for the certificate's intended purpose. In most cases, the certificate requires *client authentication* so that the user or device can authenticate to a server. You can add additional key usages as required.

   - **Renewal threshold (%)**:  
     Enter the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.

   - **SCEP Server URLs**:  
     Enter one or more URLs for the NDES Servers that issue certificates via SCEP. For example, enter something like *https://ndes.contoso.com/certsrv/mscep/mscep.dll*.

7. Select **OK**, and then select **Create**. The profile is created and appears on the *Device configuration - Profiles* list.


## Assign the certificate profile
Assign SCEP certificate profiles the same way you [deploy device profiles](device-profile-assign.md) for other purposes. However, consider the following before you continue:

- When you assign SCEP certificate profiles to groups, the Trusted Root CA certificate file (as specified in the *trusted certificate profile*) is installed on the device. The device uses the SCEP certificate profile to create a certificate request for that Trusted Root CA certificate. 

- The SCEP certificate profile installs only on devices that run the platform you specified when you created the certificate profile.

- You can assign certificate profiles to user collections or to device collections.

- To publish a certificate to a device quickly after the device enrolls, assign the certificate profile to a user group rather than to a device group. If you assign to a device group, a full device registration is required before the device receives policies.  

- If you use co-management for Intune and Configuration Manager, in Configuration Manager [set the workload slider](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads) for Resource Access Policy to **Intune** or **Pilot Intune**. This setting allows Windows 10 clients to start the process of requesting the certificate.

- Although you create and assign the trusted certificate profile and the SCEP certificate profile separately, both must be assigned. Without both installed on a device, the SCEP certificate policy fails.


> [!NOTE]
> On iOS devices, when a SCEP certificate profile is associated with an additional profile, like a Wi-Fi or VPN profile, the device receives a certificate for each of those additional profiles. This results in the iOS device having multiple certificates delivered by the SCEP certificate request.  

## Next steps  

[Assign profiles](device-profile-assign.md)  