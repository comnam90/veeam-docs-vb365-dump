---
title: "Get-VBOFolderExclusions"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbofolderexclusions.html"
last_updated: "1/13/2026"
product_version: "8.3.0.2201"
---

# Get-VBOFolderExclusions


Short Description

Returns folder exclusion settings.

Syntax

|  |
| --- |
| Get-VBOFolderExclusions [<CommonParameters>] |

Detailed Description

This cmdlet returns folder exclusion settings. Backup jobs will not process the specified mailbox data.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOFolderExclusions](vbofolderexclusions.md) object that contains folder exclusion settings.

Example

Getting Folder Exclusion Settings

This command returns the folder exclusion settings.

|  |
| --- |
| Get-VBOFolderExclusions |


