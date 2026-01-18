---
title: "VBOEmailSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboemailsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOEmailSettings


Contains details about email notification settings.

| Property | Type | Description |
| --- | --- | --- |
| EnableNotification | Bool | If True, sending email notifications is enabled. |
| AuthenticationType | VBOAuthenticationType | Authentication type. Possible values:   * CustomSmtp * GoogleGmail * Microsoft365 |
| SMTPServer | String | DNS name or IP address of the SMTP server. |
| Port | Int | Port number. |
| UseSSL | Bool | If True, the SSL encryption if enabled. |
| UseAuthentication | Bool | If True, the SMTP server requires authentication. |
| Username | String | User name used for authentication to the SMTP server. |
| From | String | Email address of the notification sender. |
| To | String | Email address of the notification recipient. |
| Subject | String | Subject for email notifications. |
| NotifyOnSuccess | Bool | If True, Veeam Backup for Microsoft 365 sends email notifications if a backup or backup copy job completes successfully without any warnings or errors. |
| NotifyOnWarning | Bool | If True, Veeam Backup for Microsoft 365 sends email notifications if a backup or backup copy job completes with warnings. |
| NotifyOnFailure | Bool | If True, Veeam Backup for Microsoft 365 sends email notifications if a backup or backup copy job completes with errors. |
| SupressUntilLastRetry | Bool | If True, Veeam Backup for Microsoft 365 sends email notifications only after the last attempt of a backup or backup copy job. |
| AttachDetailedReport | Bool | If True, Veeam Backup for Microsoft 365 sends a detailed report about the job results as an email attachment. |
| ClientId | String | Client ID obtained while registering an application in the Google Cloud console or Microsoft Identity platform. |
| TenantId | String | Tenant ID in Microsoft Entra ID. |
| UserId | String | Authenticated user account ID. |
| MailApiUrl | String | Authenticated user account ID. |
| IsAuthenticated | Bool | If True, a user is authenticated. |

Related Commands

* [Get-VBOEmailSettings](get-vboemailsettings.md)
* [Set-VBOEmailSettings](set-vboemailsettings.md)


