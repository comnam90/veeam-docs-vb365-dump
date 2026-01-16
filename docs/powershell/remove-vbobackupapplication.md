---
title: "remove-vbobackupapplication"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vbobackupapplication.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes backup application settings from Microsoft organizations.

Syntax

|  |
| --- |
| Remove-VBOBackupApplication -Organization <VBOOrganization> -BackupApplications <VBOBackupApplication[]> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes backup application settings from Microsoft organizations that are added to the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will remove backup application settings from the specified Microsoft organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| BackupApplications | Specifies an array of backup applications whose settings you want to remove. The cmdlet will remove these backup application settings from a Microsoft organization. | Accepts the VBOBackupApplication[] object.  To get this object, run the [Get-VBOBackupApplication](get-vbobackupapplication.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Backup Application Settings from Microsoft Organization

This example shows how to remove the c3adb1ab-dc54-4a1c-8d7c-63dacf5209f3 backup application settings from the Columbus Microsoft organization that are added to the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| $organization = Get-VBOOrganization -Name "Columbus"  $application = Get-VBOBackupApplication -Organization $organization -ApplicationId c3adb1ab-dc54-4a1c-8d7c-63dacf5209f3  Remove-VBOBackupApplication -Organization $organization -BackupApplications $application -Confirm |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $organization variable.
2. Run the [Get-VBOBackupApplication](get-vbobackupapplication.md) cmdlet. Specify the ApplicationId parameter value. Save the result to the $application variable.
3. Run the Remove-VBOBackupApplication cmdlet. Specify the following settings:

* Set the $organization variable as the Organization parameter value.
* Set the $application variable as the BackupApplications parameter value.
* Provide the Confirm parameter.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOBackupApplication](get-vbobackupapplication.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
