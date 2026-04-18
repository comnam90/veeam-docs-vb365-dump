---
title: "Get-VBOVersionBackupOptions"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboversionbackupoptions.html"
last_updated: "3/12/2026"
product_version: "8.4.0.1457"
---

# Get-VBOVersionBackupOptions


Short Description

Returns the version backup options for Microsoft organizations.

Syntax

|  |
| --- |
| Get-VBOVersionBackupOptions -Organization <IVBOOrganization> [<CommonParameters>] |

Detailed Description

This cmdlet returns the version backup options for a Microsoft organization. These options are used for the SharePoint backup.

Parameters

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| Organization | Specifies a Microsoft organization. The cmdlet will return the version backup options for this Microsoft organization. | IVBOOrganization  Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOVersionBackupOptions](vboversionbackupoptions.md) object that contains details on the version backup options for the specified Microsoft organization.

Example

Getting Version Backup Options for SharePoint Backup

This example shows how to get the version backup options for a Microsoft organization.

|  |
| --- |
| $org = Get-VBOOrganization -Name "Columbus"  Get-VBOVersionBackupOptions -Organization $org |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable.
2. Run the Get-VBOVersionBackupOptions cmdlet. Set the $org variable as the Organization parameter value.

Related Commands

[Get-VBOOrganization](get-vboorganization.md)


