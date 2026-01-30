---
title: "Notification Settings"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_notification_settings.html"
last_updated: "7/18/2024"
product_version: "8.3.0.2201"
---

# Notification Settings


You can configure notification settings if you want Veeam Backup for Microsoft 365 to send email notifications about backup and backup copy job results.

You can allow Veeam Backup for Microsoft 365 to send email notifications on behalf of your Google or Microsoft 365 account using [OAuth 2.0 Authorization Framework](https://datatracker.ietf.org/doc/html/rfc6749), or you can specify connection settings of your SMTP server that uses basic authentication.

For more information, see the following sections:

* [SMTP Server with Basic Authentication](smtp_server.md)
* [Google Account](google_acc.md)
* [Microsoft 365 Account](m365_acc.md)

|  |
| --- |
| Note |
| Notifications about the backup and backup copy job results are sent by a backup proxy server specified in the backup repository settings. For more information, see [Specify Backup Repository](specify_backup_proxy_server.md). |


