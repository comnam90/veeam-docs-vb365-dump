---
title: "Install-VBOLicense"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/install-vbolicense.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---

# Install-VBOLicense


Short Description

Installs the license on the Veeam Backup for Microsoft 365 server.

Syntax

|  |
| --- |
| Install-VBOLicense -Path <String> [<CommonParameters>] |

Detailed Description

This cmdlet installs or updates the product license on the Veeam Backup for Microsoft 365 server. You must install the license from the license LIC file.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Path | Specifies a path to the license LIC file. | String | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Installing License on Veeam Backup for Microsoft 365 Server

This command installs the license on the Veeam Backup for Microsoft 365 server.

|  |
| --- |
| Install-VBOLicense -Path "C:\Veeam\Office365\Licenses\veeam\_backup\_microsoft\_365\_subscription\_xxx.lic" |


