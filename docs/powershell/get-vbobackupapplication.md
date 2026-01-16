---
title: "get-vbobackupapplication"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbobackupapplication.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns backup application settings that are added to Microsoft organizations.

Syntax

|  |
| --- |
| Get-VBOBackupApplication -Organization <VBOOrganization> [-DisplayName <String>] [-ApplicationId <Guid>] [-ThumbprintCertificate <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns backup application settings that are added to Microsoft organizations. The backup application represents settings of a Microsoft Entra application.

|  |
| --- |
| ![Get-VBOBackupApplication](images/icon_important.webp) Important |
| This cmdlet will run only for Microsoft organizations that are added to the Veeam Backup for Microsoft 365 infrastructure using modern app-only authentication method. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return settings of backup applications that are added to the specified Microsoft organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| DisplayName | Specifies a display name of the backup application. The cmdlet will return settings of a backup application with the specified name. | String | False | Named | False |
| ApplicationId | Specifies an ID of the backup application. The cmdlet will return settings of the backup application with the specified ID. | Guid | False | Named | False |
| ThumbprintCertificate | Specifies a thumbprint of the backup application. The cmdlet will return settings of a backup application with the specified thumbprint. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOBackupApplication object that contains backup application settings that are added to Microsoft organizations.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Backup Application Settings

|  |  |
| --- | --- |
| This example shows how to get all backup application settings that are added to Microsoft organizations.  |  | | --- | | $org = Get-VBOOrganization  Get-VBOBackupApplication -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable. 2. Run the Get-VBOBackupApplication cmdlet. Set the $org variable as the Organization parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Backup Application Settings by ID

|  |  |
| --- | --- |
| This example shows how to get the c3adb1ab-dc54-4a1c-8d7c-63dacf5209f3 backup application settings that are added to Microsoft organizations.  |  | | --- | | $org = Get-VBOOrganization  Get-VBOBackupApplication -Organization $org -ApplicationId c3adb1ab-dc54-4a1c-8d7c-63dacf5209f3 |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable. 2. Run the Get-VBOBackupApplication cmdlet. Set the $org variable as the Organization parameter value. Specify the ApplicationId parameter value. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
