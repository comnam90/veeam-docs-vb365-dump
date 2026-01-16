---
title: "set-vbobackupitem"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbobackupitem.html"
last_updated: "11/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies organization object settings.

Syntax

|  |
| --- |
| Set-VBOBackupItem -BackupItem <VBOBackupItem[]> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [-GroupMailbox] [-GroupSite] [-Teams] [-TeamsChats] [<CommonParameters>] |

Detailed Description

This cmdlet modifies organization object settings. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| BackupItem | Specifies an organization object. The cmdlet will modify settings of this object. | Accepts the VBOBackupItem[] object.  To get this object, run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. | True | Named | False |
| Mailbox | Defines that the cmdlet will enable the mailbox option for an object.  Default: False | SwitchParameter | False | Named | False |
| ArchiveMailbox | Defines that the cmdlet will enable the archive mailbox option for an object.  Default: False  Note: You cannot specify this parameter for the user of the PublicMailbox type. | SwitchParameter | False | Named | False |
| OneDrive | Defines that the cmdlet will enable the OneDrive option for an object.  Default: False  Note: You cannot specify this parameter for the user of the PublicMailbox type. | SwitchParameter | False | Named | False |
| Sites | Defines that the cmdlet will enable the sites option for an object.  Default: False | SwitchParameter | False | Named | False |
| GroupMailbox | Defines that the cmdlet will enable the group mailbox option for an object.  Default: False | SwitchParameter | False | Named | False |
| GroupSite | Defines that the cmdlet will enable the group site option for an object.  Default: False | SwitchParameter | False | Named | False |
| Teams | Defines that the cmdlet will enable the teams option for an object.  Default: False | SwitchParameter | False | Named | False |
| TeamsChats | Defines that the cmdlet will enable the team chats option for an object.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Modifying Processing Options of User Backup Item

This example shows how to add all processing options except for the mailbox for a backup item with a user named userAlpha.

|  |
| --- |
| $org = Get-VBOOrganization -Name "ABC"  $user = Get-VBOOrganizationUser -Organization $org -DisplayName "userAlpha"  $backupitem = New-VBOBackupItem -User $user -Mailbox -ArchiveMailbox -OneDrive -Sites  Set-VBOBackupItem -BackupItem $backupitem -Mailbox:$false -ArchiveMailbox -OneDrive -Sites |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable.
2. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet with the $org variable and the userAlpha value for the DisplayName parameter to get a user with the display name userAlpha. Save the result to the $user variable.
3. Run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet with the $user variable as the User parameter value and Mailbox, ArchiveMailbox, OneDrive and Sites parameters. Save the result to the $backupitem variable.
4. Run the Set-VBOBackupItem cmdlet with the $backupitem variable as the BackupItem parameter value, ArchiveMailbox, OneDrive and Sites parameters, and the false value for the Mailbox parameter to create a backup item with all userAlpha processing options except for the mailbox.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [New-VBOBackupItem](new-vbobackupitem.md)
* [Get-VBOBackupItem](get-vbobackupitem.md)

Page updated 11/10/2025

Page content applies to build 8.3.0.2201
