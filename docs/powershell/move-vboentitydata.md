---
title: "move-vboentitydata"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/move-vboentitydata.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Moves organization data from a JET-based backup repository to another JET-based backup repository or object storage repository.

Syntax

This cmdlet provides parameter sets that allow you to:

* Move of an organization user data.

|  |
| --- |
| Move-VBOEntityData -From <VBORepository> -To <VBORepository> -User <VBOUserData> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [-NoDelete] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

* Move of an organization group data.

|  |
| --- |
| Move-VBOEntityData -From <VBORepository> -To <VBORepository> -Group <VBOGroupData> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [-GroupMailbox] [-GroupSite] [-NoDelete] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

* Move of an organization site data.

|  |
| --- |
| Move-VBOEntityData -From <VBORepository> -To <VBORepository> -Site <VBOSiteData> [-NoDelete] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

* Move of an organization team data.

|  |
| --- |
| Move-VBOEntityData -From <VBORepository> -To <VBORepository> -Team <VBOTeamData> [-NoDelete] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet moves the organization data between repositories and supports the following scenarios:

* Data move from one JET-based backup repository to another JET-based backup repository.
* Data move from a JET-based backup repository to an object storage repository.

|  |
| --- |
| ![Move-VBOEntityData](images/icon_important.webp) Important |
| Consider the following:   * Data move is not supported for object storage repositories with the enabled data immutability. * Data move from an object storage repository to another object storage repository (including the object storage repository specified as target for backup copy jobs) or a JET-based backup repository is not supported. * Target backup repository or an object storage repository where you want to move backed-up data must not contain any data associated with the items that you want to move. * If the move process was interrupted, make sure to resume your data move before starting backup jobs to back up data to the source or target backup repository. * As data is being moved, Veeam Backup for Microsoft 365 removes items from the source backup repository and replaces them with the whitespace in the source backup repository database. Use the NoDelete parameter to disable data remove. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| From | Specifies a source JET-based backup repository. The cmdlet will move data from this backup repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| To | Specifies a target JET-based backup repository or object storage repository for backed-up data. The cmdlet will move data to this backup repository. You can specify one of the following types of repositories:   * Local JET-based backup repository * Object storage repository | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| User | Specifies the organization user data that the cmdlet will move. | VBOUserData | True | Named | True (ByValue) |
| Mailbox | Defines that the cmdlet will move the entity mailbox data.  Default: False | SwitchParameter | False | Named | False |
| ArchiveMailbox | Defines that the cmdlet will move the entity archive mailbox data.  Default: False | SwitchParameter | False | Named | False |
| OneDrive | Defines that the cmdlet will move the entity OneDrive data.  Default: False | SwitchParameter | False | Named | False |
| Sites | Defines that the cmdlet will move the entity sites data.  Default: False | SwitchParameter | False | Named | False |
| NoDelete | Defines that the cmdlet will not remove items from the source JET-based backup repository.  Default: False | SwitchParameter | False | Named | False |
| RunAsync | Defines that the command returns immediately without waiting for the task to complete.  Default: False | SwitchParameter | False | Named | False |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |
| Group | Specifies the organization group data that the cmdlet will move. | VBOGroupData | True | Named | True (ByValue) |
| GroupMailbox | Defines that the cmdlet will move the organization group mailbox data.  Default: False | SwitchParameter | False | Named | False |
| GroupSite | Defines that the cmdlet will move the organization group site data.  Default: False | SwitchParameter | False | Named | False |
| Site | Specifies the organization site data that the cmdlet will move. | VBOSiteData | True | Named | True (ByValue) |
| Team | Specifies the organization team data that the cmdlet will move. | VBOTeamData | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Moving User Data

|  |  |
| --- | --- |
| This example shows how to move data of a user with the name Chuck Brown from one JET-based backup repository to another.  |  | | --- | | $repository = Get-VBORepository -Name "ABC Daily Backup"  $destination = Get-VBORepository -Name "Support North"  $user = Get-VBOEntityData -Type User -Repository $repository -Name "Chuck Brown"  Move-VBOEntityData -From $repository -To $destination -User $user -Mailbox -ArchiveMailbox -OneDrive -Sites |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the source backup repository. Save the result to the $repository variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the target backup repository. Save result to the $destination variable. 3. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Name parameter and the $repository variable. Save result to the $user variable. 4. Run the Move-VBOEntityData cmdlet with the $repository, $destination and $user variables and Mailbox, ArchiveMailbox, OneDrive and Sites parameters to move the data to the specified backup repository. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Moving Group Data

|  |  |
| --- | --- |
| This example shows how to move data of an organization group with the name Support from one JET-based backup repository to another.  |  | | --- | | $repository = Get-VBORepository -Name "ABC Daily Backup"  $destination = Get-VBORepository -Name "Support North"  $group = Get-VBOEntityData -Type Group -Repository $repository -Name "Support"  Move-VBOEntityData -From $repository -To $destination -Group $group -Mailbox -ArchiveMailbox -OneDrive -Sites -GroupMailbox -GroupSite |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the source backup repository. Save the result to the $repository variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the target backup repository. Save result to the $destination variable. 3. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Name parameter and the $repository variable. Save result to the $group variable. 4. Run the Move-VBOEntityData cmdlet with the $repository, $destination and $group variables and Mailbox, ArchiveMailbox, OneDrive, Sites, GroupMailbox and GroupSite parameters to move the data to the specified backup repository. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Moving Site Data

|  |  |
| --- | --- |
| This example shows how to move data of an organization site with the name Support from one JET-based backup repository to another.  |  | | --- | | $repository = Get-VBORepository -Name "ABC Daily Backup"  $destination = Get-VBORepository -Name "Support North"  $site = Get-VBOEntityData -Type Site -Repository $repository -Name "Support"  Move-VBOEntityData -From $repository -To $destination -Site $site |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the source backup repository. Save the result to the $repository variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the target backup repository. Save result to the $destination variable. 3. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Name parameter and the $repository variable. Save result to the $site variable. 4. Run the Move-VBOEntityData cmdlet with the $repository, $destination and $site variables to move the data to the specified backup repository. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Moving User Data to Object Storage Repository

|  |  |
| --- | --- |
| This example shows how to move the Chuck Brown user data from a JET-based backup repository to an object storage repository.  |  | | --- | | $source = Get-VBORepository -Name "ABC Daily Backup"  $target = Get-VBORepository -Name "Object Storage"  $user = Get-VBOEntityData -Type User -Repository $source -Name "Chuck Brown"  Move-VBOEntityData -From $source -To $target -User $user -Mailbox -ArchiveMailbox -RunAsync |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the source backup repository. Save the result to the $source variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter to get the target object storage repository. Save result to the $target variable. 3. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet with the Type and Name parameters and the $source variable. Save result to the $user variable. 4. Run the Move-VBOEntityData cmdlet with the $source, $target and $user variables to move the data to the specified object storage repository. |

Related Commands

* [Get-VBORepository](get-vborepository.md)
* [Get-VBOEntityData](get-vboentitydata.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
