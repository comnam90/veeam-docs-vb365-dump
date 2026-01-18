---
title: "VBOFolderExclusions"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbofolderexclusions.html"
last_updated: "1/15/2026"
product_version: "8.3.0.2201"
---

# VBOFolderExclusions


Contains details about folder exclusion settings.

| Property | Type | Description |
| --- | --- | --- |
| DeletedItems | Bool | If True, the Deleted Items and Recoverable Items mailbox folders are not processed. |
| Drafts | Bool | If True, the Drafts mailbox folder is not processed. |
| JunkEmail | Bool | If True, the Junk Email mailbox folder is not processed. |
| Outbox | Bool | If True, the Outbox mailbox folder is not processed. |
| SyncIssues | Bool | If True, the Sync Issues mailbox folder is not processed. |
| LitigationHold | Bool | If True, items of mailboxes placed on Litigation Hold are not processed. |
| InPlaceHold | Bool | If True, preserved items of mailboxes placed on In-Place Hold are not processed. |

Related Commands

* [Get-VBOFolderExclusions](get-vbofolderexclusions.md)
* [Set-VBOFolderExclusions](set-vbofolderexclusions.md)


