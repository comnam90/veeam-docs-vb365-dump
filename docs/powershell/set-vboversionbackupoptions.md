---
title: "Set-VBOVersionBackupOptions"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboversionbackupoptions.html"
last_updated: "3/12/2026"
product_version: "8.4.0.1457"
---

# Set-VBOVersionBackupOptions


Short Description

Modifies the version backup options for Microsoft organizations.

Syntax

|  |
| --- |
| Set-VBOVersionBackupOptions -Organization <IVBOOrganization> -SharePointBackupMode <VBOSharePointVersionBackupMode> [<CommonParameters>] |

Detailed Description

This cmdlet modifies the version backup options for a Microsoft organization. These options are used for the SharePoint backup.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| Organization | Specifies a Microsoft organization. The cmdlet will modify the version backup options for this Microsoft organization. | IVBOOrganization  Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| SharePointBackupMode | Specifies the version backup mode used for the SharePoint backup. You can set either of the following modes:   * All. The backup job will back up all versions of SharePoint items. * Latest. The backup job will back up only the latest version of SharePoint items.   Default: Latest | VBOSharePointVersionBackupMode | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOVersionBackupOptions](vboversionbackupoptions.md) object that contains details on the version backup options for the specified Microsoft organization.

Example

Modifying Version Backup Options for SharePoint Backup

This example shows how to change the version backup options for a Microsoft organization.

|  |
| --- |
| $org = Get-VBOOrganization -Name "Columbus"  Set-VBOVersionBackupOptions -Organization $org -SharePointBackupMode All |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable.
2. Run the Set-VBOVersionBackupOptions cmdlet. Set the $org variable as the Organization parameter value. Set All as the SharePointBackupMode parameter value.

Related Commands

[Get-VBOOrganization](get-vboorganization.md)


