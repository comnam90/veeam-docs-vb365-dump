---
title: "Stop-VBORestoreSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/stop-vborestoresession.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# Stop-VBORestoreSession


Short Description

Stops Veeam Backup for Microsoft 365 restore sessions.

Syntax

|  |
| --- |
| Stop-VBORestoreSession -Session <VBORestoreSession> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet stops a specific restore session.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Session | Specifies a restore session that you want to stop. | Accepts the [VBORestoreSession](vborestoresession.md) object.  To get this object, run the [Get-VBORestoreSession](get-vborestoresession.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Stopping Restore Session

This example shows how to stop the restore session.

|  |
| --- |
| $session = Get-VBORestoreSession  Stop-VBORestoreSession -Session $session |

Perform the following steps:

1. Run the [Get-VBORestoreSession](get-vborestoresession.md) cmdlet to get the restore session you want to stop. Save the result to the $session variable.
2. Run the Stop-VBORestoreSession cmdlet with the $session variable.

Related Commands

[Get-VBORestoreSession](get-vborestoresession.md)


