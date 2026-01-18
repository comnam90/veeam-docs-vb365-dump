---
title: "Start-VBOOrganizationSynchronization"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vboorganizationsynchronization.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# Start-VBOOrganizationSynchronization


Short Description

Starts to synchronize Microsoft organization objects with the organization cache database.

|  |
| --- |
| ![Start-VBOOrganizationSynchronization](images/icon_note.webp) Note |
| Synchronization of objects with the organization cache database is only available for Microsoft organizations with modern app-only authentication. |

Syntax

|  |
| --- |
| Start-VBOOrganizationSynchronization -Organization <IVBOOrganization> [-Full] [<CommonParameters>] |

Detailed Description

This cmdlet starts to synchronize Microsoft organization objects with the organization cache database. Veeam Backup for Microsoft 365 uses the organization cache database to store information about all restore points created for Microsoft 365 organizations and to index all objects in Microsoft 365 organizations with modern app-only authentication.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will start synchronization of objects for this Microsoft organization. | IVBOOrganization  Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| Full | Defines that the cmdlet will start synchronization of all objects in this Microsoft organization.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Synchronizing All Microsoft Organization Objects with Organization Cache Database

This example shows how to start synchronizing all Microsoft organization objects with the organization cache database.

|  |
| --- |
| $orgs = Get-VBOOrganization  foreach ($org in $orgs) { Start-VBOOrganizationSynchronization -Organization $org -Full:$true } |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $orgs variable.
2. Run the Start-VBOOrganizationSynchronization cmdlet. Set the $org variable as the Organization parameter value. Set the true value for the Full parameter.

Related Commands

[Get-VBOOrganization](get-vboorganization.md)


