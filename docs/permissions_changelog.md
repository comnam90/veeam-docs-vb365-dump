---
title: "Permissions Changelog"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_changelog.html"
last_updated: "6/23/2026"
product_version: "8.5.0.1014"
---

# Permissions Changelog


This section contains information about changes in permissions required for Veeam Backup for Microsoft 365 version 8.5 comparing to version 7.0.

Microsoft Entra Application Permissions

The following table lists changes in permissions for modern app-only authentication:

Microsoft Entra Application Permissions

| API | Permission name | Type | Usage | Description | Status |
| Microsoft Graph | ChannelMember.Read.All | Application | Backup | Accessing Microsoft Teams private and shared channels. | new |
| ChannelMember.ReadWrite.All | Delegated | Restore | Reading the current state and restoring Microsoft Teams private and shared channels using device code flow. | new |
| ChannelMember.ReadWrite.All | Application | Restore | Reading the current state and restoring Microsoft Teams private and shared channels using the Microsoft Entra application certificate. | new |
| Files.ReadWrite.All | Application | Restore | Reading the current state and restoring files of Microsoft Teams shared channels. | new |
| User.Read.All | Application | Backup, restore | Accessing Exchange mailboxes that belong to a user (getting mailbox IDs). | new |
| User.Read.All | Delegated | Restore | Accessing Exchange mailboxes that belong to a user (getting mailbox IDs). | new |
| MailboxItem.ImportExport.All | Application | Backup, restore | Exporting Exchange mailbox item data and creating a session to import an Exchange mailbox item. | new |
| MailboxItem.ImportExport | Delegated | Restore | Creating a session to import an Exchange mailbox item. | new |
| MailboxFolder.ReadWrite.All | Application | Backup | Accessing Exchange mailbox folders. | new |
| MailboxFolder.ReadWrite.All | Application | Restore | Creating a new mailbox folder or subfolder in a user mailbox. | new |
| MailboxFolder.ReadWrite | Delegated | Restore | Creating a new mailbox folder or subfolder in a user mailbox. | new |
| MailboxFolder.Read.All | Application | Restore | Accessing Exchange mailbox folders to do the following:   * Read properties and relationships of a mailbox folder.  * Get mailbox folder objects that were added, deleted, or removed from a user mailbox. * Create a new mailbox folder or subfolder in a user mailbox. | new |
| MailboxItem.Read.All | Application | Backup, restore | Accessing Exchange mailbox items to do the following:   * Get mailbox item properties. * Get mailbox items that were added, deleted, or updated in a mailbox folder. | new |
| MailboxItem.Read | Delegated | Restore | Accessing Exchange mailbox items within a mailbox folder in a mailbox. | new |

Linux-based Backup Proxy Server

You can add Linux-based backup proxy servers to the Veeam Backup for Microsoft 365 backup infrastructure. A service account must be granted permissions to run Veeam Backup for Microsoft 365 Proxy Service on a machine with Linux operating systems installed. For more information, see [Permissions for Service Account on Linux](permissions_linux.md).

Windows-based Backup Proxy Server

You can add Windows-based backup proxy servers to the Veeam Backup for Microsoft 365 backup infrastructure. A service account must be granted permissions to run Veeam Backup for Microsoft 365 Proxy Service on a machine with Windows operating systems installed. For more information, see [Permissions for Service Account on Windows](permissions_windows.md).


