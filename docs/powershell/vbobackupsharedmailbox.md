---
title: "VBOBackupSharedMailbox"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbobackupsharedmailbox.html"
last_updated: "1/15/2026"
product_version: "8.3.0.2201"
---

# VBOBackupSharedMailbox


Contains details about a backup shared mailbox. See also [VBOBackupItem](vbobackupitem.md).

| Property | Type | Description |
| --- | --- | --- |
| User | [VBOOrganizationUser](vboorganizationuser.md) | Details about the organization user. |
| Mailbox | Bool | If True, the mailbox option is enabled. |
| ArchiveMailbox | Bool | If True, the archived mailbox option is enabled. |
| OneDrive | Bool | If True, the OneDrive option is enabled. |
| Site | Bool | If True, the sites option is enabled. |

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


