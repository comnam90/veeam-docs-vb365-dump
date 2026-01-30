---
title: "Veeam Backup for Microsoft 365 Feature Deprecation"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/feature_deprecation.html"
last_updated: "12/5/2024"
product_version: "8.3.0.2201"
---

# Veeam Backup for Microsoft 365 Feature Deprecation


In Veeam Backup for Microsoft 365 version 8, the following product features became deprecated:

* Modern authentication method with legacy protocols allowed.

Since [Microsoft deprecated basic authentication and legacy authentication protocols](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437), Veeam Backup for Microsoft 365 does not support adding new Microsoft 365 organizations using modern authentication method with legacy protocols allowed. However, you can continue to use Veeam Backup for Microsoft 365 to back up and restore data of Microsoft 365 organizations that were added to previous installations of the product using this authentication method. For more information, see [Permissions for Modern Authentication and Legacy Protocols](ad_app_permissions_legacy.md).

In future versions of Veeam Backup for Microsoft 365, the following product features will be deprecated:

* Basic authentication method. In Veeam Backup for Microsoft 365 version 8, adding Microsoft 365 organizations using basic authentication method is only available in Microsoft Entra China region through REST API and PowerShell.
* Auxiliary backup accounts. For more information, see [Backup Accounts](backup_accounts.md).

* Support for Microsoft 365 organizations located in Microsoft Entra Germany region. In Veeam Backup for Microsoft 365 version 8, you can add organizations located in Microsoft Entra Germany region only through REST API and PowerShell. For more information, see [Limitations for Microsoft Entra Germany region](germany.md).
* SMB shares. For more information, see [Network Attached Storage (SMB Shares)](br_smb.md).
* Using multiple auxiliary backup applications. For more information, see [Backup Applications](backup_applications.md).
* On-premises Microsoft Exchange and Microsoft SharePoint organizations. For more information, see [Adding On-Premises Microsoft Organizations](vbo_add_onpremises_org.md).

For more information on deprecated features in Veeam Backup for Microsoft 365, see [this Veeam KB article](https://www.veeam.com/kb4567).


