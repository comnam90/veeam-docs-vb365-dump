---
title: "Remove-VBOEntityData"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboentitydata.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# Remove-VBOEntityData


Short Description

Removes an organization entity data from a backup repository including an object storage repository that was specified as a target for backup copy jobs.

Syntax

This cmdlet provides parameter sets that allow you to:

* Remove organization user data.

|  |
| --- |
| Remove-VBOEntityData -Repository <VBORepository> -User <VBOUserData> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

* Remove organization group data.

|  |
| --- |
| Remove-VBOEntityData -Repository <VBORepository> -Group <VBOGroupData> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [-GroupMailbox] [-GroupSite] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

* Remove organization site data.

|  |
| --- |
| Remove-VBOEntityData -Repository <VBORepository> -Site <VBOSiteData> [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

* Remove organization team data.

|  |
| --- |
| Remove-VBOEntityData -Repository <VBORepository> -Team <VBOTeamData> [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes the organization entity data.

|  |
| --- |
| ![Remove-VBOEntityData](images/icon_note.webp) Note |
| You cannot remove the organization entity data from object storage repositories with the enabled data immutability. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Repository | Specifies a backup repository where the backed-up entity data is located. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| User | Specifies an organization user entity. | VBOUserData | True | Named | True (ByValue) |
| Mailbox | Defines that the cmdlet will remove the entity mailbox data.  Default: False | SwitchParameter | False | Named | False |
| ArchiveMailbox | Defines that the cmdlet will remove the entity archive mailbox data.  Default: False | SwitchParameter | False | Named | False |
| OneDrive | Defines that the cmdlet will remove the entity OneDrive data.  Default: False | SwitchParameter | False | Named | False |
| Sites | Defines that the cmdlet will remove the entity sites data.  Default: False | SwitchParameter | False | Named | False |
| RunAsync | Defines that the command returns immediately without waiting for the task to complete.  Default: False | SwitchParameter | False | Named | False |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |
| Group | Specifies an organization group entity. | VBOGroupData | True | Named | True (ByValue) |
| GroupMailbox | Defines that the cmdlet will remove the organization group mailbox data.  Default: False | SwitchParameter | False | Named | False |
| GroupSite | Defines that the cmdlet will remove the organization group site data.  Default: False | SwitchParameter | False | Named | False |
| Site | Specifies an organization site entity. | VBOSiteData | True | Named | True (ByValue) |
| Team | Specifies an organization team entity. | VBOTeamData | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Removing User Data

|  |  |
| --- | --- |
| This example shows how to remove data of a user with the name Chuck Brown.  |  | | --- | | $repository = Get-VBORepository -Name "ABC Daily Backup"  $user = Get-VBOEntityData -Type User -Repository $repository -Name "Chuck Brown"  Remove-VBOEntityData -Repository $repository -User $user -Mailbox -ArchiveMailbox -OneDrive -Sites |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the repository. Save the result to the $repository variable. 2. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Name parameter and the $repository variable. Save result to the $user variable. 3. Run the Remove-VBOEntityData cmdlet with the $repository and $user variables and Mailbox, ArchiveMailbox, OneDrive and Sites parameters to remove the data. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Removing Group Data

|  |  |
| --- | --- |
| This example shows how to remove data of an organization group with the name Support.  |  | | --- | | $repository = Get-VBORepository -Name "ABC Daily Backup"  $group = Get-VBOEntityData -Type Group -Repository $repository -Name "Support"  Remove-VBOEntityData -Repository $repository -Group $group -Mailbox -ArchiveMailbox -OneDrive -Sites -GroupMailbox -GroupSite |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the source repository. Save the result to the $repository variable. 2. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Name parameter and the $repository variable. Save result to the $group variable. 3. Run the Remove-VBOEntityData cmdlet with the $repository and $group variables and Mailbox, ArchiveMailbox, OneDrive, Sites, GroupMailbox and GroupSite parameters to remove the data. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Removing Site Data

|  |  |
| --- | --- |
| This example shows how to remove data of an organization site with the name Support.  |  | | --- | | $repository = Get-VBORepository -Name "ABC Daily Backup"  $site = Get-VBOEntityData -Type Site -Repository $repository -Name "Support"  Remove-VBOEntityData -Repository $repository -Site $site |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the source repository. Save the result to the $repository variable. 2. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Name parameter and the $repository variable. Save result to the $site variable. 3. Run the Remove-VBOEntityData cmdlet with the $repository and $site variables to remove the data. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Removing User Data From Azure Blob Storage Archive

|  |  |
| --- | --- |
| This example shows how to remove data of a user with the name Chuck Brown from Azure Blob Storage Archive that was specified as a target for backup copy jobs.  |  | | --- | | $archiverepo = Get-VBORepository -Name "Azure Blob Storage Archive" -LongTerm  $user = Get-VBOEntityData -Type User -Repository $archiverepo -Name "Chuck Brown"  Remove-VBOEntityData -Repository $archiverepo -User $user -Mailbox -ArchiveMailbox -OneDrive -Sites |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter. Provide the LongTerm parameter. Save the result to the $archiverepo variable. 2. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Name parameter and the $archiverepo variable. Save result to the $user variable. 3. Run the Remove-VBOEntityData cmdlet with the $archiverepo and $user variables and Mailbox, ArchiveMailbox, OneDrive and Sites parameters to remove the data. |

Related Commands

* [Get-VBORepository](get-vborepository.md)
* [Get-VBOEntityData](get-vboentitydata.md)


