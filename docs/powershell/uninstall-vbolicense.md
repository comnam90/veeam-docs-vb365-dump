---
title: "uninstall-vbolicense"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/uninstall-vbolicense.html"
last_updated: "5/14/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes the currently installed license from Veeam Backup for Microsoft 365.

Syntax

|  |
| --- |
| Uninstall-VBOLicense [-Force] [<CommonParameters>] |

Detailed Description

This cmdlet uninstalls the product license from the Veeam Backup for Microsoft 365 server.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Force | Defines that the cmdlet will remove the installed license without showing warnings in the PowerShell console.  Default: False  If you do not provide the parameter, the cmdlet will prompt you to confirm the operation. | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Uninstalling License from Veeam Backup for Microsoft 365 Server

This command uninstalls the license from the Veeam Backup for Microsoft 365 server without prompting the confirmation.

|  |
| --- |
| Uninstall-VBOLicense -Force |

Page updated 5/14/2024

Page content applies to build 8.3.0.2201
