---
title: "New-VBOBackupItem"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vbobackupitem.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# New-VBOBackupItem


Short Description

Creates organization objects.

Syntax

This cmdlet provides parameter sets that allow you to:

* Create objects that represent users.

|  |
| --- |
| New-VBOBackupItem -User <VBOOrganizationUser[]> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [<CommonParameters>] |

* Create objects that represent organizations.

|  |
| --- |
| New-VBOBackupItem -Organization <VBOOrganization[]> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [-Teams] [-TeamsChats] [<CommonParameters>] |

* Create objects that represents sites.

|  |
| --- |
| New-VBOBackupItem -Site <VBOOrganizationSite[]> [<CommonParameters>] |

* Create objects that represent groups.

|  |
| --- |
| New-VBOBackupItem -Group <VBOOrganizationGroup[]> [-Mailbox] [-ArchiveMailbox] [-OneDrive] [-Sites] [-GroupMailbox] [-GroupSite] [<CommonParameters>] |

* Create objects that represent personal sites.

|  |
| --- |
| New-VBOBackupItem [-PersonalSites] [<CommonParameters>] |

* Create objects that represent teams.

|  |
| --- |
| New-VBOBackupItem -Team <VBOOrganizationTeam[]> [-TeamsChats] [<CommonParameters>] |

Detailed Description

Creates organization objects. You can add or exclude these objects from a backup job.

For more information on object types, see the [Organization Object Types](https://helpcenter.veeam.com/docs/vbo365/guide/vbo_object_types.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.

Run the [Add-VBOBackupItem](add-vbobackupitem.md) cmdlet to create a list of objects included in a backup job. The job will back up these objects.

Run the [Add-VBOExcludedBackupItem](add-vboexcludedbackupitem.md) cmdlet to create a list of objects excluded from a backup job. The job will exclude these objects from backup.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| User | Specifies an array of users added to Veeam Backup for Microsoft 365. The cmdlet will create an organization object that contains a user. | Accepts the [VBOOrganizationUser](vboorganizationuser.md)[] object.  To get this object, run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet. | True | Named | False |
| Mailbox | Defines that the cmdlet will create an organization object that will have the mailbox option enabled.  Default: False | SwitchParameter | False | Named | False |
| ArchiveMailbox | Defines that the cmdlet will create an organization object that will have the archived mailbox option enabled.  Default: False  Note: You cannot specify this parameter for the PublicMailbox type of the user. | SwitchParameter | False | Named | False |
| OneDrive | Defines that the cmdlet will create an organization object that will have the OneDrive option enabled.  Default: False  Note: You cannot specify this parameter for the PublicMailbox type of the user. | SwitchParameter | False | Named | False |
| Sites | Defines that the cmdlet will create an organization object that will have the sites option enabled.  Default: False | SwitchParameter | False | Named | False |
| Organization | Specifies an array of organizations added to Veeam Backup for Microsoft 365. The cmdlet will create an organization object that contains an organization. | Accepts the [VBOOrganization](vboorganization.md)[] object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | False |
| Teams | Defines that the cmdlet will create an organization object that will have the teams option enabled.  Default: False | SwitchParameter | False | Named | False |
| TeamsChats | Defines that the cmdlet will create an organization object that will have the team chats option enabled.  Default: False | SwitchParameter | False | Named | False |
| Site | Specifies an array of sites added to Veeam Backup for Microsoft 365. The cmdlet will create an organization object that contains a site. | Accepts the [VBOOrganizationSite](vboorganizationsite.md)[] object.  To get this object, run the [Get-VBOOrganizationSite](get-vboorganizationsite.md) cmdlet. | True | Named | False |
| Group | Specifies an array of groups added to Veeam Backup for Microsoft 365. The cmdlet will create an organization object that contains a group. | Accepts the [VBOOrganizationGroup](vboorganizationgroup.md)[] object.  To get this object, run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet. | True | Named | False |
| GroupMailbox | Defines that the cmdlet will create an organization object that will have the group mailbox enabled.  Default: False | SwitchParameter | False | Named | False |
| GroupSite | Defines that the cmdlet will create an organization object that will have the group site option enabled.  Default: False | SwitchParameter | False | Named | False |
| Team | Specifies an array of teams added to Veeam Backup for Microsoft 365. The cmdlet will create an organization object that contains a team. | Accepts the [VBOOrganizationTeam](vboorganizationteam.md)[] object.  To get this object, run the [Get-VBOOrganizationTeam](get-vboorganizationteam.md) cmdlet. | True | Named | False |
| PersonalSites | Defines that the cmdlet will create an organization object with the personal sites option enabled.  Default: False | SwitchParameter | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating User Object

|  |  |
| --- | --- |
| This example shows how to create an organization object that contains a user. An object will be created with the following settings:   * The object will contain the William Sonders user. * The object will have all options enabled except for the mailbox.   |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $user = Get-VBOOrganizationUser -Organization $org -DisplayName "William Sonders"  New-VBOBackupItem -User $user -Mailbox:$false -ArchiveMailbox -OneDrive -Sites |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set ABC as the Name parameter value. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet. Set the $org variable as the Organization parameter value. Set William Sonders as the DisplayName parameter value. Save the result to the $user variable. 3. Run the New-VBOBackupItem cmdlet. Specify the following settings:  * Set the $user variable as the User parameter value. * Set the ArchiveMailbox, OneDrive and Sites parameters. * Set :$false as the Mailbox parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Object with Mailbox, Archive Mailbox, Teams, Team Chats and Sites

|  |  |
| --- | --- |
| This example shows how to create a backup item with an organization ABC mailbox, archive mailbox and all of the sites, teams and team chats but without the OneDrive processing option.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  New-VBOBackupItem -Organization $org -Mailbox -ArchiveMailbox -OneDrive:$false -Sites -Teams -TeamsChats |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the New-VBOBackupItem cmdlet with the $org variable as the Organization parameter value, the Mailbox, ArchiveMailbox, Sites, Teams and TeamsChats parameters, and the false value for the OneDrive parameter to create a backup item with all ABC organization processing options except for the OneDrive components. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Creating Site Object

|  |  |
| --- | --- |
| This example shows how to create a backup item with an ABC organization site with a given URL.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $siteUrl = "https://exampleorganization.sharepoint.com/sites/exampleparentsite"  $site = Get-VBOOrganizationSite -Organization $org -URL $siteUrl  New-VBOBackupItem -Site $site |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Save a certain SharePoint organization site URL address to the $siteUrl variable. 3. Run the [Get-VBOOrganizationSite](get-vboorganizationsite.md) cmdlet with the $org variable and the $siteURL variable as the URL parameter value to get an ABC organization site. Save the result to the $site variable. 4. Run the New-VBOBackupItem cmdlet with the $site variable to create a backup item with ABC organization site with a given URL. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Creating Group Object

|  |  |
| --- | --- |
| This example shows how to create a backup item with all processing options for the UsersAlpha organization user group.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $group = Get-VBOOrganizationGroup -Organization $org -DisplayName "UsersAlpha"  New-VBOBackupItem -Group $group -Mailbox -ArchiveMailbox -OneDrive -Sites -GroupMailbox -GroupSite |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationGroup](get-vboorganizationgroup.md) cmdlet with the $org variable and the UsersAlpha value for the DisplayName parameter to get an organization user group with the display name UsersAlpha. Save the result to the $group variable. 3. Run the New-VBOBackupItem cmdlet with the $group variable as the Group parameter value and the Mailbox, ArchiveMailbox, OneDrive, Sites, GroupMailbox and GroupSite parameters to create a backup item with all processing options for the UsersAlpha organization user group. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Creating Object to Process Personal Sites

|  |  |
| --- | --- |
| This command creates a backup item with the PersonalSites processing option.  |  | | --- | | New-VBOBackupItem -PersonalSites:$true | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 6: Creating Object to Process Team with Team Chats

|  |  |
| --- | --- |
| This example shows how to create a backup item with the TeamsChats processing option for a team with the display name IT.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  $team = Get-VBOOrganizationTeam -Organization $org -DisplayName "IT"  New-VBOBackupItem -Team $team -TeamsChats |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationTeam](get-vboorganizationteam.md) cmdlet. Set the $org variable as the Organization parameter value. Specify the DisplayName parameter value. Save the result to the $team variable. 3. Run the New-VBOBackupItem cmdlet with the $team variable as the Team parameter value and the TeamsChats parameter to create a backup item to process the IT team with team chats. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)
* [Get-VBOOrganizationSite](get-vboorganizationsite.md)
* [Get-VBOOrganizationTeam](get-vboorganizationteam.md)


