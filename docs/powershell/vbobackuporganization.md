---
title: "VBOBackupOrganization"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbobackuporganization.html"
last_updated: "1/15/2026"
product_version: "8.3.0.2201"
---

# VBOBackupOrganization


Contains details about a backup organization. See also [VBOBackupItem](vbobackupitem.md).

| Property | Type | Description |
| --- | --- | --- |
| Organization | [VBOOrganization](vboorganization.md) | Details about the Microsoft organization. |
| Mailbox | Bool | If True, the mailbox option is enabled. |
| ArchiveMailbox | Bool | If True, the archived mailbox option is enabled. |
| OneDrive | Bool | If True, the OneDrive option is enabled. |
| Sites | Bool | If True, the sites option is enabled. |
| Teams | Bool | If True, the teams option is enabled. |
| TeamsChats | Bool | If True, the team chats option is enabled. |

Related Commands

* [Add-VBOBackupItem](add-vbobackupitem.md)
* [Get-VBOBackupItem](get-vbobackupitem.md)
* [Set-VBOBackupItem](set-vbobackupitem.md)
* [Remove-VBOBackupItem](remove-vbobackupitem.md)
* [Get-VBOExcludedBackupItem](get-vboexcludedbackupitem.md)
* [Add-VBOExcludedBackupItem](add-vboexcludedbackupitem.md)
* [Remove-VBOExcludedBackupItem](remove-vboexcludedbackupitem.md)
* [Add-VBOJob](add-vbojob.md)
* [Set-VBOJob](set-vbojob.md)


