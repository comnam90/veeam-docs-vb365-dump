---
title: "Veeam Backup Account Permissions"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_veeam_backup_account.html"
last_updated: "8/22/2024"
product_version: "8.3.0.2201"
---

# Veeam Backup Account Permissions


Veeam Backup for Microsoft 365 requires the Veeam Backup account credentials when you add the following Microsoft organizations:

* [On-premises Microsoft Exchange organizations](vbo_add_onpremises_org.md)
* [On-premises Microsoft SharePoint organizations](vbo_add_onpremises_org.md)
* Microsoft 365 organization with basic authentication

This functionality is only available in Microsoft Entra China region through REST API and PowerShell.

For Microsoft 365 organizations that were added to previous installations of the product using modern authentication method with legacy protocols allowed, Veeam Backup for Microsoft 365 also uses Veeam Backup account.

Veeam Backup account is required to establish and maintain connection between Veeam Backup for Microsoft 365 and Microsoft 365 organizations or on-premises Microsoft organizations and perform backup and restore of the organization data.

Depending on data that you want to protect, you must assign the following roles and permissions to Veeam Backup account:

* [Microsoft Exchange Data](permissions_exchange.md)

Roles and permissions required to protect data in Microsoft Exchange organizations.

* [Microsoft SharePoint and OneDrive for Business Data](permissions_sharepoint.md)

Roles and permissions required to protect data in Microsoft SharePoint and OneDrive for Business organizations.

* [Microsoft Teams Data](permissions_teams.md)

Roles and permissions required to protect Microsoft Teams data.


