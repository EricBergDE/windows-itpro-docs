---
title: Assign user access to the Windows Defender Advanced Threat Protection portal
description: Assign read and write or read only access to the Windows Defender Advanced Threat Protection portal. 
keywords: assign user roles, assign read and write access, assign read only access, user, user roles, roles
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
---

# Assign user access to the Windows Defender ATP portal

**Applies to:**

- Windows 10 Insider Preview Build 14332 or later
- Azure Active Directory
<!--Office 365-->
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

<span style="color:#ED1C24;">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</span>

Windows Defender ATP users and access permissions are managed in Azure Active Directory (AAD). User can be assigned one of the following levels of permissions:
- Full access (Read and Write)
- Read only access

**Full access** <br>
Users with full access can log in, view all system information as well as resolve alerts, submit files for deep analysis, and download the onboarding package.
Assigning full access rights requires adding the users to the “Security Administrator” or “Global Administrator” AAD built-in roles.

**Read only access** <br>
Users with read only access can log in, view all alerts, and related information. 
They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.
Assigning read only access rights requires adding the users to the “Security Reader” AAD built-in role.

<!--
Your administrator can assign roles using the Office 365 portal, or in the Azure classic portal, or by using the AAD module for Windows PowerShell. 
For more information, see [Assigning admin roles in Office 365](https://support.office.com/en-us/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) and [Assigning administrator roles in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-assign-admin-roles/).-->

Use the following cmdlets to perform the security role assignment:

- Full access:<br>```Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress “reader@Contoso.onmicrosoft.com”```
- Read only access:<br>```Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"```

For more information see, [Manage Azure AD group and role membership](https://technet.microsoft.com/en-us/library/321d532e-407d-4e29-a00a-8afbe23008dd#BKMK_ManageGroups).